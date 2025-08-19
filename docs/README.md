# CRAFT Documentation Hub (`/docs`)

Welcome to the documentation hub for **CRAFT — Configurable Reusable AI Framework Technology**.

## 1) What it is

This `/docs` folder is the central knowledge base for the CRAFT framework. It explains how CRAFT’s **four-file architecture** works (Project file, AI chat history handoff, Framework Spec, and Core Cookbook), how to get started, and where to find deeper guides and examples. See the repo’s `core/` for the framework files that power these docs.

## 2) Why it’s useful

CRAFT helps you turn ad‑hoc AI chats into a **structured, reusable workflow**:
- **Consistency across sessions** via a standard project file and chat-history handoffs.
- **Clear separation of concerns** (framework spec vs. your project state).
- **Token & time savings** thanks to reusable variables, functions, and objects defined once and reused.
- **Beginner‑friendly** on‑ramp with copy‑paste templates and predictable file naming.

## 3) Install / Quick Start

> No build step required — CRAFT is driven by Python‑compatible **text** files you share with your AI assistant.

1. **Clone / open the repo** and review its layout:
core/ # Framework spec & cookbook (CRAFT core)
examples/ # Sample projects/templates
docs/ # You are here (documentation hub)
.github/ # Issue/PR templates, workflows, config


2. **Add/confirm the four CRAFT files** (often stored under `core/`):
- `CFT-FWK-SPEC-v*.txt` – Framework Specification (authoritative rules & patterns)
- `CFT-FWK-COOKBK-CORE-v*.txt` – Core Cookbook (base recipes)
- `CFT-PROJ-CP-***_[PROJECT-NAME]-v*.txt` – Your **Project Implementation** file
- `CFT-PROJ-CP-***_AI-CHAT-HISTORY-v*.txt` – Chat **Handoff** file
3. **Name your project files** using the included MASTER template guidance:
- Three‑digit project number (`***`), UPPERCASE‑HYPHENATED project name, and version `vMMDDaX`.
4. **Fill placeholders** in your Project file:
- Update `PROJECT_META`, set goals, add persistent values in `PROJECT_VARIABLES`, and keep functions/objects project‑specific.
5. **Use the Handoff flow** during/after each working session:
- Record what changed, decisions, next steps, and open questions in the **latest** handoff section (reverse‑chronological), then continue seamlessly next time.
6. **Commit** your changes. Keep docs/pages (below) in sync with what’s actually in `core/` and your project files.

> Tip: Start with **Getting Started** and **Framework Overview** (links below), then skim **Comment System** to learn how CRAFT’s instruction comments shape responses.

## 4) Links to docs/

- **Getting Started** → `./getting-started.md`  
- **Framework Overview** (four-file model & roles) → `./framework-overview.md`  
- **CRAFT Comment System** (H->AI / AI->H patterns) → `./comment-system.md`  
- **Project File Guide** (`CFT-PROJ-CP-***_[PROJECT-NAME]-v*.txt`) → `./project-file.md`  
- **Chat Handoff Guide** (`..._AI-CHAT-HISTORY-v*.txt`) → `./handoff-guide.md`  
- **Core Cookbook Guide** (`CFT-FWK-COOKBK-CORE-v*.txt`) → `./cookbook-core.md`  
- **Framework Spec Reference** (`CFT-FWK-SPEC-v*.txt`) → `./framework-spec-reference.md`  
- **Examples Index** → `../examples/README.md`  
- **Core Index** → `../core/README.md`

> If a page doesn’t exist yet, treat this link set as a TODO checklist.

## 5) How to contribute

1. Read `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md` at the repo root.  
2. For docs changes, create a branch and edit files under `/docs`. Prefer concise pages that link to deeper references.  
3. Open an Issue for proposals; link it in your PR.  
4. Follow style: sentence‑case headings, short paragraphs, examples over theory, and relative links.  
5. Keep examples synced with `core/` files and `examples/` projects.

## 6) License

This repository uses the **Business Source License 1.1 (BSL 1.1)**.  
- **Non‑commercial use** (research, educational, experimental) is permitted.  
- **Commercial use** requires a separate license from the rights holder.  
- On or after **2029‑01‑01**, applicable files are set to relicense to **Apache 2.0** (per the license header present in the framework/spec files).

See the root `LICENSE` (or the included “Business Source License 1.1” file) for the full legal text. If you’re planning commercial use, please contact the project owner to obtain a commercial license.

---
