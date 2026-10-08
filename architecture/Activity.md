flowchart TB
    subgraph Student["Student"]
        direction TB
        S0((Start))
        S1["Open booking form"]
        S2["Enter pickup point,<br/>destination and time"]
        S3["Receive 'driver<br/>assigned' alert"]
        S4["Arrive at school and<br/>view trip summary"]
        S5(("End: trip completed"))
    end

    subgraph System["System"]
        direction TB
        Y1["Validate booking<br/>details"]
        D1{"Details valid?"}
        Y2["Create booking,<br/>status = AwaitingDriver"]
        Y3["Alert available<br/>drivers"]
        D2{"Accept request?"}
        Y4["Set status = Expired,<br/>alert student"]
        Y5["Assign driver,<br/>status = DriverAssigned"]
        Y6["Set status = InProgress,<br/>share driver location"]
        Y7["Set status = Completed,<br/>save fare"]
    end

    subgraph Driver["Driver"]
        direction TB
        R1["Review booking<br/>request"]
        R2["Drive to pickup point"]
        R3["Start trip"]
        R4["Complete trip"]
    end

    S0 --> S1 --> S2 --> Y1 --> D1
    D1 -->|"details invalid"| S2
    D1 -->|"details valid"| Y2 --> Y3 --> R1 --> D2
    D2 -->|"declined or timed out"| Y4
    D2 -->|"accepted"| Y5 --> S3
    Y5 --> R2 --> R3 --> Y6 --> R4 --> Y7 --> S4 --> S5

Diagram 5 — Sequence Diagram

sequenceDiagram
    participant Student
    participant UI as Booking Page (UI)
    participant API
    participant DB as Database
    participant Maps as Maps Provider (external)
    participant Notify as Notification Provider (external)
    participant Driver as Driver (via Driver Page)

    Student->>UI: Submit pickup point, destination and time
    UI->>API: POST /api/bookings
    API->>Maps: Request distance and ETA
    Maps-->>API: Distance and ETA

    alt details valid and maps answered
        API->>DB: Insert booking (status = AwaitingDriver)
        DB-->>API: Booking id
        API-)Notify: Alert available drivers (async)
        API-->>UI: 201 Created + booking id
        UI-->>Student: Show "Looking for a driver"
    else invalid details or maps unavailable
        API-->>UI: 422 / 503 error
        UI-->>Student: Show error, let student retry
    end

    Driver->>API: POST /api/bookings/{id}/accept
    API->>DB: Set DriverAssigned only if status = AwaitingDriver

    alt one row updated
        DB-->>API: 1 row updated
        API-)Notify: Alert student: driver assigned (async)
        API-->>Driver: 200 OK
    else already taken, cancelled or expired
        DB-->>API: 0 rows updated
        API-->>Driver: 409 Conflict
    end

    loop every few seconds while the booking is active
        UI->>API: GET /api/bookings/{id}
        API->>DB: Read status and latest driver location
        DB-->>API: Status and location
        API-->>UI: Booking JSON

        opt status is DriverAssigned
            UI-->>Student: Show driver details and location
        end
    end
