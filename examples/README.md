# CRAFT Examples Index

> **Status:** 🚧 seed catalog — examples are being added.  
> **Audience:** new to CRAFT; follow the guided quick-starts below.

![BSL-1.1](https://img.shields.io/badge/license-BSL--1.1-blue.svg)
![Experimental](https://img.shields.io/badge/status-experimental-orange.svg)
[![Code of Conduct](https://img.shields.io/badge/CoC-org--wide-green.svg)](../CODE_OF_CONDUCT.md)

---

## What this folder is for

These examples will serve **three** purposes:

1) **“Hello, CRAFT” quick starts** that teach the **four-file workflow** (Project, Chat History, Framework Spec, Core Cookbook).  
2) **Template projects** you can copy/rename to bootstrap your own work.  
3) **Showcase & recipes** that demonstrate common tasks and patterns.

> CRAFT projects always use the same four files working together. See the docs links below if you’re new to this. (CFT-FWK-SPEC-v0.0825g6.txt, 2025; CFT-FWK-COOKBK-CORE-v0825c5.txt, 2025.) :contentReference[oaicite:0]{index=0} :contentReference[oaicite:1]{index=1}

---

## Before you start (recommended reading)

- **Getting Started** → `../docs/getting-started.md`  
- **Framework Overview** (four-file model & roles) → `../docs/framework-overview.md`  
- **Project File Guide** → `../docs/project-file.md`  
- **Chat Handoff Guide** → `../docs/handoff-guide.md`  
- **Core Cookbook Guide** → `../docs/cookbook-core.md`  
- **Framework Spec Reference** → `../docs/framework-spec-reference.md`  
- **Comment System** → `../docs/comment-system.md`

---

## How to run an example

The current runtime is **LLM chat**. Pick your model (ChatGPT / GPT-5 Pro / Claude / Gemini), then:

1. **Open a new chat/session.**  
2. **Load the four CRAFT files** for the example or template you’re trying:
   - Project implementation: `CFT-PROJ-CP-***_[PROJECT-NAME]-v*.txt`
   - Chat continuity: `CFT-PROJ-CP-***_AI-CHAT-HISTORY-v*.txt`
   - Framework spec: `CFT-FWK-SPEC-v*.txt`
   - Core cookbook: `CFT-FWK-COOKBK-CORE-v*.txt`  
3. **Follow the prompts** the files provide (the Spec & Cookbook define how the chat operates).  
4. When you’re done, **create a handoff** (see Handoff Guide) and save updates back into your files.

> Tip: The repository’s planned structure and four-file workflow are defined in the project plan. (CFT-PROJ-CP-032_MANAGE-CRAFT-ON-GITHUB-v1a.txt, 2025.) :contentReference[oaicite:2]{index=2}

---

## Directory map

This index lists the categories you’ll see here. We’ve included a `README.md` in each folder so the directories remain visible while examples are being authored.

examples/
├─ basic/ # “Hello, CRAFT” quick starts – smallest possible runnable samples
├─ templates/ # Copy-ready project skeletons aligned to the master templates
├─ workflows/ # Multi-step, realistic flows (e.g., draft→review→handoff)
├─ advanced/ # Deeper patterns, larger or specialized scenarios
└─ integrations/ # Optional integrations and ecosystem examples


- **basic/** → `examples/basic/README.md` (placeholder)  
- **templates/** → `examples/templates/README.md` (placeholder)  
- **workflows/** → `examples/workflows/README.md` (placeholder)  
- **advanced/** → `examples/advanced/README.md` (placeholder)  
- **integrations/** → `examples/integrations/README.md` (placeholder)

---

## Use any example as a template

You can turn any example into your own project by following these steps (consistent with the **MASTER templates**):

1. **Copy** the example folder into a new location.  
2. **Rename** files to the standard pattern:
   - `CFT-PROJ-CP-***_[PROJECT-NAME]-v*.txt`
   - `CFT-PROJ-CP-***_AI-CHAT-HISTORY-v*.txt`
3. In each file, **replace placeholders**:
   - `***` → your three-digit project number (e.g., `032`)  
   - `[PROJECT-NAME]` → UPPERCASE-HYPHENATED name (e.g., `MY-FIRST-CRAFT`)  
   - `v*` → version format `vMMDDaX` (e.g., `v0819a1`)  
4. Update the **date** and **version** headers.  
5. Load the four files into a new chat and begin.

> See the master templates for the exact placeholder rules. (MASTER templates) :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4}

---

## What’s here now (and what’s coming)

- ✅ Folder scaffolding with `README.md` placeholders in **basic/**, **templates/**, **workflows/**, **advanced/**, **integrations/**.  
- 🚧 Initial runnable examples are being curated; watch this space for the first “Hello, CRAFT” quick start and a copy-ready template.

---

## License & usage

All examples in this folder are covered by the repository’s **Business Source License 1.1 (BSL)**:

- **Non-commercial** use (research, education, experimentation, personal) is permitted.  
- **Commercial** use requires a separate license from Ketelsen Digital Solutions LLC.  
- On the **Change Date** (**2029-01-01** for this release), the examples will be available under **Apache 2.0**.  
- See the full text in the repo root: `../LICENSE`. (Business Source License 1.1 parameters are included with the four CRAFT files.) :contentReference[oaicite:5]{index=5}

---

## Community & conduct

This repository follows an **org-wide Code of Conduct**. Please read and abide by it when proposing or discussing examples: `../CODE_OF_CONDUCT.md`.

---

## Handy references

- Four-file model & rules: Framework Spec and Core Cookbook. :contentReference[oaicite:6]{index=6} :contentReference[oaicite:7]{index=7}  
- Repo structure and GitHub strategy for CRAFT: Project file for CP-032. :contentReference[oaicite:8]{index=8}
