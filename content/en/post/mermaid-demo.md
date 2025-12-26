---
title: "Mermaid Diagram Guide"
date: 2024-01-16T10:00:00+08:00
draft: false
description: "A detailed guide to Hugo Fluid theme's Mermaid diagram features, including configuration, syntax, and rich examples."
categories:
  - Tutorial
tags:
  - Mermaid
  - Flowchart
  - Diagram
index_img: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&h=400&fit=crop"
mermaid: true
---

This article details Hugo Fluid theme's Mermaid diagram features.

<!--more-->

## Quick Start

### 1. Enable Mermaid

Enable Mermaid support in `params.toml`:

```toml
[post.mermaid]
enable = true
specific = true
[post.mermaid.options]
theme = "default"
```

### 2. Use in Articles

If `specific = true`, add to article Front-matter:

```yaml
---
title: "My Article"
mermaid: true
---
```

---

## Flowchart

### Basic Flowchart

```mermaid
graph TD
    A[Start] --> B{Condition}
    B -->|Yes| C[Action A]
    B -->|No| D[Action B]
    C --> E[End]
    D --> E
```

### Left to Right Flowchart

```mermaid
graph LR
    A[Input] --> B[Process]
    B --> C[Output]
```

---

## Sequence Diagram

```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server
    
    User->>Browser: Enter URL
    Browser->>Server: HTTP Request
    Server-->>Browser: HTTP Response
    Browser-->>User: Display Page
```

---

## Class Diagram

```mermaid
classDiagram
    class Animal {
        +String name
        +int age
        +makeSound()
    }
    
    class Dog {
        +String breed
        +bark()
    }
    
    class Cat {
        +String color
        +meow()
    }
    
    Animal <|-- Dog
    Animal <|-- Cat
```

---

## State Diagram

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Running: Start
    Running --> Paused: Pause
    Paused --> Running: Resume
    Running --> Stopped: Stop
    Stopped --> [*]
```

---

## Gantt Chart

```mermaid
gantt
    title Project Plan
    dateFormat  YYYY-MM-DD
    
    section Design
    Requirements    :a1, 2024-01-01, 7d
    UI Design       :a2, after a1, 5d
    
    section Development
    Frontend        :b1, after a2, 14d
    Backend         :b2, after a2, 14d
    
    section Testing
    Unit Tests      :c1, after b1, 5d
    Integration     :c2, after c1, 5d
```

---

## Pie Chart

```mermaid
pie title Programming Language Usage
    "JavaScript" : 35
    "Python" : 25
    "Java" : 20
    "Go" : 10
    "Other" : 10
```

---

## ER Diagram

```mermaid
erDiagram
    USER ||--o{ ORDER : places
    USER {
        int id PK
        string name
        string email
    }
    ORDER ||--|{ ORDER_ITEM : contains
    ORDER {
        int id PK
        date created_at
    }
```

---

## Git Graph

```mermaid
gitGraph
    commit id: "Initial commit"
    commit id: "Add feature A"
    branch develop
    checkout develop
    commit id: "Develop feature B"
    commit id: "Fix bug"
    checkout main
    merge develop id: "Merge develop"
    commit id: "Release v1.0"
```

---

## References

- [Mermaid Documentation](https://mermaid.js.org/)
- [Mermaid Live Editor](https://mermaid.live/)
