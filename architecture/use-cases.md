# Diagram 3 – Use Case Diagram: SRJ Student Ride Booking

```mermaid
flowchart LR

    Student["Student"]

    Driver["Tricycle Driver"]

    Coordinator["Coordinator"]

    subgraph SRJ["SRJ Ride Booking"]

        Track["Track driver location"]

        Book["Book a ride"]

        Cancel["Cancel booking"]

        Register["Register account"]

        Availability["Set availability"]

        Login["Log in"]

        Accept["Accept booking"]

        Update["Update trip status"]

        Manage["Manage drivers"]

        Metrics["View usage metrics"]

    end

    Maps["Maps Provider<br/>External System"]

    Notify["Notification Provider<br/>External System"]

    Student --- Track
    Student --- Book
    Student --- Cancel
    Student --- Register
    Student --- Login

    Driver --- Register
    Driver --- Login
    Driver --- Availability
    Driver --- Accept
    Driver --- Update

    Coordinator --- Login
    Coordinator --- Manage
    Coordinator --- Metrics

    Maps --- Track
    Maps --- Book

    Notify --- Accept
    Notify --- Update
