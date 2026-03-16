# Documentation Templates

## Feature Documentation Template

```markdown
# [Feature Name]

## Overview
_One paragraph: What this feature does and who it's for._

## How It Works
_Step-by-step user flow._

### For Users
1. [Step 1]
2. [Step 2]

## API Reference (if applicable)

### `POST /api/[endpoint]`
**Description:** [What it does]
**Auth:** Required
**Body:**
| Field | Type | Required | Description |
|-------|------|----------|-------------|

**Response:** `201 Created`

## Data Model
_Reference ER diagram or describe tables._

## Configuration
_Environment variables, settings needed._

## Diagrams
- Architecture: [eraser.io link]
- Data Flow: [eraser.io link]
```

---

## Architecture Overview Template

```markdown
# Architecture Overview

## System Design
_High-level description of the system architecture._

## Components

### Frontend
- **Technology:** [e.g., Next.js + React]
- **Hosting:** [e.g., Vercel]
- **Key Features:** [list]

### Backend
- **Technology:** [e.g., Supabase / WAT Tools]
- **Database:** [e.g., PostgreSQL]
- **Key Services:** [list]

### External Services
- [Service 1]: [purpose]
- [Service 2]: [purpose]

## Data Flow
_Description of how data moves through the system._

## Security
- Authentication: [method]
- Authorization: [method]
- Data Protection: [approach]

## Diagrams
- System Architecture: [eraser.io link]
- ER Diagram: [eraser.io link]
- Deployment Architecture: [eraser.io link]

## Architecture Decisions
| Decision | Choice | Rationale |
|----------|--------|-----------|
```

---

## Getting Started Template

```markdown
# Getting Started

## Prerequisites
- Node.js [version]
- npm/yarn
- [other requirements]

## Setup
1. Clone the repository
2. Install dependencies: `npm install`
3. Copy `.env.local.example` to `.env.local` and fill in values
4. Start development server: `npm run dev`

## Environment Variables
| Variable | Description | Required |
|----------|-------------|----------|

## Project Structure
[Tree of key directories and files]

## Development Workflow
1. `/requirements` — Define features
2. `/architecture` — Design
3. `/frontend` — Build UI
4. `/backend` — Build APIs
5. `/qa` — Test
6. `/docs` — Document
7. `/deploy` — Ship

## Useful Commands
- `npm run dev` — Development server
- `npm run build` — Production build
- `npm run lint` — Lint code
```
