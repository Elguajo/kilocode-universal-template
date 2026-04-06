---
description: Start development of a new feature using the Principal 3-Phase Workflow
agent: principal
---
# Task Initialization Workflow

Formally start a new implementation task.

## Action
1. Immediately acknowledge the command.
2. Output the following exact message:
   > "Task initialized. I am transitioning into Phase 1: Discovery. Analyzing the context..."
3. Automatically begin Phase 1 (Discovery) of the Principal Workflow by scanning the repository.
4. Output a numbered list of highly technical, clarifying questions regarding the new feature.
5. Stop and wait for the user's response. Do NOT provide code.