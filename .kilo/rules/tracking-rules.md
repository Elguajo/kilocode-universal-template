# Project Tracking Rules

## Required Files
These files MUST exist in the project root. If any are missing, create them BEFORE doing any other work.

---

## PLAN.md — Rules

### Format
```md
# Project Plan

## Status
Current version: 0.1.0
Last updated: YYYY-MM-DD

## Phase 1 — MVP (in progress)
- [ ] Task one
- [-] Task two (in progress)
- [x] Task three (done)

## Backlog
- [ ] Nice-to-have feature

## Known Issues
- None
```

### Status markers
- `[ ]` not started
- `[-]` in progress
- `[x]` done and approved
- `[!]` blocked — add one-line reason inline

### Rules
- Read `PLAN.md` BEFORE starting any task.
- Mark tasks `[-]` when starting, `[x]` when user approves the result.
- Never delete completed tasks — history must stay.
- Update "Last updated" date every time the file is touched.

---

## CHANGELOG.md — Rules

### Format
```md
# Changelog

## [Unreleased]
### Added
- New feature or file
### Fixed
- Bug fix description

---

## [0.1.0] — YYYY-MM-DD
### Added
- Initial project scaffold
```

### Change types — use exactly these labels
- `Added` — new feature, file, or component
- `Changed` — modification to existing functionality
- `Fixed` — bug fix
- `Removed` — deleted feature or file
- `Security` — security-related fix

### Rules
- Add entry under `[Unreleased]` AFTER every completed and approved step.
- New changes go to the TOP of the Unreleased section.
- Never edit past version blocks.
- One bullet = one logical change, not one file edit.

---

## VERSION — Rules
Semantic Versioning: `MAJOR.MINOR.PATCH`
- File contains exactly one line — the version number, no prefix, no quotes.
- Update only via `/release.md` workflow.

---

## DECISIONS.md — Rules

### Format
```md
## YYYY-MM-DD — Decision title
Rationale: one sentence explaining why this choice was made over alternatives.
```
### Rules
- Add entry whenever an architectural or tooling decision is made.
- Include what was rejected and why. Never delete entries.