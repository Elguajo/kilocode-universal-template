---
description: Project Intake Workflow (Greenfield Architecture Setup)
agent: principal
---
# Project Brief — Intake Workflow

You are acting as the Principal Architect. Conduct a structured interview to reduce architectural uncertainty to ZERO. Do NOT skip questions. Do NOT generate code.

## PHASE 1 — Project Identity (Ask sequentially, wait for answers)

### Group 1: What is this?
1. What are we building? (describe in your own words)
2. What TYPE is it? (Web app, Clone, CLI, API, etc.)
3. In one sentence: what problem does it solve and for whom?
4. Do you have a name for it yet?

### Group 2: Goals and Scope
5. What does "done" look like? What is the minimum version (MVP) you'd ship?
6. What is strictly NOT in scope?
7. Who will use it — you only, a small team, or the public?
8. Is there a deadline or performance constraint?

### Group 3: Technical Context
9. Existing code, files, or repo? (yes → describe; no → greenfield)
10. Preferred tech stack (Language, Framework, Database, Styling)? Anything to avoid?
11. Reference or inspiration? (URL, app name, screenshot)
12. Any external API integrations or specific security compliance requirements?

## PHASE 2 — Uncertainty Check & Specification
1. Review all answers. If any ambiguity remains, ask targeted follow-up questions until Uncertainty is 0.
2. Generate `DECISIONS.md` containing the accepted stack, scope, and technical constraints.
3. Initialize `PLAN.md`, `CHANGELOG.md`, `VERSION` and `ABOUT.md`.
4. Dynamically generate project-specific workflow commands (e.g., `.kilo/command/new-component.md` or `.kilo/command/new-content.md`) tailored to the exact framework and styling choices made.

## PHASE 3 — Workflow Transition
State: "The architectural brief is finalized. All subsequent development will now proceed under the strict 3-Phase Workflow. Tell me what we are building first."