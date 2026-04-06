---
name: spec-writer
description: Generates or updates the technical specification document during Phase 2 of the Principal Workflow.
---

# Skill: Technical Specification Writer

## Context
Use this skill when you are in **Phase 2 (Planning)** of the `principal-workflow.md` process, right after receiving answers to your Discovery questions.

## Instructions
1. Synthesize the user's answers and the existing architectural rules.
2. Create or overwrite the file `.kilo/specs/current-task.md`.
3. The specification MUST strictly include:
   - **Task Objective:** Clear definition of "done".
   - **Architectural Impact:** Which layers (UI, State, DB) are affected.
   - **File Mutation Plan:** Exact paths of files to be created/edited/deleted.
   - **Error Handling Strategy:** How potential network/I/O/DB failures will be handled.
   - **Security Vectors:** Validation requirements for inputs.
4. Output the content of the plan in the chat and ask for explicit approval to transition into **Phase 3: Execution**.