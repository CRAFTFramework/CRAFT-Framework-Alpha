# CRAFT Comment System
**File:** `docs/comment-system.md`  
**Audience:** Beginners implementing CRAFT in repos

> **Note:** This guide summarizes and operationalizes the official **CRAFT Framework Specification** comment system. When in doubt, the **Spec is the source of truth**.

---

## What it is (and how to think about it)

The **CRAFT Comment System** is a lightweight markup you and the AI both use inside chats and project files to make instructions **explicit**, **routable**, and **auditable**.

- You (human) write comments that start with **`#H->AI::...`**.  
- The AI must respond with **`#AI->H::...`** in the **most specific** response type available.

Think of it like **structured headers for a conversation**, *not* code.

---

## Why it’s useful

- **Eliminates ambiguity:** Every instruction carries a clear intent (`Directive`, `Context`, `Constraint`, etc.).  
- **Forces acknowledgments:** The AI must acknowledge and act on each human comment type.  
- **Enables QA:** You can audit “who said what and why” across sessions and files.  
- **Pairs with persistence & handoff:** Works with the four-file model so sessions stay aligned.

---

## The two directions (syntax you’ll actually use)

### Human → AI (you write these)

Prefix your instruction with **`#H->AI::Type:`** and put your content in **parentheses**.

**Common types you’ll use most:**
- `#H->AI::Directive: (Do X now…)`
- `#H->AI::Context: (Background info…)`
- `#H->AI::Constraint: (Do not exceed 500 words…)`
- `#H->AI::Structure: (Return as bullets with headings…)`
- `#H->AI::Question: (What’s the ETA?)`
- `#H->AI::Role: (Act as Technical Writer…)`
- `#H->AI::UseSource: (Prioritize Spec v0.0825g6…)`
- `#H->AI::OnError: (If blocked, propose two alternatives…)`

### AI → Human (the assistant must use these)

- `#AI->H::Note: (Acknowledgment + action)`  
- `#AI->H::RequiredQuestion: (Blocks progress until answered)`  
- `#AI->H::OptionalQuestion: (Helpful, not blocking)`  
- `#AI->H::Caution: (Risk/limitation)`  
- `#AI->H::Status: (Progress update)`  
- `#AI->H::RecipeFound / RecipeExecuting / RecipeStatus: (Recipe lifecycle)`  
- `#AI->H::SecurityWarning: (Security block on recipes)`  
- `#AI->H::COM::Status: (Operations Manager tracking — **must appear once per response**)`

---

## Quick Start (60-second setup)

Copy this starter block into the top of any instruction you give the AI:

```text
#H->AI::Directive: (Follow the CRAFT comment system for this task)
#H->AI::Constraint: (Acknowledge each #H->AI:: comment with the most specific #AI->H:: response)
#H->AI::Structure: (Use headings + bullets, include one #AI->H::COM::Status at end)
