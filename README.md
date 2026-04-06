<div align="center">

# ⚙️ Kilo Code: Universal Principal Engineer Template
**An Architecture-First AI Agent Template for Kilo Code**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Kilo Code Compatible](https://img.shields.io/badge/Kilo_Code-Compatible-000000?logo=github&logoColor=white)](https://github.com/Elguajo/kilocode-universal-template)
[![Architecture: 3-Phase](https://img.shields.io/badge/Architecture-3--Phase_Workflow-success)](#-the-3-phase-workflow)

*This template transforms your Kilo Code AI agent into a strict, methodical **Principal Engineer**.*

</div>

---

## 📖 Overview

Welcome to the **Universal Principal Engineer Template**. This repository is not a boilerplate of code; it is a **workflow state machine**. It overrides the AI's default "chatty" or "eager-to-code" behavior and enforces a highly professional, enterprise-grade development cycle.

By using this template, you ensure that the AI will **never write code blindly**. Instead, it follows a strict architectural discovery process, plans the implementation, and waits for your explicit approval before modifying a single file.

---

## 🏗️ The 3-Phase Workflow

This template programs the AI to operate strictly within three phases:

1. 🔍 **Phase 1: Discovery**
   *   The AI scans the codebase, identifies edge cases, and asks highly technical, clarifying questions.
   *   *Constraint:* The AI must reduce uncertainty to `0.0` before proceeding.
2. 📋 **Phase 2: Planning & Specification**
   *   The AI formulates a step-by-step implementation plan based on your answers.
   *   It updates tracking documents and waits for your explicit approval (`PLAN.md`).
3. ⚡ **Phase 3: Execution**
   *   The AI writes code adhering strictly to DRY, SOLID, and secure coding principles.
   *   Deep error handling and proper abstractions are implemented automatically.

---

## 🚀 Quick Start

To use this template for your next project, follow these steps:

### 1. Initialize from Template
Click the green **[Use this template]** button at the top right of this repository to create a new project.

### 2. Run the Brief Command
Once your new repository is open in your IDE with the Kilo Code extension active, open the chat and type:
```text
/brief
```

### 3. Answer the Intake Questions
The Principal Agent will ask you a series of questions about your stack, scope, and goals. It will then dynamically generate project-specific rules, `PLAN.md`, `CHANGELOG.md`, and replace this `README.md` with your actual project documentation.

---

## 📂 Architecture & Directory Structure

```text
/
├── .kilo/
│   ├── agent/             # The core Principal Engineer AI persona
│   │   └── principal.md   # Configures the YAML profile for Kilo UI
│   ├── command/           # Interactive slash workflows
│   │   ├── audit.md       # /audit: Codebase health and security check
│   │   ├── brief.md       # /brief: Project initialization
│   │   ├── release.md     # /release: SemVer and changelog generator
│   │   ├── status.md      # /status: Progress dashboard parser
│   │   └── task.md        # /task: Feature implementation starter
│   ├── rules/             # System-level constraints
│   │   ├── mcp-rules.md          # Rules for using Context7, Playwright, etc.
│   │   ├── project-rules.md      # Base stack, naming, and SEO conventions
│   │   ├── restricted-files.md   # Security locks for .env and credentials
│   │   └── tracking-rules.md     # Formatting for PLAN, CHANGELOG, etc.
│   ├── skill/             # Custom AI skills
│   │   └── spec-writer/   # Instructions for writing technical specifications
│   └── ABOUT.md           # The template documentation boilerplate
├── AGENTS.md              # Global AI instructions and security rules
├── ARCHITECTURE_LOG.md    # Historical log of template evolution
├── TEMPLATE_GUIDE.md      # Detailed usage guide
└── kilo.json              # Kilo Code extension configuration
```

---

## 🛠️ Dynamic Tooling

A key feature of this template is **Dynamic Tooling Generation**. During the `/brief` initialization, the Principal Agent analyzes your chosen tech stack (e.g., React vs. Astro vs. Python CLI). Instead of relying on static, generic tools, the agent will automatically write **custom commands** tailored exactly to your framework (e.g., `/new-component` specifically for React/Tailwind).

---

## 🔒 Security

This template includes strict `restricted-files.md` rules. The AI is explicitly forbidden from reading, outputting, or interacting with:
*   `.env` files and production credentials
*   `package-lock.json` / `yarn.lock` (to prevent context window bloat)
*   Any file containing hardcoded secrets.

---

## 🤝 Contributing

We welcome architectural proposals and bug reports. Please use the provided `.github/ISSUE_TEMPLATE` forms when submitting:
*   [Report a Bug](../../issues/new?template=bug_report.md)
*   [Propose an Architectural Change](../../issues/new?template=feature_request.md)

## 📄 License

This project is licensed under the [MIT License](LICENSE) - see the LICENSE file for details.
Copyright (c) 2026 Khusan Turaev (Elguajo).