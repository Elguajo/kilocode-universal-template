---
description: Tag and release a new version
agent: principal
---
# Release Workflow

Execute the release process step-by-step.

## Step 1 — Read current state
- `VERSION` — current version number
- `CHANGELOG.md` — check what is under `[Unreleased]`
- `PLAN.md` — check which tasks are done

If `[Unreleased]` section is empty, tell the user: "Nothing to release — no unreleased changes found in CHANGELOG.md." and stop.

## Step 2 — Ask for version bump type
Ask the user:
> "Current version is X.Y.Z. What kind of release is this?
> - **patch** (X.Y.**Z+1**) — bug fixes only
> - **minor** (X.**Y+1**.0) — new features or pages
> - **major** (**X+1**.0.0) — public launch"

## Step 3 — Calculate new version
Based on the answer, compute the new version number.

## Step 4 — Update CHANGELOG.md
1. Replace `## [Unreleased]` header with `## [NEW_VERSION] — YYYY-MM-DD` (today's date)
2. Add a new empty `## [Unreleased]` section at the top.

## Step 5 — Update VERSION file
Overwrite `VERSION` with the new version number.

## Step 6 — Update PLAN.md
Update the `Current version:` line in the Status section of `PLAN.md` to the new version.

## Step 7 — Confirm to user
Show the user a summary of the release and suggest committing the changes.