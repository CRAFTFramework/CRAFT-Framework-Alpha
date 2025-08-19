CRAFT Comment System

File: docs/comment-system.md
Audience: Beginners implementing CRAFT in repos

Note: This guide summarizes and operationalizes the official CRAFT Framework Specification’s comment system. When in doubt, the Spec is the source of truth.

What it is (and how to think about it)

The CRAFT Comment System is a lightweight markup you and the AI both use inside chats and project files to make instructions explicit, routable, and auditable.
You write comments that start with #H->AI::… (human → AI), and the AI must respond with #AI->H::… using the most specific response type available. Think of it like structured headers for a conversation, not code.

Why it’s useful

Eliminates ambiguity: Every instruction carries a clear intent (Directive, Context, Constraint, etc.).

Forces acknowledgments: The AI must acknowledge and act on each human comment type.

Enables QA: You can audit who said what and why across sessions and files.

Pairs with persistence & handoff: Works with the four-file model so sessions stay aligned.

The two directions (syntax you’ll actually use)
Human → AI (you write these)

Prefix your instruction with #H->AI::Type: and put your content in parentheses.

Common types

#H->AI::Directive: (Do X now…)

#H->AI::Context: (Background info…)

#H->AI::Constraint: (Do not exceed 500 words…)

#H->AI::Structure: (Return as bullets with headings…)

#H->AI::Question: (What’s the ETA?)

#H->AI::Role: (Act as Technical Writer…)

#H->AI::UseSource: (Prioritize Spec v0.0825g6…)

#H->AI::OnError: (If blocked, propose two alternatives…)

AI → Human (the assistant must use these)

#AI->H::Note: (Acknowledgment + action)

#AI->H::RequiredQuestion: (Blocks progress until answered)

#AI->H::OptionalQuestion: (Helpful, not blocking)

#AI->H::Caution: (Risk/limitation)

#AI->H::Status: (Progress update)

#AI->H::RecipeFound / RecipeExecuting / RecipeStatus (Recipe lifecycle)

#AI->H::SecurityWarning: (Security block on recipes)

#AI->H::COM::Status: (Operations Manager tracking — must appear once per response)

Quick Start (60-second setup)

Copy this starter block into the top of any instruction you give the AI:

#H->AI::Directive: (Follow the CRAFT comment system for this task)
#H->AI::Constraint: (Acknowledge each #H->AI:: comment with the most specific #AI->H:: response)
#H->AI::Structure: (Use headings + bullets, include one #AI->H::COM::Status at end)


Then:

Write your actual instruction using the types above.

Expect an acknowledgment (#AI->H::Note: or a more specific response) before content.

Look for COM tracking at the bottom of every response:
#AI->H::COM::Status: (…status text…)

Must-follow companion rules (you’ll see these in the Spec)

Clarifying questions protocol:
Start every task with either “No questions. Ready.” or explicit #AI->H::RequiredQuestion: / #AI->H::OptionalQuestion:. This reduces back-and-forth and keeps scope tight.

Code inclusion rule:
If code will be included, the AI should first ask:
#AI->H::Question: (I will be including code in my response. Should I proceed?)
If execution is simulated, the AI must prefix with “SIMULATION:”.

Content labeling:
Require the AI to mark speculative vs. factual content with:

#AI->H::SuggestedContent:(…) for speculative

#AI->H::BestGuess::ConfidenceLevel:XX%:(…) for estimates

Factual claims must include citations.

Citations:
Use APA-style references to CRAFT files in prose and include inline citation markers when referencing specific sections of the Spec.

Recipe security (recipes only):
If a recipe URL doesn’t match the allowed domain, the AI must block execution with #AI->H::SecurityWarning:. (General web access is still allowed; this check is recipe-specific.)

Comment types — Complete reference (copy/paste cheat-sheet)
Human → AI (you)

Directive – “Do this”

Context – “Here’s background”

Constraint – “Don’t exceed/avoid/limit…”

Structure – “Output format”

Question – “Answer this explicitly”

Focus – “Prioritize these aspects”

Role – “Adopt persona”

UseSource – “Prioritize specific files/sections”

EvaluateBy – “What ‘good’ looks like”

OnError – “Fallback plan”

Metadata / Consider – “Record/Factor in”

Recipe – “Execute recipe X with Y params”

AI → Human (assistant)

Note / Status / Caution / Question (incl. Required / Optional)

RecommendedChange / RecommendMakingThisAFunction / Variable / Object

RecipeFound / RecipeExecuting / RecipeStatus / RecipeSuggestion / RecipeWarning

SecurityWarning / PolicyCaution / PolicyBlock / PolicySuggestion

COM::Status (required once per response)

Patterns you’ll use a lot
Pattern: Question differentiation
#AI->H::RequiredQuestion: (What is the exact output format you need?)
#AI->H::OptionalQuestion: (Any preferred tone or examples to emulate?)

Pattern: Multi-directive handling
#H->AI::Context: (We’re documenting the repo)
#H->AI::Directive: (Draft the README sections)
#H->AI::Constraint: (≤ 200 words per section)

#AI->H::Note: (Context acknowledged; proceeding under 200-word limit)

Pattern: Error handling
#H->AI::Directive: (Access multiple URLs simultaneously)

#AI->H::Caution: (Platform limitation—sequential access only)
#AI->H::RecommendedChange: (Process URLs one by one across steps)


(These are lifted from Spec examples and phrased for quick application.)

Block markers for mixed content (when pasting into files)

Use these markers to clearly label the content type inside project files:

### START REGULAR TEXT BLOCK ###
...plain text / instructions...
### END REGULAR TEXT BLOCK  ###

### START PYTHON CODE BLOCK ###
# python code here
### END PYTHON CODE BLOCK ###

### START HTML BLOCK ###
<!-- HTML here -->
### END HTML BLOCK ###


When you reference a file line, include a note like:
#AI->H::((Refer to line 20 in CFT-FWK-SPEC-v0.0825g6.txt)) for traceability.

Enforcement tips (for your repo)

PR checklist: “Does this PR use CRAFT comment types in prompts/docs?”

Issue template: Include a small “Use CRAFT comment headers” section.

Docs linter (manual): Scan for missing #AI->H::COM::Status in example replies.

Team habit: Begin work items with
#H->AI::Directive: + #H->AI::Constraint: + #H->AI::Structure:.

Minimal “starter prompt” (paste into new tasks)
#H->AI::Directive: (Complete the requested task)
#H->AI::Context: (Use CRAFT comment system & COM tracking)
#H->AI::Constraint: (Be concise; cite any factual claims from the Spec)
#H->AI::Structure: (Headings + bullets; include one final #AI->H::COM::Status)

FAQ (fast answers)

Do I always need COM tracking?
Yes—include one #AI->H::COM::Status: per AI response after initialization.

When should the AI ask questions vs. proceed?
Begin with either “No questions. Ready.” or use RequiredQuestion/OptionalQuestion to clarify.

Can I mix speculative and factual content?
Yes, but label speculative with #AI->H::SuggestedContent: and estimates with confidence; cite factual claims.

License & source-of-truth

This project uses the Business Source License 1.1 (BSL 1.1) as attached with the four CRAFT files; non-commercial use is allowed, commercial use requires a license; converts to Apache 2.0 on the date specified in the files. See the license header in the Spec for exact terms and conversion date.
