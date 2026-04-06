# Step-by-Step Execution Rules

## CORE PRINCIPLE

Do ONE thing at a time. Stop. Report. Wait for approval. Then continue.

Never chain multiple independent tasks in a single response.
Never assume that completing step N means you should immediately start step N+1.

---

## WHAT COUNTS AS ONE STEP

One step = one of the following:
- Creating a single file
- Editing a single file
- Running a single terminal command
- Making a single architectural decision

If a task naturally involves multiple files that are tightly coupled and cannot function independently — they may be grouped into one step. Everything else is a separate step.

---

## REQUIRED FORMAT AFTER EVERY STEP

After completing each step, output this exact structure:

```md
## Done

**What I did:**
[One or two sentences describing what was created or changed]

**File(s) affected:**
- path/to/file.ext — [created / modified / deleted]

**Current task log:**
- [x] Step 1 — description
- [x] Step 2 — description
- [-] Step 3 — description (just completed)
- [ ] Step 4 — description

**Next step:**
[Clear description of what step 4 will do]

Shall I continue?
```

---

## GO-AHEAD SIGNALS

- **Accepted:** "yes", "continue", "go", "ok", "next"
- **Skip:** "skip" → skip current step, mark `[!] skipped`, move to next
- **Stop:** "stop" → halt, summarize what was completed so far
- **Correction:** Any correction → apply to current step first, then ask to continue

- NEVER proceed without explicit go-ahead.
- NEVER say "I'll now do steps 1 through 4" and execute all of them.