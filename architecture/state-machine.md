# State-machine Diagram
```mermaid
stateDiagram-v2

    [*] --> AwaitingDriver : Student submits booking

    AwaitingDriver --> DriverAssigned : Driver accepts

    AwaitingDriver --> Cancelled : Student cancels

    AwaitingDriver --> Expired : No driver accepts within time limit

    DriverAssigned --> InProgress : Driver starts trip

    DriverAssigned --> Cancelled : Student or driver cancels

    InProgress --> Completed : Driver completes trip

    Completed --> [*]

    Cancelled --> [*]

    Expired --> [*]
