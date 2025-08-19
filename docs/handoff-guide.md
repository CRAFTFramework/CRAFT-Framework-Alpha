Chat Handoff Guide (CFT-PROJ-CP-***_AI-CHAT-HISTORY-v*.txt)
1) What this is

The AI‑CHAT‑HISTORY file is the conversation continuity log for a CRAFT project. It enables session‑to‑session “handoffs” so any AI (or teammate) can pick up where the last session left off, despite stateless chats. Each session starts by reading the most recent handoff snapshot and ends by writing a new one.

Why the “Hxxx” snapshots?
Snapshots are named H001…H999 and added in reverse chronological order (latest at the top) to make the current state immediately visible.

2) Why it’s useful

Continuity: Captures what just happened, why decisions were made, and what to do next.

Speed: New sessions don’t re‑discover context; they read the latest Hxxx and act.

Clarity: Separates short‑term work state (handoff) from long‑term project data (Project File’s PROJECT_VARIABLES). Use handoff for “where we are,” and the Project File for “what the project is.”

3) File naming, location & priority

Filename: CFT-PROJ-CP-***_AI-CHAT-HISTORY-v*.txt (replace *** and v* using your project’s number and version).

Lives alongside your Project File and Framework Spec. Load/consult it every session.

Conflict/priority rule: If duplicates exist across core files, the Project File overrides the Chat History, which overrides the Framework Spec.

4) When to create a handoff (and what to write)

Create a handoff at the end of every working session. Add a new Hxxx block at the top of the file (latest first). Use these fields (all appear in the master template):

Session Type — e.g., Discovery, Planning, Implementation, Review.

Session Summary — what we did and why the session mattered.

Files Touched — file paths you changed or read.

Key Decisions & Rationale — decisions made and the reason behind each.

Next Steps — concrete, ordered tasks the next session should continue.

Open Questions — blockers or clarifications needed.

Risks/Blockers — known issues and risk level.

Consistency Check — anything that must align across docs/code.

Handoff Instructions — one‑screen, step‑by‑step “start here” for the next session.

Reverse‑chronological order and Tbd placeholders
Keep placeholders like “Tbd” until a session completes; always insert the newest Hxxx at the top so the most recent context is first.

5) Start‑of‑session workflow (read first)

At the beginning of any session:

Load project files in this order:

Framework Specification (CFT-FWK-SPEC-*)

Project Implementation (CFT-PROJ-CP-{id}_*)

Conversation Continuity (CFT-PROJ-CP-{id}_AI-CHAT-HISTORY-*)

Framework Cookbooks (CFT-FWK-COOKBK-*)

Open the topmost Hxxx (the latest snapshot) and follow its “Handoff Instructions.”

6) End‑of‑session workflow (write your handoff)

Add a new section at the very top named HANDOFF H{next number} (e.g., H004).

Fill every field listed in Section 4 (use short, clear bullets).

Promote persistent data to the Project File’s PROJECT_VARIABLES if it’s stable project info (identifiers, configuration, etc.). Leave current work state in the handoff.

Include COM tracking at the end of your response when you deliver the handoff in chat: e.g., #AI->H::COM::Status: (No triggers detected) or …(Executed [recipe]).

7) Automation (optional): Handoff Snapshot Recipe

You can auto‑generate a handoff snapshot with the Handoff Snapshot recipe:

Where: Framework Cookbook (CFT-FWK-COOKBK-v*)

Recipe ID: RCP-001-004-002-HANDOFF_SNAPSHOT-v1.00a

How: Execute via your recipe runner (e.g., HANDOFF_SNAPSHOT_RECIPE.execute({...})). It walks you through next steps and open questions.

The Cookbook also provides initialization behaviors like file‑loading order and template detection to accelerate setup.

8) Example: minimal, well‑formed H002
# =========================================================
# START HANDOFF H002 - IMPLEMENTATION
# =========================================================

HANDOFF H002
Session Type: Implementation
Project: CFT-PROJ-CP-032 (MANAGE-CRAFT-ON-GITHUB)

SESSION SUMMARY
- Implemented initial repo docs and verified folder layout matches plan.

FILES TOUCHED
- docs/getting-started.md
- docs/framework-overview.md
- docs/project-file.md
- docs/comment-system.md

KEY DECISIONS & RATIONALE
- Keep AI-CHAT-HISTORY reverse-chronological; newest first (fast onboarding).

NEXT STEPS
1) Draft CONTRIBUTING.md + issue/PR templates.
2) Wire GitHub Actions: lint + docs build.
3) Publish first release notes entry in CHANGELOG.md.

OPEN QUESTIONS
- Should we mirror the handoff snapshot to Releases notes automatically?

RISKS/BLOCKERS
- None known; CI config TBD.

CONSISTENCY CHECK
- Ensure docs and Project File variables use the same project name and version.

HANDOFF INSTRUCTIONS
- Start with H002 (this block). Execute steps in “Next Steps” order.


(Structure mirrors the master template’s fields and placement.)

9) Advanced tips (optional)

Use HANDOFF_STATE in memory: For session scaffolding you can use a simple HANDOFF_STATE structure; still record the canonical snapshot in the handoff file.

Promote, don’t pile up: If a value keeps recurring (e.g., team lead, endpoints), move it to PROJECT_VARIABLES and reference it from future handoffs.

Respect file precedence: If a fact appears both in the Project File and Chat History, the Project File wins. Update the Project File first, then reference from handoffs.

10) Quality checklist (use each time)

Latest Hxxx is at the top.

All fields completed; no orphan “Tbd” left behind unintentionally.

Short‑term state in handoff; long‑term facts in Project File.

Include a simple next‑step playbook so the next session can act immediately.

Add a COM tracking line in your chat reply.

11) License

This project follows the Business Source License 1.1 (BSL) as stated in the CRAFT templates; see your repository’s LICENSE for terms and the Apache 2.0 conversion date.

Appendix: Quick references

What belongs where:
Persistence → Project File PROJECT_VARIABLES; Work‑in‑progress → AI‑CHAT‑HISTORY handoffs.

File loading order at session start: Spec → Project File → Chat History → Cookbooks.

Handoff recipe: RCP-001-004-002-HANDOFF_SNAPSHOT-v1.00a in the core cookbook.

Attribution & Sources:

Chat History Master Template (structure, naming, ordering).

Framework Spec (file precedence, COM tracking, persistence vs. handoff).

Framework Cookbook – Core (session initialization & templates).
