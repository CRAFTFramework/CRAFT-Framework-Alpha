# CRAFT Framework Overview (Four‑File Model & Roles)

## What this page is
A beginner‑friendly overview of how the CRAFT framework is organized into **four cooperating, Python‑compatible text files**, what each file is responsible for, and how they work together in your repo. :contentReference[oaicite:0]{index=0}

---

## The four files at a glance

> **CRAFT uses exactly four core files per project.** Keep these names and roles consistent to make handoffs and automation reliable. :contentReference[oaicite:1]{index=1}

1) **Project Implementation File**  
   **Name pattern:** `CFT-PROJ-[project_number]_[project_name]-v[version].txt`  
   **Role:** Your *active* project “code”—the place to define variables, functions, objects, and any structured chat instructions specific to this project. Update this as your implementation evolves. **Do** put persistent values under `PROJECT_VARIABLES`. **Don’t** store long‑running chat context here. 

2) **Conversation Continuity (AI Chat History) File**  
   **Name pattern:** `CFT-PROJ-[project_number]_AI-CHAT-HISTORY-v[version].txt`  
   **Role:** Provides the **Handoff** system so each session can pass “what just happened, what’s next” to the next session. Its content is short‑term context (reverse‑chronological snapshots), not permanent configuration. :contentReference[oaicite:3]{index=3}

3) **Framework Specification File**  
   **Name pattern:** `CFT-FWK-SPEC-v[version].txt`  
   **Role:** The authoritative spec for CRAFT (principles, rules, patterns, global instructions). This is where the comment system, persistence guidance, and order‑of‑operations are defined. :contentReference[oaicite:4]{index=4}

4) **Basic Framework Cookbook File**  
   **Name pattern:** `CFT-FWK-COOKBK-CORE-v[version].txt`  
   **Role:** The base set of **recipes** that every CRAFT project can use (e.g., handoff helpers, common tasks). Keep it enabled for reliable defaults. :contentReference[oaicite:5]{index=5}

---

## How the files work together

- **Load/priority (“Order of Operations”):** When duplicate instructions exist, **the Project Implementation file takes priority over AI‑CHAT‑HISTORY**, and both take priority over the Framework Spec. (Cookbook recipes are utilities called by the others.) This ensures project‑specific rules win. :contentReference[oaicite:6]{index=6}

- **Persistence vs. Handoff:**  
  - **Persistence** = long‑term values you want available every session → put them in **`PROJECT_VARIABLES`** inside the Project Implementation file.  
  - **Handoff** = short‑term “where we left off” between sessions → maintain via the **AI‑CHAT‑HISTORY** file’s snapshot sections (newest at the top). 

---

## What belongs in each file (quick checklist)

**Project Implementation (`CFT-PROJ-...-v*.txt`)**  
- ✅ Project identifiers, constants, config dictionaries  
- ✅ Reusable project functions/objects  
- ✅ Persistent variables under `PROJECT_VARIABLES`  
- ❌ No session transcripts or ephemeral notes (use AI‑CHAT‑HISTORY) :contentReference[oaicite:8]{index=8}

**AI‑CHAT‑HISTORY (`CFT-PROJ-..._AI-CHAT-HISTORY-v*.txt`)**  
- ✅ Reverse‑chronological **Handoff** snapshots (Session summary, decisions, next steps)  
- ✅ Short‑term blockers, open questions  
- ❌ No persistent configuration (move to `PROJECT_VARIABLES` in Project Implementation) :contentReference[oaicite:9]{index=9}

**Framework Spec (`CFT-FWK-SPEC-v*.txt`)**  
- ✅ Global rules (comment system, safety, validation, philosophy)  
- ✅ Reference for “how to talk CRAFT” and priorities  
- ❌ No project‑specific constants (keep those in Project Implementation) :contentReference[oaicite:10]{index=10}

**Core Cookbook (`CFT-FWK-COOKBK-CORE-v*.txt`)**  
- ✅ Standard recipes (e.g., Handoff helpers)  
- ✅ Keep **enabled** in `COOKBOOK_CONFIG` for reliability  
- ❌ No project‑specific state (call recipes, don’t store data here) :contentReference[oaicite:11]{index=11}

---

## Naming & versioning conventions

Use the templates’ patterns so tools and humans can find things quickly:

- **Project file:** `CFT-PROJ-CP-***_[PROJECT-NAME]-vMMDDaX.txt`  
- **Chat history:** `CFT-PROJ-CP-***_AI-CHAT-HISTORY-vMMDDaX.txt`  
- Replace `***` with a 3‑digit project number; use **UPPERCASE‑HYPHENATED** project names; versions use `vMMDDaX`. 

You can also configure **COOKBOOK_CONFIG** to keep the core cookbook enabled and select loading strategy. :contentReference[oaicite:13]{index=13}

---

## Suggested repo placement

A clean layout helps newcomers navigate:

/core/
CFT-PROJ-CP-032_MANAGE-CRAFT-ON-GITHUB-v1a.txt
CFT-PROJ-CP-032_AI-CHAT-HISTORY-v1a.txt
CFT-FWK-SPEC-v0.0825g6.txt
CFT-FWK-COOKBK-CORE-v0825c5.txt

/docs/
README.md
getting-started.md
framework-overview.md ← (this file)

/.github/
ISSUE_TEMPLATE/...
PULL_REQUEST_TEMPLATE.md
workflows/...

/examples/
...

> Tip: Some teams keep the **four core files together under `/core/`** and use `/docs` for human‑readable guides like this page. Keep filenames intact for compatibility with CRAFT conventions. :contentReference[oaicite:14]{index=14}

---

## Daily workflow (beginner‑friendly)

1. **Open the Project Implementation file** to review persistent config (`PROJECT_VARIABLES`) and any reusable functions/objects. :contentReference[oaicite:15]{index=15}  
2. **Skim the latest Handoff** at the top of the AI‑CHAT‑HISTORY file to see what just happened and the next steps. :contentReference[oaicite:16]{index=16}  
3. **Do the work** (update implementation, run recipes, make decisions).  
4. **Capture a new Handoff snapshot** (short summary, decisions, next steps) at session end—add it to the **top** of AI‑CHAT‑HISTORY. :contentReference[oaicite:17]{index=17}  
5. **Move any lasting values** (URLs, flags, constants) into `PROJECT_VARIABLES` so they persist next time. :contentReference[oaicite:18]{index=18}

---

## License (read me first)

This project uses the **Business Source License 1.1 (BSL 1.1)**:  
- **Free for non‑commercial use** (research, educational, experimental).  
- **Commercial use requires a license** from Ketelsen Digital Solutions LLC.  
- **Change date:** On or after **2029‑01‑01**, the files transition to **Apache 2.0**.  

Place your `LICENSE` at the repo root and keep the license header in each CRAFT file intact. 

---

## Links & next steps

- **Docs home:** [`./README.md`](./README.md)  
- **Getting Started:** [`./getting-started.md`](./getting-started.md)  
- **Project Implementation template details:** see comments and sections inside your `CFT-PROJ-...-v*.txt` file. :contentReference[oaicite:20]{index=20}  
- **Handoff structure & reverse‑chronology:** see `CFT-PROJ-..._AI-CHAT-HISTORY-v*.txt`. :contentReference[oaicite:21]{index=21}  
- **Global rules & priorities:** see `CFT-FWK-SPEC-v*.txt` (comment system, order of operations). :contentReference[oaicite:22]{index=22}
