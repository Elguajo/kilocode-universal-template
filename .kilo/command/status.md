---
description: Project progress dashboard
agent: principal
---
# Status Workflow

Get a quick overview of where the project stands.

## Step 1 — Read project files
- `VERSION`
- `PLAN.md`
- `CHANGELOG.md` (only the `[Unreleased]` section)

## Step 2 — Count task stats from PLAN.md
Count all tasks by status:
- `[x]` = done
- `[-]` = in progress
- `[!]` = blocked
- `[ ]` = todo

## Step 3 — Report to user
Output a clean status report in this format:

## Project Status

Version: X.Y.Z

### Progress
Done:        [N] tasks  ████████████░░░░  [X]%
In progress: [N] tasks
Blocked:     [N] tasks
Todo:        [N] tasks

### Currently in progress
- [Task names]

### Blocked
[Tasks or None]

### Unreleased changes (will go into next version)
- [List from CHANGELOG]

### Up next (first todo tasks)
- [Tasks from PLAN.md]

### Suggested next version bump
[patch/minor/major based on unreleased changes]