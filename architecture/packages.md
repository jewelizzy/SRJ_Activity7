# Packages Diagram
```mermaid
flowchart TB

    subgraph Presentation
        WebUI[Web UI]
        StudentUI[Student Interface]
        DriverUI[Driver Interface]
        AdminUI[Admin Interface]
    end

    subgraph Application
        Auth[Authentication]
        BookingService[Booking Service]
        UserService[User Service]
        NotificationService[Notification Service]
    end

    subgraph Domain
        UserModel[User]
        BookingModel[Booking]
        DriverModel[Driver]
        NotificationModel[Notification]
    end

    subgraph Infrastructure
        Database[(PostgreSQL)]
        MapsAdapter[Maps Adapter]
        NotifyAdapter[Notification Adapter]
    end

    StudentUI --> WebUI
    DriverUI --> WebUI
    AdminUI --> WebUI

    WebUI --> Auth
    WebUI --> BookingService
    WebUI --> UserService

    Auth --> UserModel
    UserService --> UserModel

    BookingService --> BookingModel
    BookingService --> DriverModel
    BookingService --> NotificationService

    NotificationService --> NotificationModel

    UserModel --> Database
    BookingModel --> Database
    DriverModel --> Database
    NotificationModel --> Database

    BookingService --> MapsAdapter
    NotificationService --> NotifyAdapter
