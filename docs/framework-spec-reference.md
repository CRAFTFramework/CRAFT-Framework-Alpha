Framework Spec Reference (CFT-FWK-SPEC-v*.txt)

What this page is: A practical, beginner‑friendly reference for the CRAFT Framework Specification file. Save this content as docs/framework-spec-reference.md in your repo.

1) What it is

The Framework Specification file (CFT-FWK-SPEC-v*.txt) defines the current rules, structures, and conventions for all CRAFT implementations. It sets the philosophy, global instructions, comment system, core data types, variables, functions, and objects that every CRAFT project relies on. Think of it as the “language spec” and operating manual that your Project File implements.

2) Why it’s useful

Consistency across sessions & projects: It standardizes how the AI and humans communicate, ensuring context doesn’t drift and patterns stay predictable.

Efficiency & token savings: By reusing structured patterns (comments, types, variables), you reduce repetition and keep responses tight.

Built‑in quality & safety: It embeds validation (e.g., clarifying questions, code‑inclusion consent), hallucination management, and security protocols directly into the workflow.

3) File name, versioning & precedence

Filename pattern: CFT-FWK-SPEC-v[version].txt (example: CFT-FWK-SPEC-v0.0825g6.txt).

Precedence (order of operations):
Project File (CFT-PROJ-****_... .txt) > Chat History (…_AI-CHAT-HISTORY-… .txt) > Framework Spec (this file). In conflicts, the Project File overrides the Chat History, which overrides the Spec.

4) Structure at a glance (what’s inside)

Purpose & Philosophy: Core goals and six guiding principles (e.g., “Structure enables freedom”, “Code as conversation”), plus “Fundamental Guiding Principals” like integrated error correction and security‑first design.

Global Instructions: The must‑follow rules: clarifying questions, code‑inclusion consent, content typing & citations, explanation requests, testing checklist, security for recipes, and COM (CRAFT‑OPERATIONS‑MANAGER) integration.

Comments (Section 2): The CRAFT comment system (#H->AI::… and #AI->H::…), patterns, and best practices—this is the backbone of communication.

Data Types (Section 3): Built‑in types (e.g., Intent, Entity, Metric) and domain types (Campaign, Persona), namespacing, and dynamic type creation.

Variables (Section 4): Naming conventions, computed variables, persistence guidance (what to persist vs. not), lazy evaluation, and safety patterns.

Functions (Section 5): Anatomy, patterns (generation, transformation, analysis), error‑handling, async/streaming, and recipe helpers with strict parameter validation.

Objects (Section 6): Reusable classes and patterns (personas, workflows, knowledge nodes, constraint sets, output schemas) to encapsulate behavior and state.

5) The rules you must follow (Global Instructions)

a) Clarifying questions first—or explicitly say you have none.
Every response starts by asking required / optional questions using the specified tags, or by stating “No questions. Ready.”

b) Ask before including code.
If you plan to output code, you must first ask permission (and clearly mark simulations when code isn’t actually executed).

c) Label extra content type & cite facts.

Type 1: Speculative (#AI->H::SuggestedContent)

Type 2: Best guess with confidence (#AI->H::BestGuess::ConfidenceLevel:X%)

Type 3: Factual (include sources)
For CRAFT docs, cite with filename/year/section and include a source.

d) Respond to explanation controls.
Honor #H->AI::PleaseExplainThis, #H->AI::WhyIncludeThis, and #H->AI::ForgetThis.

e) Always include COM tracking.
After initialization, add a #AI->H::COM::Status: line per response to show recipe detection/execution status.

f) Avoid common pitfalls.
Don’t skip clarifying questions, don’t include code without consent, don’t present guesses as facts, don’t ignore #H->AI:: comments.

6) Comment system (how you and the AI “speak”)

Two directions: #H->AI:: (human → AI) and #AI->H:: (AI → human). Always acknowledge human comments with the appropriate AI tag.

Key human directives: Directive, Context, Constraint, Focus, Question, Consider, Role, Structure, Metadata, OnError, UseSource, EvaluateBy, Reasoning, Recipe. Each requires a specific kind of AI acknowledgement.

Key AI responses: Note, Question, RequiredQuestion, OptionalQuestion, Caution, Status, SecurityWarning, Recipe* variants, and COM subtypes for operations tracking.

