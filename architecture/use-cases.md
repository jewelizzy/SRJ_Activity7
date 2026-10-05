
---

# 3. `use-cases.md`

```markdown
# Diagram 3 – Use Case Diagram: SRJ Student Ride Booking

```mermaid
flowchart LR

    Student(["👤 Student"])
    Driver(["👤 Tricycle Driver"])
    Coordinator(["👤 Coordinator"])

    subgraph SRJ["SRJ Student Ride Booking System"]

        UC1(["Track driver location"])
        UC2(["Book a ride"])
        UC3(["Cancel booking"])
        UC4(["Register account"])
        UC5(["Set availability"])
        UC6(["Log in"])
        UC7(["Accept booking"])
        UC8(["Update trip status"])
        UC9(["Manage drivers"])
        UC10(["View usage metrics"])

    end


    Student --- UC1
    Student --- UC2
    Student --- UC3
    Student --- UC4
    Student --- UC6

    Driver --- UC5
    Driver --- UC6
    Driver --- UC7
    Driver --- UC8

    Coordinator --- UC9
    Coordinator --- UC10
