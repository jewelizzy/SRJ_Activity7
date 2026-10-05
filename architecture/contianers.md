flowchart TB

    Student["Student"]
    Driver["Tricycle Driver"]
    Admin["Coordinator / Admin"]

    subgraph SRJ["SRJ Student Ride Booking System"]

        Browser["Next.js UI<br/>(Web Browser)"]

        API["Next.js API Route Handlers<br/>(Server)"]

        Database[("PostgreSQL<br/>Database")]

    end

    Maps["Maps Provider"]
    Notification["Notification Provider"]

    Student -->|"Uses"| Browser
    Driver -->|"Uses"| Browser
    Admin -->|"Uses"| Browser

    Browser -->|"HTTP Requests"| API

    API -->|"Read / Write data"| Database

    API -->|"Route / Location"| Maps
    API -->|"Notifications"| Notification
