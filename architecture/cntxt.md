# Diagram 1 - C4 System Context

```mermaid
flowchart TB

    Person(student, "Student", "Off-campus SORSU student who needs a ride to school.")
    Person(driver, "Tricycle Driver", "Local driver who accepts student bookings.")
    Person(coordinator, "Coordinator", "Manages drivers and reviews booking metrics.")

    SRJ["SRJ Ride Booking<br/>Software System<br/>Web app for booking rides to campus with live trip updates"]

    Maps["Maps Provider<br/>External System<br/>Converts places to coordinates and returns distance and ETA"]

    Notify["Notification Provider<br/>External System<br/>Delivers email or SMS alerts about booking changes"]

    Student -->|"Books a ride, cancels it, and follows the ride<br/>HTTPS"| SRJ
    Driver -->|"Sets availability, accepts rides,<br/>and updates trip status<br/>HTTPS"| SRJ
    Coordinator -->|"Manages drivers and reviews<br/>booking metrics<br/>HTTPS"| SRJ

    SRJ -->|"Asks for distance and ETA of a trip<br/>HTTPS / JSON"| Maps
    SRJ -->|"Asks to alert users about booking changes<br/>HTTPS / JSON"| Notify
```
