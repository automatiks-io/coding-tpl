---
paths:
  - "workflows/**"
  - "tools/**"
  - ".tmp/**"
---

# WAT Framework Rules

> Workflows, Agents, Tools — separates probabilistic AI reasoning from deterministic code execution.

## Architecture

**Layer 1: Workflows** — Markdown SOPs in `workflows/`
- Each workflow defines: objective, required inputs, tools to use, expected outputs, edge cases
- Written in plain language like a team briefing

**Layer 2: Agents** — AI orchestration (your role)
- Read the relevant workflow, run tools in correct sequence, handle failures, ask clarifying questions
- Never try to do everything directly — delegate execution to tools

**Layer 3: Tools** — Python scripts in `tools/`
- API calls, data transformations, file operations, database queries
- Deterministic, testable, fast
- Credentials stored in `.env` (never elsewhere)

## Operating Rules

### 1. Look for existing tools first
Before building anything new, check `tools/` for what your workflow requires. Only create new scripts when nothing exists.

### 2. Learn and adapt when things fail
- Read the full error message and trace
- Fix the script and retest
- If it uses paid API calls or credits, check with the user before re-running
- Document what you learned in the workflow

### 3. Keep workflows current
- Update workflows when you find better methods, discover constraints, or hit recurring issues
- Do NOT create or overwrite workflows without asking unless explicitly told to
- Workflows are instructions — preserve and refine them, don't discard after one use

## Self-Improvement Loop
1. Identify what broke
2. Fix the tool
3. Verify the fix works
4. Update the workflow with the new approach
5. Move on with a more robust system

## File Conventions
- `workflows/` — Markdown SOPs (one per process)
- `tools/` — Python scripts (one per discrete task)
- `.tmp/` — Temporary/intermediate files (disposable, regenerated as needed)
- `.env` — API keys and environment variables
- Final deliverables go to cloud services, not local files

## Tool Development Standards
- Each script must handle errors gracefully with clear messages
- Document required environment variables at top of each script
- Include usage examples in script docstrings
- Keep scripts focused on one task (Single Responsibility)
