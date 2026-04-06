# Kilo Code: Principal Engineer Template Guide

This guide explains how to use the Kilo Code Principal Engineer environment. This template enforces a strict, architecture-first workflow to ensure code quality, predictability, and professional project tracking.

## Architecture & Workflow

This template operates on a **3-Phase State Machine**. The AI is instructed *never* to write code blindly.

1. **Phase 1: Discovery:** The AI analyzes your request, scans the codebase, and asks clarifying questions to reduce uncertainty to zero.
2. **Phase 2: Planning:** The AI proposes a step-by-step implementation plan and updates `ABOUT.md` (or `.kilo/ABOUT.md`) and `PLAN.md`. It waits for your explicit approval.
3. **Phase 3: Execution:** The AI implements the code strictly according to the approved plan, ensuring DRY, SOLID, and deep error handling.

## Directory Structure

```text
/
├── .kilo/
│   ├── agent/             # The core Principal Engineer AI persona
│   │   └── principal.md   # Configures the YAML profile for Kilo UI
│   ├── command/           # Interactive workflows (/audit, /brief, etc.)
│   │   ├── audit.md       # Codebase health and security check
│   │   ├── brief.md       # Project initialization and architecture setup
│   │   ├── release.md     # Semantic versioning and changelog generator
│   │   ├── status.md      # Project progress dashboard parser
│   │   └── task.md        # Feature implementation starter
│   ├── rules/             # System-level constraints
│   │   ├── mcp-rules.md          # Rules for using context7, playwright, etc.
│   │   ├── project-rules.md      # Base stack, naming, and SEO conventions
│   │   ├── restricted-files.md   # Security locks for .env and credentials
│   │   ├── step-by-step-rules.md # Enforces the 1-step-at-a-time execution
│   │   └── tracking-rules.md     # Formatting for PLAN, CHANGELOG, etc.
│   ├── skill/             # Custom AI skills
│   │   └── spec-writer/
│   │       └── SKILL.md   # Instructions for writing technical specifications
│   └── ABOUT.md           # The template documentation boilerplate
├── Remove/                # Deprecated framework-specific scripts
├── AGENTS.md              # Global AI instructions and security rules
├── ARCHITECTURE_LOG.md    # Historical log of template evolution
├── kilo.json              # Kilo Code extension configuration
└── TEMPLATE_GUIDE.md      # This guide
```

*Note: Files like `PLAN.md`, `CHANGELOG.md`, `DECISIONS.md`, `VERSION`, and the root `ABOUT.md` are deliberately absent. They are dynamically generated when you run the `/brief` command.*

## How to Start a New Project

When applying this template to a completely empty repository, follow these steps:

1. **Initialize the Environment:**
   In the Kilo Code chat, type the `/brief` command.
   
2. **Answer the Architectural Questions:**
   The Principal Agent will ask you a series of questions regarding the project's scope, tech stack, and goals. Provide detailed answers.

3. **Confirm Initialization:**
   The agent will generate `DECISIONS.md` and configure `PLAN.md`, `CHANGELOG.md`, `VERSION`, and the project's root `ABOUT.md`.
   
4. **Dynamic Tooling Generation:**
   Based on your tech stack (e.g., React vs. Astro), the agent will automatically generate custom scaffolding commands (like `/new-component`) tailored specifically to your chosen framework.

## Day-to-Day Development

Do not write raw prompts like "make a login page." Instead, use the formal task initialization command:

1. **Start a Task:**
   Type `/task I need to build the authentication system`.
   
2. **Review the Plan:**
   The agent will ask technical questions (e.g., "Are we using JWT or Sessions?"). Answer them, and approve the generated plan.

3. **Check Progress:**
   At any time, type `/status` to see a visual dashboard of completed and pending tasks based on `PLAN.md`.

4. **Audit Code Quality:**
   Before merging a large feature, type `/audit`. The agent will scan for `console.log` statements, `any` types, and hardcoded secrets.

5. **Release a Version:**
   When you are ready to "ship," type `/release`. The agent will calculate the next Semantic Version, update the `CHANGELOG.md`, and modify the `VERSION` file.

## Security Constraints

The AI is strictly forbidden from reading or exposing `.env`, `credentials.json`, or lockfiles. Do not ask the AI to debug environment variables containing real production keys.