# Activity (Swimlanes Diagram)
```mermaid
flowchart TB
    subgraph Student["Student"]
        direction LR
        S0((Start))
        S1["Open booking form"]
        S2["Enter pickup point,<br/>destination and time"]
        S3["Receive 'driver<br/>assigned' alert"]
        S4["Arrive at school and<br/>view trip summary"]
        S5(("End: trip completed"))
    end

    subgraph System["System"]
        direction LR
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
        direction LR
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


