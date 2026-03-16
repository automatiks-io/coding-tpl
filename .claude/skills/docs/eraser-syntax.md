# eraser.io DSL Syntax Reference

Quick reference for generating diagrams programmatically. Full docs: https://docs.eraser.io/docs/diagram-as-code

---

## Flowcharts

```eraser
// Nodes
Start [shape: oval]
Decision [shape: diamond]
Process [shape: rectangle]
End [shape: oval]

// Connections
Start > Process: step 1
Process > Decision: check
Decision > End: yes
Decision > Process: no, retry
```

**Node Properties:**
- `shape`: oval, rectangle, diamond, cylinder, hexagon, parallelogram
- `color`: red, blue, green, yellow, orange, purple, gray
- `icon`: aws-ec2, gcp-cloud-run, k8s-pod, etc.

**Groups:**
```eraser
Backend {
  API [shape: rectangle]
  Database [shape: cylinder]
  API > Database
}
```

---

## Sequence Diagrams

```eraser
// Entities (columns)
User
Frontend
API
Database

// Messages
User > Frontend: Click button
Frontend > API: POST /api/tasks
API > Database: INSERT INTO tasks
Database > API: Success
API > Frontend: 201 Created
Frontend > User: Show confirmation
```

**Control Flow:**
```eraser
// Conditional
alt [condition: user authenticated] {
  Frontend > API: Fetch data
}
else {
  Frontend > User: Show login
}

// Parallel
par {
  API > ServiceA: Request
  API > ServiceB: Request
}
```

---

## Entity Relationship Diagrams

```eraser
// Tables
users [icon: user] {
  id uuid pk
  email varchar
  name varchar
  created_at timestamp
}

tasks [icon: document] {
  id uuid pk
  user_id uuid fk
  title varchar
  status enum
  created_at timestamp
}

// Relationships
users.id <> tasks.user_id
```

**Relationship Types:**
- `<>` — one-to-many
- `<->` — many-to-many
- `--` — one-to-one

---

## Cloud Architecture Diagrams

```eraser
// Services with icons
Vercel [icon: vercel]
Supabase [icon: supabase]
CloudFlare [icon: cloudflare]

// Groups
Frontend {
  NextJS [icon: nextjs]
  CDN [icon: cloudflare]
}

Backend {
  API [icon: vercel]
  DB [icon: postgresql]
  Auth [icon: lock]
}

// Connections
User > CloudFlare > NextJS
NextJS > API
API > DB
API > Auth
```

**Common Icons:** aws-*, gcp-*, azure-*, vercel, supabase, nextjs, postgresql, redis, docker, k8s-*, github, slack

---

## BPMN Diagrams

```eraser
// Events
Start [shape: oval, color: green]
End [shape: oval, color: red]

// Tasks
Review [shape: rectangle]
Approve [shape: rectangle]
Reject [shape: rectangle]

// Gateways
Check [shape: diamond]

// Flow
Start > Review > Check
Check > Approve: approved
Check > Reject: rejected
Approve > End
Reject > Review: revise
```

---

## Tips for Documentation Diagrams

1. **System Architecture**: Use cloud architecture style with groups for layers (Frontend, Backend, External Services)
2. **Data Model**: Use ER diagram with all tables, PKs, FKs, and relationships
3. **User Flows**: Use sequence diagrams showing User → UI → API → DB interactions
4. **Deployment**: Use cloud architecture with hosting platform icons
5. **Processes (WAT)**: Use flowcharts with decision diamonds for branching logic
