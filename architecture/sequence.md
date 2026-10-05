---
# Diagram 5 – Sequence Diagram: Book a Ride and Driver Acceptance

```mermaid
sequenceDiagram

    actor Student
    participant UI as Web App UI
    participant API as API
    participant Maps as Maps Provider
    participant DB as PostgreSQL Database
    participant Notify as Notification Provider
    actor Driver

    Student->>UI: Enter pickup, destination and time

    UI->>API: POST /api/bookings

    API->>Maps: Request distance and ETA
    Maps-->>API: Return distance and ETA

    API->>DB: Create booking

    DB-->>API: Booking created

    API-->>UI: Booking confirmation

    UI-->>Student: Show AwaitingDriver

    API->>Notify: Notify available drivers

    Notify-->>Driver: New booking notification

    Driver->>API: Accept booking

    API->>DB: Update booking to DriverAssigned

    DB-->>API: Booking updated

    API->>Notify: Notify student

    Notify-->>Student: Driver assigned

    loop Poll every few seconds

        Student->>UI: Refresh trip status

        UI->>API: GET /api/bookings/{id}

        API->>DB: Read booking and location

        DB-->>API: Status and latest location

        API-->>UI: Booking JSON

        UI-->>Student: Display driver status/location

    end

    Driver->>API: Start trip

    API->>DB: Set status InProgress

    Driver->>API: Complete trip

    API->>DB: Set status Completed

    API-->>Student: Trip completed
