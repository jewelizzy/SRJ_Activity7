# Diagram 4 – Activity Diagram: Request a Ride Until Trip Ends

```mermaid
flowchart TB

    Start((Start))

    subgraph Student["Student"]

        S1["Open booking form"]
        S2["Enter pickup point,<br/>destination and scheduled time"]
        S3["Receive driver assignment"]
        S4["View trip progress"]
        S5["View completed trip"]

    end


    subgraph System["SRJ System"]

        A1["Validate booking details"]

        D1{"Details valid?"}

        A2["Create booking<br/>Status = AwaitingDriver"]

        A3["Find available drivers"]

        D2{"Driver accepts?"}

        A4["Set status = Expired"]

        A5["Assign driver<br/>Status = DriverAssigned"]

        A6["Update driver location"]

        A7["Set status = InProgress"]

        A8["Set status = Completed"]

    end


    subgraph Driver["Tricycle Driver"]

        D3["Receive booking request"]

        D4["Accept booking"]

        D5["Travel to pickup point"]

        D6["Start trip"]

        D7["Complete trip"]

    end


    Start --> S1
    S1 --> S2
    S2 --> A1
    A1 --> D1

    D1 -->|"No"| S2
    D1 -->|"Yes"| A2

    A2 --> A3
    A3 --> D3
    D3 --> D4
    D4 --> D2

    D2 -->|"No / Timeout"| A4
    A4 --> S5

    D2 -->|"Yes"| A5
    A5 --> S3
    S3 --> D5
    D5 --> D6
    D6 --> A7

    A7 --> A6
    A6 --> S4

    S4 --> D7
    D7 --> A8
    A8 --> S5

    S5 --> End((End))
