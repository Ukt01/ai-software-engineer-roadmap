# Stage 0 — Architecture & Workflow Diagrams

Visual models depicting core concepts from Stage 0: REST API request execution, Git state transitions, Object-Oriented memory instantiation, and SQL Relational models.

---

## 1. REST API Request / Response Lifecycle

This diagram demonstrates how data moves between a client (Postman/Browser), an API server, and a relational database during HTTP requests.

```mermaid
sequenceDiagram
    autonumber
    actor Client as Client App / Postman
    participant Controller as REST API Controller
    participant Service as OOP Business Service
    participant DB as SQL Database

    Client->>Controller: POST /api/users (JSON Body)
    Controller->>Controller: Validate Request Format & Headers
    Controller->>Service: CreateUser(userData)
    Service->>Service: Instantiate User Object & Apply Rules
    Service->>DB: INSERT INTO Users (Name, Email)...
    DB-->>Service: Success (ID: 101 generated)
    Service-->>Controller: Return User Entity (ID: 101)
    Controller-->>Client: 201 Created (JSON Response Payload)
```

---

## 2. Git State & Lifecycle Progression

This diagram illustrates how files move through Git environments from unstaged local edits to remote cloud repositories.

```mermaid
flowchart LR
    subgraph Local Workspace
        WD[Working Directory<br/><i>Unstaged Changes</i>]
        SA[Staging Area / Index<br/><i>Staged via 'git add'</i>]
        LR[Local Repository<br/><i>Committed via 'git commit'</i>]
    end

    subgraph Remote Host
        RR[Remote Repository<br/><i>GitHub / GitLab via 'git push'</i>]
    end

    WD -- "git add" --> SA
    SA -- "git commit" --> LR
    LR -- "git push" --> RR
    RR -- "git fetch / git pull" --> Local Workspace
```

---

## 3. OOP Class Blueprint vs. Instance Memory Model

This diagram highlights how a single class definition acts as a blueprint to spawn distinct object instances in system heap memory.

```mermaid
classDiagram
    class CarBlueprint {
        +String Brand
        +String Model
        +Int Speed
        +Accelerate(int amount) Void
        +Brake() Void
    }

    class CarInstance_1 {
        Brand = "Tesla"
        Model = "Model 3"
        Speed = 65
    }

    class CarInstance_2 {
        Brand = "Ford"
        Model = "Mustang"
        Speed = 80
    }

    CarBlueprint <|-- CarInstance_1 : Instantiates in Memory
    CarBlueprint <|-- CarInstance_2 : Instantiates in Memory
```

---

## 4. Database CRUD & Foreign Key Relationship Model

This entity-relationship structure shows how SQL tables enforce foreign key integrity and execute JOIN operations.

```mermaid
erDiagram
    USERS ||--o{ ORDERS : places
    USERS {
        int Id PK
        string Name
        string Email
        datetime CreatedAt
    }
    ORDERS {
        int Id PK
        int UserId FK
        decimal TotalAmount
        string Status
    }
```
