# C4 System Context Diagram

```mermaid
C4Context
title C4 System Context - SRJ Student Ride Booking System

Person(student, "Student", "Off-campus SORSU student who needs a ride to school.")
Person(driver, "Tricycle Driver", "Local driver who accepts student bookings.")
Person(coordinator, "Coordinator", "Manages drivers and reviews booking metrics.")

System(srj, "SRJ Ride Booking System", "Web application for booking rides to campus with live trip updates.")
System_Ext(maps, "Maps Provider", "Provides distance and ETA.")
System_Ext(notify, "Notification Provider", "Sends booking change alerts.")

Rel_D(student, srj, "Books, cancels, tracks", "HTTPS")
Rel_D(driver, srj, "Accepts and updates trips", "HTTPS")
Rel_D(coordinator, srj, "Manages drivers and metrics", "HTTPS")

Rel_L(srj, maps, "Gets distance and ETA", "HTTPS / JSON")
Rel_R(srj, notify, "Sends booking alerts", "HTTPS / JSON")

UpdateRelStyle(student, srj, $offsetX="-10", $offsetY="10")
UpdateRelStyle(driver, srj, $offsetX="0", $offsetY="10")
UpdateRelStyle(coordinator, srj, $offsetX="10", $offsetY="10")
UpdateRelStyle(srj, maps, $offsetX="-10", $offsetY="-5")
UpdateRelStyle(srj, notify, $offsetX="10", $offsetY="-5")

UpdateLayoutConfig($c4ShapeInRow="3", $c4BoundaryInRow="1")
