---
description: Run a full project health check, architecture audit, and code quality review
agent: principal
---
# Principal Engineer Audit Workflow

Perform a ruthless, high-level codebase and product audit.

## Step 1: Read Project State
- Read `VERSION`, `PLAN.md`, and `DECISIONS.md`.

## Step 2: Dynamic Path Discovery
Do NOT assume directory structures. Use `bash` (`ls -R`, `find`) or `glob` to locate:
1. Source directories (`src`, `app`, `lib`).
2. UI Components directories.
3. Content/Pages directories.

## Step 3: Execute Strict Checks
Run the following checks:

### Check 1: Code & Architecture Quality
- [ ] No `any` types (if using TypeScript).
- [ ] No raw `console.log`, `console.warn` in production source code.
- [ ] No dead code.

### Check 2: Security & Environment
- [ ] No `.env` files tracked in Git.
- [ ] No hardcoded API keys, tokens, or third-party service URLs in source files.

## Step 4: Generate Output
Print the report in the following strict format:

## Principal Audit Report — v[VERSION]

### Critical Violations (Must Fix immediately)
- [List specific files and lines violating Security or Code Quality rules]

### Warnings & Debt
- [List structural debt]

### Passed Checks
- [List systems that correctly adhere to standards]

## Step 5: Update Tracking
- Add unresolved issues to `PLAN.md` under `## Known Issues` with a `[!]` marker.
- Inform the user: "Audit complete. Fix critical violations before proceeding."