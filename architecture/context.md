# Diagram 1 – C4 System Context: SRJ Student Ride Booking

'''mermaid
flowchart TD
    Student["Student<br/>Person<br/>Off-campus SORSU student without a vehicle who needs a ride to school"]
    Driver["Tricycle Driver<br/>Person<br/>Local driver who accepts student booking"]
    Coordinator["Coordinator<br/>Person<br/>SRJ team member who manages drivers and reviews usage metrics"]

    SRJ["SRJ Ride Booking<br/>Software System<br/>Web app for booking rides to campus in advance with live trip updates"]

    Maps["Maps Provider<br/>External System<br/>Converts places to coordinates and returns distance and ETA"]
    Notify["Notification Provider<br/>External System<br/>Delivers email or SMS alerts about booking changes"]

    Student -->|"Books a ride, cancels it<br/>and follows the driver<br/>HTTPS"| SRJ
    Driver -->|"Sets availability, accepts<br/>rides and updates trip status<br/>HTTPS"| SRJ
    Coordinator -->|"Manages drivers and<br/>reviews booking metrics<br/>HTTPS"| SRJ

    SRJ -->|"Asks for distance and ETA<br/>HTTPS/JSON"| Maps
    SRJ -->|"Asks it to alert users<br/>about booking changes<br/>HTTPS/JSON"| Notify