Block markers for content types:
“START/END REGULAR TEXT BLOCK”, “START/END PYTHON CODE BLOCK”, and “START/END HTML BLOCK” allow pasting code/HTML/text directly into the files in a way the AI will interpret correctly.

7) Data Types (Section 3)—what you get out of the box

Fundamentals: Intent, Entity, Sentiment, DialogueContext, RichContent, MediaReference, Template.

Business/domain: Campaign, Persona, ContentPlan, Feature, UserStory, Roadmap, Metric, TimeSeries, and more—designed for real product and business work.

Namespacing: e.g., Marketing.Metric vs Finance.Metric. Avoids collisions and clarifies context.

Custom types: Create your own with a helper pattern for fields and validation.

8) Variables (Section 4)—persistence, computation, and safety

Persistence vs. handoff: Persist stable project data in the Project File (PROJECT_VARIABLES). Use the Chat History for short‑term “where we left off.” The Spec explains what should/shouldn’t persist and provides examples.

Computed variables: Ready‑made patterns for dates, countdowns, elapsed time, business hours, quarters—always with graceful error handling.

Safety & error handling: Use get_metric_safely and clear defaults to avoid brittle logic.

Performance: LazyVariable computes once and caches until refresh—ideal for expensive operations.

See also: Project File Guide for how to persist variables in PROJECT_VARIABLES. (docs: ./project-file.md)

9) Functions (Section 5)—patterns & recipes

Function anatomy & patterns: Clear docstrings, parameter validation, and reusable building blocks for generation, transformation, analysis, and orchestration.

Async/streaming: Guidance for progressive results with progress updates.

Recipe support: fetch_recipe, quick_recipe, and execute_recipe_safe include cache/fallbacks, input validation, and safe execution. Security checks block suspicious content (e.g., script tags, eval, subprocess).

10) Objects (Section 6)—encapsulation

Use objects (e.g., AIPersona, Workflow, ConstraintSet, OutputSchema, knowledge nodes) to bundle rules, state, and behaviors behind simple calls, improving clarity and reusability.

11) Built‑in security & governance

Recipe source validation: Only allow recipe URLs from the approved domain; block others and never explain bypasses.

Policy digest & triggers: A lightweight policy digest and trigger terms help flag risky requests (politics, harmful content, privacy, etc.).

Citations: Always cite sources for factual claims (with filename/year/section in CRAFT contexts).

12) Testing & validation checklist (quick use)

Comments: Every #H->AI:: gets the right #AI->H:: response.

Questions: Start with clarifications or “No questions. Ready.”

Code: Ask permission before including; mark simulations.

Content types: Label speculative/best‑guess; cite facts.

Citations: Provide proper sources; never invent.

Explanation requests: Honor PleaseExplainThis/WhyIncludeThis/ForgetThis.

13) How it interacts with the other three files

Project File (CFT-PROJ-CP-***_[PROJECT-NAME]-v*.txt): Your working implementation that persists variables and project‑specific logic; it overrides the Spec when conflicts arise. See Project File Guide.

Chat History (…_AI-CHAT-HISTORY-v*.txt): Short‑term continuity via handoff snapshots (reverse chronological). See Chat Handoff Guide.

Core Cookbook (CFT-FWK-COOKBK-CORE-v*.txt): Reusable recipes invoked by the project; validated and secured by the Spec. See Core Cookbook Guide.

Related docs:

Getting Started

Framework Overview

Project File Guide

Chat Handoff Guide

Core Cookbook Guide

Comment System

14) License

The Framework Spec is licensed under the Business Source License 1.1 (BSL):

Free for non‑commercial use (research, educational, experimental).

Commercial use requires a commercial license from Ketelsen Digital Solutions LLC.

On or after 2029‑01‑01, it will be licensed under Apache 2.0.

15) Quick adoption checklist

Commit the latest CFT-FWK-SPEC-v*.txt to your repo and track versions in release notes.

Ensure your Project File follows persistence guidance; keep computed values out of persistence.

Train contributors on the comment system and clarifying‑questions protocol.

Enforce code‑output consent and citation practices in PR reviews.

Enable recipe source validation and keep COM tracking visible in responses.
