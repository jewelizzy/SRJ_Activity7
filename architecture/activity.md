````md
# Activity Diagram
## SRJ Student Ride Booking

```mermaid
flowchart TD

    Start([Start])

    A["Student logs in"]
    B["Student submits ride request"]
    C["System validates booking details"]
    D{"Booking details valid?"}

    E["System searches for available driver"]
    F["System notifies available driver"]
    G{"Driver accepts booking?"}

    H["System searches for another driver"]
    I["System confirms booking"]
    J["Driver goes to pickup location"]
    K["Driver picks up student"]
    L["Ride is in progress"]
    M["Driver completes ride"]
    N["Student pays fare in cash"]
    O["System updates booking status"]

    End([End])

    Start --> A
    A --> B
    B --> C
    C --> D

    D -- "No" --> B
    D -- "Yes" --> E

    E --> F
    F --> G

    G -- "No" --> H
    H --> E

    G -- "Yes" --> I
    I --> J
    J --> K
    K --> L
    L --> M
    M --> N
    N --> O
    O --> End
````

### Activity Flow

1. Student logs in.
2. Student submits a ride request.
3. System validates the booking details.
4. System searches for an available driver.
5. Available driver receives the request.
6. Driver accepts or declines the booking.
7. If declined, the system searches for another driver.
8. If accepted, the system confirms the booking.
9. Driver goes to the pickup location.
10. Driver picks up the student.
11. The ride is in progress.
12. Driver completes the ride.
13. Student pays the fare in cash.
14. System updates the booking status.

```

This corresponds to **Diagram 4 – Activity (swimlanes)** in your architecture document, whose stated purpose is to show branches in the core workflow, including the case where **no driver accepts**.

Kapag okay na, sabihin mo lang **“next”** → `sequence.md`.
```
