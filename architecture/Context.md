# C4 System Context Diagram

```mermaid
C4Context

title C4 System Context - SRJ Student Ride Booking System

Person(student, "Student", "Off-campus SORSU student who needs a ride to school.")
Person(driver, "Tricycle Driver", "Local driver who accepts student bookings.")
Person(coordinator, "Coordinator", "Manages drivers and reviews booking metrics.")

System(srj, "SRJ Ride Booking System", "Web application for booking rides to campus with live trip updates.")

System_Ext(maps, "Maps Provider", "Provides distance and ETA.")
System_Ext(notify, "Notification Provider", "Sends booking alerts.")

Rel_D(student, srj, "Book / Track")
Rel_D(driver, srj, "Accept / Update")
Rel_D(coordinator, srj, "Manage")

Rel_L(srj, maps, "Distance / ETA")
Rel_R(srj, notify, "Alerts")

UpdateLayoutConfig($c4ShapeInRow="3", $c4BoundaryInRow="1")

UpdateRelStyle(student, srj, $offsetX="-15", $offsetY="5")
UpdateRelStyle(driver, srj, $offsetX="0", $offsetY="5")
UpdateRelStyle(coordinator, srj, $offsetX="15", $offsetY="5")

UpdateRelStyle(srj, maps, $offsetX="-15", $offsetY="0")
UpdateRelStyle(srj, notify, $offsetX="15", $offsetY="0")
