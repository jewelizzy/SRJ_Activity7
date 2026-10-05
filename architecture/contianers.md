# Diagram 2 – C4 Container: SRJ Student Ride Booking (MVP)

```mermaid
flowchart TB

    Student["Student<br/>Person<br/>Books rides"]

    Driver["Tricycle Driver<br/>Person<br/>Accepts rides and updates trips"]

    Coordinator["Coordinator<br/>Person<br/>Manages drivers and reviews metrics"]

    subgraph SRJ["SRJ Ride Booking"]

        UI["Web App (UI)<br/><br/>Next.js / React<br/>Runs in the browser<br/><br/>Booking, driver and coordinator pages"]

        API["API<br/><br/>Next.js Route Handlers<br/>Node.js runtime<br/><br/>Booking rules, matching and trip status"]

        DB[("Database<br/><br/>PostgreSQL<br/><br/>Users, bookings,<br/>location updates and notifications")]

    end

    Maps["Maps Provider<br/>External System<br/><br/>Distance and ETA"]

    Notification["Notification Provider<br/>External System<br/><br/>Email or SMS alerts"]


    Student -->|"HTTPS"| UI
    Driver -->|"HTTPS"| UI
    Coordinator -->|"HTTPS"| UI

    UI -->|"HTTPS / JSON<br/>Polling"| API

    API -->|"SQL over TLS"| DB

    API -->|"HTTPS / JSON"| Maps
    API -->|"HTTPS / JSON"| Notification
