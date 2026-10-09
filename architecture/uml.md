# UML Component Diagram ( API Route)

```mermaid
flowchart TB
    Routes["API Route Handlers"]

        AUTH["Auth Service"]
        BOOK["Booking Service"]
        TRACK["Tracking Service"]

        IAUTH(["IAuthService"])
        IBOOK(["IBookingService"])
        ITRACK(["ITrackingService"])

        USERREPO["User Repository"]
        BOOKREPO["Booking Repository"]
        LOCREPO["Location Repository"]

        IUSER(["IUserRepository"])
        IBOOKREPO(["IBookingRepository"])
        ILOC(["ILocationRepository"])

        MAPADAPTER["Maps Adapter"]
        NOTIFYADAPTER["Notification Adapter"]

        IMAPS(["IMapsProvider"])
        INOTIFY(["INotifier"])
        IDB(["IDatabase"])

        AUTH --- IAUTH
        BOOK --- IBOOK
        TRACK --- ITRACK

        USERREPO --- IUSER
        BOOKREPO --- IBOOKREPO
        LOCREPO --- ILOC

        MAPADAPTER --- IMAPS
        NOTIFYADAPTER --- INOTIFY

        RH -.->|requires| IAUTH
        RH -.->|requires| IBOOK
        RH -.->|requires| ITRACK

        AUTH -.-> IUSER

        BOOK -.-> IBOOKREPO
        BOOK -.-> IUSER
        BOOK -.-> IMAPS
        BOOK -.-> INOTIFY

        TRACK -.-> ILOC
        TRACK -.-> IBOOKREPO

        USERREPO -.-> IDB
        BOOKREPO -.-> IDB
        LOCREPO -.-> IDB
    end

    DB[("PostgreSQL Database")]
    MAPS["Maps Provider<br/>External System"]
    NOTIFY["Notification Provider<br/>External System"]

    IDB -.->|SQL| DB
    IMAPS -.->|HTTPS / JSON| MAPS
    INOTIFY -.->|HTTPS / JSON| NOTIFY

    classDef component fill:#e8f1fb,stroke:#245b91,stroke-width:1.5px,color:#102a43
    classDef interface fill:#fff4d6,stroke:#9a6700,stroke-width:1.5px,color:#553900
    classDef external fill:#e6f4ea,stroke:#287d45,stroke-width:1.5px,color:#153d24

    class RH,AUTH,BOOK,TRACK,USERREPO,BOOKREPO,LOCREPO,MAPADAPTER,NOTIFYADAPTER component
    class IAUTH,IBOOK,ITRACK,IUSER,IBOOKREPO,ILOC,IMAPS,INOTIFY,IDB interface
    class DB,MAPS,NOTIFY external
