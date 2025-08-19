Core Cookbook Guide (CFT-FWK-COOKBK-CORE-v*.txt)

Who this is for: Beginners setting up or extending the CRAFT framework who want a simple, reliable way to run repeatable “recipes” (structured prompts and workflows) across sessions.

1) What the Core Cookbook is

The Core Cookbook is the default, versioned collection of foundational CRAFT recipes that ship with every project. It provides reliable, reusable building blocks (e.g., session handoff, persona and token monitoring, safety checks) so you don’t have to reinvent common workflows each time. In the CRAFT four‑file model, the cookbook sits alongside your Project File, AI Chat History, and Framework Spec, and is referenced by your project’s configuration. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, “Every CRAFT project consists…”)

2) Why it’s useful

Consistency & speed: Encodes “how we do things” once, then reuses it everywhere.

Safety by design: Adds guardrails (e.g., recipe security validation) before execution.

Low token footprint: Replacing long instructions with short recipe calls saves tokens.

Upgradable: Cookbook versions can be bumped without breaking your project structure.
These benefits are core to CRAFT’s philosophy of structure, safety, and token conservation. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Sections 1 & 1.10)

3) Where it fits in your repo

File name: CFT-FWK-COOKBK-CORE-v*.txt (the * is your version tag).

Activation: Your Project File declares which cookbooks are active and how they load. Look for the COOKBOOK_CONFIG block and RECIPE_CATEGORIES mapping to see what’s enabled and how recipes are grouped (e.g., “Core Framework Operations”). (CFT‑PROJ‑MASTER‑TEMPLATE, 2025, Section 6)

Tip: Keep the core cookbook under core/ or a framework folder and reference it via COOKBOOK_CONFIG in your project file so projects can opt‑in/out cleanly. (CFT‑PROJ‑MASTER‑TEMPLATE, 2025, Section 6)

4) Cookbook anatomy (what’s inside)

Recipes are structured objects with well‑defined fields so AIs can load, validate, and run them reliably:

Recipe: recipe_id, title, prompt_template, parameters, plus optional description, difficulty, examples, version, and compatibility.

RecipeParameter: name, type, optional required, default, description, validation, example.

RecipeVersion: major, minor, patch (+ optional metadata).

RecipeCompatibility: min_craft_version, max_craft_version, required_features.
(See Data Types for Recipe, RecipeParameter, RecipeVersion, RecipeCompatibility.) (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 3.2)

5) How recipes run (no code required)

You’ll typically reference and execute recipes using framework‑standard functions defined in the spec. While you don’t need to write code to understand usage, here’s the flow you’ll follow conceptually:

Fetch (or quick‑run) a recipe

Quick execution: “fetch and execute in one step” with parameter validation handled for you.

Fetch only: Retrieve the recipe first (with cache and retries), then execute separately if you want more control.

Validation before execution

Ensures required parameters are present, types match, and security checks pass (e.g., blocks script injections).

Execute safely

On failure, the framework returns structured error info and guidance instead of breaking the flow.
(Functions covered: fetch_recipe, quick_recipe, execute_recipe_safe, plus parameter validation.) (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 5.9)

Beginner mental model

You choose a recipe → Framework confirms it’s safe and the inputs look right → Framework runs it and returns structured results or a clear, helpful error.

6) Security & safety (must‑know rule)

For any recipe-related operations, the spec enforces a strict URL allowlist and blocks unauthorized sources. The default policy only permits cookbook recipes from the official AICookbook.ai path; anything else is blocked with a security warning. Do not bypass or disable these checks—this is by design. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, “1.10 Recipe Security Validation Protocol”)

7) CRAFT‑OPERATIONS‑MANAGER (COM) integration

COM runs in the background to detect opportunities to use recipes, auto‑execute configured ones, and log COM tracking in responses (e.g., COM::Status). You don’t have to do anything special—just know that when you ask for something a recipe can handle, COM may auto‑suggest or run it and annotate the response for traceability. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 1.11)

8) Handoff: where the cookbook meets continuity

