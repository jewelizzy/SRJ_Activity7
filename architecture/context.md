# Diagram 1 – C4 System Context: SRJ Student Ride Booking

'''mermaid
flowchart TD
    Student["Student"]
    Driver["Tricycle Driver"]
    Coordinator["Coordinator"]
    SRJ["SRJ Student Ride Booking System"]
    Maps["Maps Provider"]
    Notify["Notofication Provider"]

    Student -->|"Books a ride"| SRJ
    Driver -->|"Accept rides"| SRJ
    Coordinator -->|"Manages drivers"] SRJ
    SRJ -->|Distance and ETA"| Maps
    SRJ -->|"Booking alerts"| Notify
