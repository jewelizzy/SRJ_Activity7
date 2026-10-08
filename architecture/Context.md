# C4 System Context Diagram

```mermaid
C4Context

title C4 System Context Diagram - SRJ Student Ride Booking System

Person(student, "Student", "Off-campus SORSU student who needs a ride to school.")
Person(driver, "Tricycle Driver", "Local driver who accepts student bookings.")
Person(coordinator, "Coordinator", "Manages drivers and reviews booking metrics.")

System_Ext(maps, "Maps Provider", "Provides distance and ETA.")
System(srj, "SRJ Ride Booking System", "Web application for booking rides to campus with live trip updates.")
System_Ext(notification, "Notification Provider", "Sends email or SMS alerts.")

Rel_D(student, srj, "Books, cancels, tracks", "HTTPS")
Rel_D(driver, srj, "Accepts and updates trips", "HTTPS")
Rel_D(coordinator, srj, "Manages drivers and metrics", "HTTPS")

Rel_L(srj, maps, "Gets distance and ETA", "HTTPS / JSON")
Rel_R(srj, notification, "Sends booking alerts", "HTTPS / JSON")

UpdateRelStyle(student, srj, $offsetX="-20", $offsetY="10")
UpdateRelStyle(driver, srj, $offsetX="0", $offsetY="15")
UpdateRelStyle(coordinator, srj, $offsetX="20", $offsetY="10")

UpdateRelStyle(srj, maps, $offsetX="-10", $offsetY="-10")
UpdateRelStyle(srj, notification, $offsetX="10", $offsetY="-10")

UpdateLayoutConfig($c4ShapeInRow="3", $c4BoundaryInRow="1")