The Handoff Snapshot workflow is provided from the cookbook so every session can end by recording “what’s done / what’s next” and the next session can start with the latest context at the top of the history file. You’ll see references such as:

Recipe location: “Framework Cookbook”

Example ID: RCP-001-004-002-HANDOFF_SNAPSHOT-v1.00a

Usage: Create a new handoff at session end; add the newest at the top (reverse chronological).
(CFT‑PROJ‑AI‑CHAT‑HISTORY‑MASTER‑TEMPLATE, 2025, “Handoff Instructions” & example)

Remember:

Persistence (Project File PROJECT_VARIABLES) = what your project is.

Handoff (Chat History snapshots) = where you are in the work right now.
(CFT‑PROJ‑AI‑CHAT‑HISTORY‑MASTER‑TEMPLATE, 2025, “Persistence vs Handoff Clarification”)

9) Versioning & compatibility

Semantic versioning for recipes (major.minor.patch) helps you understand changes and impact.

Use RecipeCompatibility to state the supported CRAFT spec range so older/newer projects know if they can use a recipe safely.

In your Project File, the COOKBOOK_CONFIG block controls which cookbooks are active and whether to fallback to core if an optional cookbook is unavailable. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 3.2; CFT‑PROJ‑MASTER‑TEMPLATE, 2025, Section 6)

10) Authoring or extending core recipes (beginner checklist)

You’ll typically propose changes via PRs rather than editing the core cookbook directly. This checklist helps you draft a clean recipe addition:

Choose a single responsibility for the recipe (keep it focused). (Function best‑practice alignment.) (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 5.10)

Assign a unique recipe_id and human‑readable title.

Define parameters clearly: name, type (string/integer/enum/etc.), required?, default, validation.

Write the prompt template to reference parameters by name (avoid hidden assumptions).

Add examples (inputs and expected outputs) to reduce ambiguity.

Set version and compatibility and update the changelog (what changed and why).

Run through safety checks: parameter validation, content policy precheck, and—if remote—URL allowlist. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Sections 5.11 & 5.9)

Categorize the recipe (e.g., CAT-001 Core Framework Operations) so COM can find it. (CFT‑PROJ‑MASTER‑TEMPLATE, 2025, Section 6)

Suggested parameter table (add to your PR description):

name	type	required	default	description
topic	string	yes	—	What the recipe should work on
count	integer	no	5	How many items to generate
tone	enum	no	professional	Style hint for output
11) Troubleshooting

“SecurityError” on recipe run: You may be referencing a non‑approved URL or passing unsafe parameter content. Use only the approved recipe host and sanitize inputs. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 1.10 & Parameter Validation)

“ValidationError: Missing required parameter”: Check the recipe’s parameter list and include all required fields. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 5.9)

Recipe runs but returns warnings: That’s expected when validation attaches non‑blocking warnings—review them to improve your inputs next time. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, Section 5.9)

12) License

This cookbook (and all CRAFT files in this repo) is licensed under the Business Source License 1.1 (BSL): free for non‑commercial use; commercial use requires a license from the publisher; and on or after 2029‑01‑01 the files transition to Apache 2.0. See the license file included in the repository for full terms. (CFT‑FWK‑SPEC‑v0.0825g6.txt, 2025, file header)

13) Related docs

Getting Started → ./getting-started.md

Framework Overview (four‑file model & roles) → ./framework-overview.md

Comment System → ./comment-system.md

Project File Guide → ./project-file.md

Chat Handoff Guide → ./handoff-guide.md

Appendix: Where configuration lives (at a glance)

Project file → COOKBOOK_CONFIG: which cookbooks are enabled; loading strategy; fallback behavior. (CFT‑PROJ‑MASTER‑TEMPLATE, 2025, Section 6)

Project file → RECIPE_CATEGORIES: category labels (e.g., CAT‑001 to CAT‑004). (CFT‑PROJ‑MASTER‑TEMPLATE, 2025, Section 6)

Chat history template: where the Handoff Snapshot recipe is referenced and how snapshots are ordered. (CFT‑PROJ‑AI‑CHAT‑HISTORY‑MASTER‑TEMPLATE, 2025)
