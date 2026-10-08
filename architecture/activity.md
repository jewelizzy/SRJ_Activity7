# Activity Diagram
'''mermaid
flowchart LR

    subgraph Student["Student"]

        S1["Open booking form"]

        S2["Enter pickup point,<br/>destination and time"]

        S3["Receive driver<br/>assigned alert"]

        S4["Arrive at school and<br/>view trip summary"]

    end

    subgraph System["System"]

        A1["Validate booking<br/>details"]

        D1{"Details valid?"}

        A2["Create booking<br/>status = AwaitingDriver"]

        A3["Alert available<br/>drivers"]

        D2{"Driver accepts?"}

        A4["Set status = Expired<br/>alert student"]

        A5["Assign driver<br/>status = DriverAssigned"]

        A6["Set status = InProgress<br/>share driver location"]

        A7["Set status = Completed<br/>save fare"]

    end

    subgraph Driver["Driver"]

        R1["Review booking<br/>request"]

        R2["Drive to pickup point"]

        R3["Start trip"]

        R4["Complete trip"]

    end

    S1 --> S2
    S2 --> A1

    A1 --> D1

    D1 -->|"details invalid"| S2
    D1 -->|"details valid"| A2

    A2 --> A3
    A3 --> R1

    R1 --> D2

    D2 -->|"declined or timed out"| A4
    D2 -->|"accepted"| A5

    A4 --> SystemEnd(["End: no driver"])

    A5 --> S3
    A5 --> R2

    R2 --> R3
    R3 --> A6

    A6 --> R4
    R4 --> A7

    A7 --> S4

    S4 --> End(["End: trip completed"])
