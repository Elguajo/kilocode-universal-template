# Kilo Code: Architectural Evolution Log

This document records the design decisions and iterations that led to the creation of the universal "Principal Engineer" Kilo Code template. It serves as historical context for why the template is structured the way it is.

## Phase 1: Breaking Down the Legacy
**The Problem:** The initial templates (`kilocode-template` and `kilocode-template-new`) contained good business logic but suffered from severe architectural flaws:
- They used the deprecated `.kilocode` directory instead of the officially supported `.kilo`.
- Instructions were heavily fragmented across multiple unlinked markdown files in a generic `rules/` folder, causing the AI to lose context.
- Commands lacked the proper YAML frontmatter required by the Kilo Code extension to route them to the correct agent persona.

**The Solution:** We established `AGENTS.md` as the single source of truth for the "Principal Engineer Mandate" (enforcing a strict Discovery -> Planning -> Execution workflow). We also created a dedicated Kilo agent profile (`.kilo/agent/principal.md`) and configured `kilo.json` to tie it all together.

## Phase 2: Centralizing Workflows (Commands)
**The Problem:** Workflows like `/audit`, `/release`, and `/brief` were scattered and often ignored by the parser.
**The Solution:** We migrated these workflows into `.kilo/command/*.md`. Each file was equipped with a `description` and bound to the `principal` agent via YAML frontmatter, turning them into first-class interactive slash-commands within the Kilo UI.

## Phase 3: The `ABOUT.md` Standard
**The Problem:** Using `README.md` as a template file inside a repository often caused merge conflicts or overriding issues when cloning into existing projects.
**The Solution:** We generated `.kilo/ABOUT.md` using the "Best README Template" standard via Context7 MCP. It includes Badges, Tech Stack tables, and Environment Variable documentation. The Principal agent is explicitly instructed to maintain `ABOUT.md` instead of `README.md` to prevent conflicts.

## Phase 4: Restoring the `rules/` Ecosystem
**The Problem:** Initially, all rules were compressed into `AGENTS.md` to prevent context loss. However, this made the file too monolithic and hard to maintain.
**The Solution:** We restored the `.kilo/rules/` directory but solved the context-loss problem by adding `".kilo/rules/*.md"` to the `instructions` array in `kilo.json`. This allows Kilo Code to dynamically parse all markdown files in the rules folder.
We extracted:
- `restricted-files.md` (Security: locking down `.env` and `package-lock.json`).
- `tracking-rules.md` (Formatting for `PLAN.md`, `CHANGELOG.md`, `DECISIONS.md`).
- `project-rules.md` (Base stack, architecture, and SEO rules).
- `step-by-step-rules.md` (Enforcing the `Shall I continue?` prompt to prevent AI hallucinations).

## Phase 5: Deep MCP Integration
**The Problem:** The AI was relying on its training data, which often resulted in hallucinated API signatures.
**The Solution:** We restored `mcp-rules.md` with strict triggers:
- **`sequential-thinking`**: Must be called *before* writing code for complex tasks (3+ files).
- **`context7`**: Must be used to fetch live library documentation, overriding any conflicting training data.
- **`playwright`**: Must be used for visual verification (`browser_snapshot`) and error checking (`browser_console_messages`) after UI changes.

## Phase 6: The Epiphany of Dynamic Tooling
**The Problem:** The legacy templates included static workflows like `new-component.md`, `new-content.md`, `rewrite.md`, and `website-clone-rules.md`. These files were highly opinionated (assuming React/Astro or strict cloning tasks) and violated the concept of a "universal" template.
**The Solution:** 
1. We moved these static files to a `/Remove` folder.
2. We gave the Principal Engineer a new mandate in `AGENTS.md`: **Dynamic Tooling Generation**. 
3. We updated the `/brief` initialization command. Now, when the user initializes a project and defines their stack (e.g., Vue vs. React), the Principal agent will *automatically generate* custom, project-specific commands (like `/new-component`) and rules tailored exactly to that framework.

## Conclusion
The template transitioned from a static collection of text files into a dynamic, state-machine-driven ecosystem. The AI now acts not just as a coder, but as an Architect who builds and maintains their own development tools based on the environment they are deployed in.