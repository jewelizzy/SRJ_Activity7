# C4 System Context Diagram

```mermaid
C4Context
title System Context Diagram - SRJ Student Ride Booking System

Person(student, "Student", "Off-campus SORSU student who needs a ride to school.")
Person(driver, "Tricycle Driver", "Local driver who accepts student bookings.")
Person(coordinator, "Coordinator", "Manages drivers and reviews booking metrics.")

System(srj, "SRJ Ride Booking System", "Web application for booking rides to campus with live trip updates.")

System_Ext(maps, "Maps Provider", "Converts places to coordinates and provides distance and ETA.")
System_Ext(notification, "Notification Provider", "Delivers email or SMS alerts about booking changes.")

Rel(student, srj, "Books rides, cancels bookings, and follows rides", "HTTPS")
Rel(driver, srj, "Sets availability, accepts rides, and updates trip status", "HTTPS")
Rel(coordinator, srj, "Manages drivers and reviews booking metrics", "HTTPS")
Rel(srj, maps, "Requests distance and ETA", "HTTPS / JSON")
Rel(srj, notification, "Sends booking change notifications", "HTTPS / JSON")
