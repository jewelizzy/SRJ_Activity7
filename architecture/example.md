graph TD
    classDef person fill:#08427b,color:#fff,stroke:#073b6f,stroke-width:2px;
    classDef system fill:#1168bd,color:#fff,stroke:#0e5296,stroke-width:2px;
    classDef external fill:#999999,color:#fff,stroke:#666666,stroke-width:2px;

    Student["<b>Student</b><br/>[Person]<br/>Off-campus SORSU student without a vehicle who needs a ride to school"]:::person
    Driver["<b>Tricycle Driver</b><br/>[Person]<br/>Local driver who accepts student bookings"]:::person
    Admin["<b>Coordinator</b><br/>[Person]<br/>SRJ team member who manages drivers and reviews usage metrics"]:::person

    SRJ["<b>SRJ Ride Booking</b><br/>[Software System]<br/>Web app for booking rides to campus in advance with live trip updates"]:::system

    Maps["<b>Maps Provider</b><br/>[External System]<br/>Converts places to coordinates and returns distance and ETA"]:::external
    Notif["<b>Notification Provider</b><br/>[External System]<br/>Delivers email or SMS alerts about booking changes"]:::external

    Student -->|Books a ride, cancels it and follows the driver<br/>[HTTPS]| SRJ
    Driver -->|Sets availability, accepts rides and updates trip status<br/>[HTTPS]| SRJ
    Admin -->|Manages drivers and reviews booking metrics<br/>[HTTPS]| SRJ

    SRJ -->|Asks for distance and ETA of a trip<br/>[HTTPS/JSON]| Maps
    SRJ -->|Asks it to alert users about booking changes<br/>[HTTPS/JSON]| Notif
