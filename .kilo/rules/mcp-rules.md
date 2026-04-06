# MCP Server Usage Rules

## MANDATORY BEHAVIOR

You have access to MCP servers. You MUST use them as specified below.
Do NOT rely on training data when current documentation or verification is available.

---

## context7 — Live Documentation

### TRIGGER CONDITIONS
- Writing or modifying any framework or library file.
- Configuring integrations, adapters, or plugins.
- Any question about component props, built-in methods, or API signatures.

### PROCEDURE
1. Call `resolve-library-id` with the library name.
2. Call `get-library-docs` with the resolved ID and a specific query.
3. Use the returned documentation as ground truth — **override any conflicting assumption from training data**.

---

## sequential-thinking — Structured Reasoning

### TRIGGER CONDITIONS (use BEFORE implementation)
- Task requires modifying 3 or more files.
- Designing a new page, layout, or multi-component feature.
- Debugging a non-obvious issue (cause not immediately clear).
- Making an architectural decision (anything recorded in `DECISIONS.md`).

### PROCEDURE
1. Call `sequentialthinking` with the full task description BEFORE writing any code.
2. Receive a structured step-by-step plan.
3. Present the plan to the user — wait for approval.
4. Implement ONLY after the plan is approved.

---

## playwright — Browser Verification

### TRIGGER CONDITIONS
- After creating or significantly modifying any page or component.
- Before executing `/release` workflow.
- When a page renders unexpectedly or a layout breaks.
- After integrating any third-party script — verify it loads without console errors.

### PROCEDURE
1. Confirm dev server is running.
2. Call `browser_navigate` with the target URL.
3. Call `browser_snapshot` for layout and content verification.
4. Call `browser_console_messages` to check for JS errors.
5. If errors found — fix before proceeding.

---

## github — Repository Search

### TRIGGER CONDITIONS
- Need a real-world implementation example not covered by context7.
- Verifying latest published version of a package before installing.

### PROCEDURE
- Use `search_repositories` or `get_file_contents` to find examples.
- Do NOT push commits or modify any repository directly via this tool.

---

## EXECUTION ORDER (non-trivial tasks)

1. `sequential-thinking` → produce and present implementation plan.
2. `context7` → fetch current docs for each library in the plan.
3. **implement** → write code based on plan + docs (one step at a time).
4. `playwright` → verify result in browser.
5. **update tracking** → `PLAN.md` (mark done) + `CHANGELOG.md` (add entry).

## OVERRIDE RULE

If training data conflicts with context7 output — context7 wins.
If implementation looks correct but playwright shows errors — fix the errors, do not rationalize them away.