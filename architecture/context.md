# Diagram 1 – C4 System Context: SRJ Student Ride Booking (MVP)

```mermaid
flowchart TB
    Student["Student<br/>Person"]
    Driver["Tricycle Driver<br/>Person"]
    Admin["Coordinator<br/>Person"]

    SRJ["SRJ Ride Booking<br/>Software System"]

    Maps["Maps Provider<br/>External System"]
    Notify["Notification Provider<br/>External System"]

    Student --> SRJ
    Driver --> SRJ
    Admin --> SRJ

    SRJ --> Maps
    SRJ --> Notify
