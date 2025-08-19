# Getting Started

Welcome! This guide helps you stand up a **CRAFT** repository quickly and run your first structured AI session.

---

## What CRAFT Is

CRAFT (Configurable Reusable AI Framework Technology) is a Python‑compatible, text‑file–based framework that turns ad‑hoc AI chats into **structured, repeatable workflows**. Each project is defined by four interoperable text files that preserve rules, memory, and handoffs between sessions.

- **Framework Spec** — the rules and primitives of CRAFT  
- **Core Cookbook** — ready‑to‑use “recipes” (standard operations)  
- **Project File** — your project’s persistent variables, functions, and objects  
- **AI Chat History** — the session‑to‑session handoff record

> Tip: Keep mental model simple → *Spec & Cookbook = the framework*, *Project & Chat History = your app & its ongoing work*.

---

## Why It’s Useful

- **Consistency across sessions** — your rules and variables persist
- **Clear collaboration** — anyone can pick up from the latest handoff
- **Token efficiency** — you send compact files, not sprawling prompts
- **Auditability** — changes, decisions, and next steps live in text

---

## Prerequisites

- A GitHub repo with this layout (or similar):
.
├─ core/ # framework + active project files
├─ docs/ # documentation
├─ examples/ # sample projects/templates
├─ .github/ # issue/PR templates, workflows
├─ LICENSE # Business Source License 1.1 (BSL 1.1)
└─ README.md


- A text editor (VS Code, Cursor, etc.)
- An AI assistant that lets you upload/read multiple text files in a chat

---

## Quick Start (10–15 minutes)

### 1) Put the four CRAFT files in `core/`

Place these files in `core/`:

- `CFT-FWK-SPEC-<version>.txt` (Framework Specification)
- `CFT-FWK-COOKBK-CORE-<version>.txt` (Core Cookbook)
- Your **Project File**: `CFT-PROJ-CP-<###>_<PROJECT-NAME>-v<MMDDaX>.txt`
- Your **Chat History**: `CFT-PROJ-CP-<###>_AI-CHAT-HISTORY-v<MMDDaX>.txt`

> Naming rules:
> - `<###>` = three‑digit project number (e.g., `032`)
> - `<PROJECT-NAME>` = UPPERCASE-HYPHENATED (e.g., `MANAGE-CRAFT-ON-GITHUB`)
> - `v<MMDDaX>` = version stamp (e.g., `v0819a1`)

If you’re starting fresh, copy the provided **MASTER templates** into `core/`, then rename them following the pattern above:
- `[MASTER-TEMPLATE]CFT-PROJ-CP-____[PROJECT-NAME]-v_.txt`
- `[MASTER-TEMPLATE]CFT-PROJ-CP-____AI-CHAT-HISTORY-v_.txt`

### 2) Open and personalize your **Project File**

In the `PROJECT_META` section:
- Set `PROJECT_ID`, `PROJECT_NAME`, `VERSION`, `LAST_UPDATED`, `PROJECT_PHASE`
- Fill out `PROJECT_GOALS` and `PROJECT_SUCCESS_METRICS`

In `PROJECT_VARIABLES`:
- Add values you want to **persist** across sessions (strings, lists, dicts)
- Avoid computed values here; keep this section as your project’s “memory”

### 3) Start your first CRAFT session

Upload these four files into a new AI chat:
1. `core/CFT-FWK-SPEC-<version>.txt`
2. `core/CFT-FWK-COOKBK-CORE-<version>.txt`
3. `core/CFT-PROJ-CP-<###>_<PROJECT-NAME>-v<...>.txt`
4. `core/CFT-PROJ-CP-<###>_AI-CHAT-HISTORY-v<...>.txt`

Then say something like:

> “Load all four CRAFT files. Follow the CRAFT comment system and CRAFT‑Operations‑Manager. Summarize what you loaded, confirm readiness with ‘No questions. Ready’, then help me tackle the first task.”

You should see the assistant acknowledge the comment protocol and report COM status.

### 4) End the session with a **Handoff Snapshot**

Before you close the chat, ask the assistant to **append a new handoff** block at the **top** of your Chat History file, summarizing:
- What was done, files touched, decisions/rationale
- Next steps, open questions, risks/blockers
- A consistency check

This enables a seamless pickup next time.

### 5) Commit & Push

Commit changes to `core/` (Project File updates, Chat History handoff) and push to GitHub so collaborators can continue from the latest handoff.

---

## Links & Next Steps

- **Overview docs** → [`docs/README.md`](./README.md)
- **This guide** → `docs/getting-started.md` (you’re here)
- **Framework Spec** → `core/CFT-FWK-SPEC-<version>.txt`
- **Core Cookbook** → `core/CFT-FWK-COOKBK-CORE-<version>.txt`
- **Examples** → `examples/` (sample projects & templates)

---

## How to Contribute

1. Read [`CONTRIBUTING.md`](../CONTRIBUTING.md) and [`CODE_OF_CONDUCT.md`](../CODE_OF_CONDUCT.md)
2. Open a clear issue or start a discussion
3. Use consistent naming/versioning for new Project/History files
4. Keep PRs small and add a concise **Handoff** note in the Chat History describing your changes

---

## License

This repository uses **Business Source License 1.1 (BSL 1.1)**.  
- **Non‑commercial use** (research, education, experimentation) is permitted.  
- **Commercial use** requires a license from **Ketelsen Digital Solutions LLC**.  
- On or after **2029‑01‑01**, the license transitions to **Apache 2.0**.  
See the root `LICENSE` file for the exact terms.

---

## FAQ

**Where should the four CRAFT files live?**  
Place them directly in `core/` for discoverability. If you keep templates, place them in `core/templates/` and copy/rename into `core/` when activating.

**What belongs in the Project File vs. Chat History?**  
- **Project File**: long‑lived facts, configs, variables (persistence)  
- **Chat History**: current work state, decisions, next steps (handoff)

**How do I version files?**  
Bump the `vMMDDaX` suffix when you make meaningful changes.
