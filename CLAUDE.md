# AI Coding Starter Kit

> A flexible project template with an AI-powered development workflow. Supports multiple stacks (Next.js, WAT Automation, Web Design, Hybrid) with specialized skills for Init, Requirements, Architecture, Frontend, Backend, QA, Documentation, Deployment, and Reporting.

## Project Configuration

@docs/project-config.md

## Tech Stack

The tech stack is configured per project via `/init`. Default options:

- **Next.js Web App:** Next.js 16 (App Router), TypeScript, Tailwind CSS, shadcn/ui, Supabase, Vercel
- **WAT Automation:** Python tools, Markdown workflow SOPs, deterministic execution
- **Web Design:** HTML + Tailwind CSS, high-craft design, screenshot workflow
- **Hybrid:** Combines Next.js frontend with WAT backend automation

See `docs/project-config.md` for this project's specific stack choices.

## Project Structure

```
src/                  (Next.js projects)
  app/                Pages (Next.js App Router)
  components/
    ui/               shadcn/ui components (NEVER recreate these)
  hooks/              Custom React hooks
  lib/                Utilities (supabase.ts, utils.ts)
workflows/            (WAT projects) Markdown SOPs
tools/                (WAT projects) Python scripts
features/             Feature specifications (PROJ-X-name.md)
  INDEX.md            Feature status overview
docs/
  PRD.md              Product Requirements Document
  project-config.md   Project configuration (stack, skills, agents)
  production/         Production guides (Sentry, security, performance)
```

## Development Workflow

0. `/init` - **Configure project** (tech stack, skills, agents, integrations) — run this FIRST
1. `/requirements` - Create feature spec from idea
2. `/architecture` - Design tech architecture (PM-friendly, no code)
3. `/frontend` - Build UI components (shadcn/ui first!)
4. `/backend` - Build APIs, database, or WAT tools
5. `/qa` - Test against acceptance criteria + security audit
6. `/docs` - Generate documentation + visual diagrams in eraser.io (optional)
7. `/deploy` - Deploy to production
8. `/report` - Generate client-facing project report with HTML export (optional)

**Utility skills:**
- `/help` - See current project status and next steps
- `/init` (re-run) - Add skills, integrations, or change config
- `/skill-builder` - Create or optimize custom skills
- `/report status` - Quick project status report anytime

## Feature Tracking

All features tracked in `features/INDEX.md`. Every skill reads it at start and updates it when done. Feature specs live in `features/PROJ-X-name.md`.

## Key Conventions

- **Feature IDs:** PROJ-1, PROJ-2, etc. (sequential)
- **Commits:** `feat(PROJ-X): description`, `fix(PROJ-X): description`
- **Single Responsibility:** One feature per spec file
- **shadcn/ui first:** NEVER create custom versions of installed shadcn components
- **Human-in-the-loop:** All workflows have user approval checkpoints

## Build & Test Commands

```bash
npm run dev        # Development server (localhost:3000)
npm run build      # Production build
npm run lint       # ESLint
npm run start      # Production server
```

## Product Context

@docs/PRD.md

## Feature Overview

@features/INDEX.md
