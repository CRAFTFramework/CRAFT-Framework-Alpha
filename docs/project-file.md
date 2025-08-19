1) What this file is

The Project File is the “working code” for a specific CRAFT project. It holds your project’s identity, global instructions, long‑lived variables (persistence), and (optionally) light, project‑specific utilities and objects. It’s one of the four files that make up every CRAFT implementation (Project File, AI Chat History, Framework Spec, and Framework Cookbook).

The Framework Specification also describes how these four files interlock and how priority/ordering works across sessions.

2) Why it’s useful

Session‑to‑session memory: Variables defined here (in PROJECT_VARIABLES) persist between chats, so your assistant starts with your project’s facts every time.

Single source of truth: Project ID, version, goals, personas, and cookbook config live in one place.

Consistency & governance: It standardizes naming/versioning and documents your rules (e.g., COM settings, recipe categories).

The Spec further clarifies persistence vs. handoff with concrete examples and best practices.

3) Install / Quick Start

Recommended location: Keep your active Project File under core/ (alongside the Framework Spec and Core Cookbook) to match the modular layout you defined (e.g., core/ for framework files).

Create your first Project File

Copy the master template named like [MASTER-TEMPLATE] CFT-PROJ-CP-***_[PROJECT-NAME]-v*.txt.

Rename using the standard pattern:

*** → three‑digit project number (e.g., 032)

[PROJECT-NAME] → UPPERCASE‑HYPHENATED (e.g., MANAGE-CRAFT-ON-GITHUB)

v* → version like v0819a1 (MMDD + letter + increment)

Set Last Updated to MM-DD-YYYY.

Open the file and replace [PLACEHOLDER] values in Section 1. PROJECT_META (ID, name, version, phase) and add your PROJECT_GOALS and PROJECT_SUCCESS_METRICS.

Configure COM and token thresholds in PROJECT_INSTRUCTIONS (usually keep defaults).

Add persistent data in PROJECT_VARIABLES (IDs, settings, descriptions, feature flags). Do not put computed/ephemeral values here.

(Optional) Add truly project‑specific helper functions/objects in PROJECT_FUNCTIONS/PROJECT_OBJECTS (keep light; prefer the Framework Spec for shared logic).

Commit the file and reference it at the start of each session.

4) Anatomy of the Project File (section‑by‑section)

Each template includes the same top‑level sections. Here’s what to fill and how each is used:

PROJECT_META — Project identity and version tracking (ID, name, phase, last updated, goals, success metrics).

PROJECT_INSTRUCTIONS — Global runtime rules (comment system types, COM on/off, token thresholds, recipe behavior). Keep defaults unless you have a reason to change.

PROJECT_VARIABLES — The persistence hub. Define strings, numbers, dicts/lists for facts and configuration that should survive across sessions. Avoid computed/temporary values here.

PROJECT_FUNCTIONS — Optional, small helpers unique to this project (if any). Shared/portable functions typically live in the Framework Spec or cookbooks.

PROJECT_OBJECTS — Optional, project‑specific classes/templates. Keep concise.

COOKBOOK CONFIGURATION — Which cookbooks are active; loading strategy; fallback behavior.

PERSONA CONFIGURATION — Default persona and allowed personas.

ABOUT_ME (Optional) — Personalization to help the AI tailor outputs.

Tip: The master template includes an explicit “Variable Persistence Documentation” block that illustrates how to structure and maintain persistent variables. Use it as your checklist while editing.

5) Persistence vs. Handoff (and how the Chat History file fits)

Persistence (Project File → PROJECT_VARIABLES) stores long‑term facts and stable configuration: “what the project is”.

Handoff (AI Chat History file) stores short‑term state for continuity between sessions: “where we are and what’s next”. The Chat History file uses reverse‑chronological HANDOFF H* blocks with placeholders that get filled at the end of each session (latest at the top).

The Spec provides additional guidance and tested patterns for what to persist, what not to persist, and how to structure both persistence and handoffs.

6) Naming, Versioning & Dates (exact format)

Use these conventions (enforced by the templates):

Filename: CFT-PROJ-CP-***_[PROJECT-NAME]-v*.txt

Project number (***): three digits (e.g., 032)

Project name: UPPERCASE‑HYPHENATED (e.g., MANAGE-CRAFT-ON-GITHUB)

Version: vMMDDaX (e.g., v0819a1)

Last Updated: MM-DD-YYYY (e.g., 08-19-2025)

7) Minimal example (top of a filled file)
# CRAFT PROJECT FILE
# Filename: CFT-PROJ-CP-032_MANAGE-CRAFT-ON-GITHUB-v0819a1.txt
# Version: v0819a1
# Last Updated: 08-19-2025

PROJECT_ID = "CFT-PROJ-CP-032"
PROJECT_NAME = "MANAGE-CRAFT-ON-GITHUB"
VERSION = "v0819a1"
LAST_UPDATED = "08-19-2025"
PROJECT_PHASE = "Alpha Phase 1"

PROJECT_GOALS = """
Establish a best‑practice GitHub repo for the CRAFT framework with clear docs,
templates, CI, and contributor onboarding.
"""

PROJECT_SUCCESS_METRICS = [
    "Ship v0.1 with passing CI and release notes",
    "≥5 external contributors within 60 days",
    "Docs coverage: getting‑started, overview, file guides"
]


Keep the rest of the sections (Instructions, Variables, etc.) from the template and tailor as needed.

8) Best‑practice tips (do / don’t)

Do

Keep facts and configs in PROJECT_VARIABLES; add date comments like # Added: YYYY‑MM‑DD.

Keep COM/token defaults unless you have a specific workflow change.

Use personas intentionally and document changes.

Don’t

Put computed or session‑specific values in PROJECT_VARIABLES. (Those belong in the Handoff.)

Overload PROJECT_FUNCTIONS with heavy/shared logic—prefer the Framework Spec or cookbook recipes.

9) Related docs

Getting Started → ./getting-started.md

Framework Overview (four‑file model & roles) → ./framework-overview.md

Comment System → ./comment-system.md

10) How to contribute (to your Project File)

Open a PR that updates the Project File (bump VERSION and LAST_UPDATED).

In the PR description, summarize what changed and why.

Ensure PROJECT_VARIABLES only adds/removes persistent values.

If you alter COM settings, note the impact on contributors.

After merge, reference the updated file in your next session’s handoff.

11) License

All CRAFT files in this repository, including the Project File, are licensed under the Business Source License 1.1 (BSL): free for non‑commercial use; commercial use requires a license from Ketelsen Digital Solutions LLC; on or after 2029‑01‑01 they will be licensed under Apache 2.0. Include the LICENSE at the repo root and keep the header intact in each file.

12) FAQ

Q: Where do I put “work‑in‑progress” notes?
A: In the AI Chat History file as the latest HANDOFF H*** block (reverse chronological). Don’t place transient notes in PROJECT_VARIABLES.

Q: Can I store functions here?
A: You can add small, project‑specific helpers, but shared or heavy logic is better placed in the Framework Spec/Cookbook for reuse and clarity.

Q: What’s the load order and priority?
A: The Spec explains instruction priority and how the Project File interacts with other files during sessions.

Template references used on this page: Project File master template & guidance; Variable Persistence documentation; section roles and naming/version rules; and the AI‑Chat‑History handoff structure.
