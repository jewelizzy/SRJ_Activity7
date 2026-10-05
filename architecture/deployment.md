```mermaid
flowchart LR

    subgraph StudentDevice["Student Device"]
        SB["Web Browser"]
    end

    subgraph DriverDevice["Driver Device"]
        DBR["Web Browser"]
    end

    subgraph Hosting["Web Hosting Platform"]
        APP["Execution Environment: Next.js Web/API<br/>Artifact: Student Transportation & Ride-Booking System"]
    end

    subgraph DataPlatform["Managed Database Platform"]
        PG["Execution Environment: PostgreSQL<br/>Artifact: MVP Database Schema"]
    end

    SB -->|"HTTPS"| APP
    SB -->|"WSS live updates"| APP
    DBR -->|"HTTPS"| APP
    DBR -->|"WSS live updates"| APP
    APP -->|"TLS-secured PostgreSQL protocol"| PG
```

## Key
- **Device nodes** = student/driver client hardware.
- **Execution environment** = runtime hosting the application/database.
- **Artifact** = deployed software/schema.
- **HTTPS/WSS/TLS** = communication/security protocols.

### Important
This diagram is intentionally titled **Provisional** because the team has not specified an actual hosting vendor, domain, IP address, or final infrastructure configuration in the previous activities.

