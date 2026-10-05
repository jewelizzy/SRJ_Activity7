flowchart LR
    Student["Student"]
    Driver["Tricycle Driver"]
    Admin["Coordinator / Admin"]

    System["SRJ Student Ride Booking System"]

    Maps["Maps Provider"]
    Notify["Notification Provider"]

    Student -->|"Books a ride"| System
    Student -->|"Views booking status"| System
    Driver -->|"Accepts / manages rides"| System
    Admin -->|"Manages system"| System

    System -->|"Gets route / location"| Maps
    System -->|"Sends notifications"| Notify
