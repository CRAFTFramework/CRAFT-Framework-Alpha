# A Beginner's Guide to Using CRAFT™️

## Welcome!

If you're reading this, you're about to discover something remarkable: an AI assistant that actually remembers your work from conversation to conversation. No more starting over. No more re-explaining everything. Just continuous, productive collaboration.

This guide will show you how to use CRAFT (Configurable Reusable AI Framework Technology) effectively. You don't need any programming knowledge. You don't need special software. You just need to understand a few simple concepts, and you'll be ready to work with CRAFT-enabled AI assistants.

---

## Part I: Understanding CRAFT

### Chapter 1: What is CRAFT?

#### The Problem CRAFT Solves

You've probably noticed something frustrating about AI assistants: they forget everything. You spend an entire conversation explaining your project, making decisions, and building something together. Then you come back the next day, and the AI has no memory of any of it. You have to start from scratch.

It's like working with someone who has perfect skills but complete amnesia between meetings.

#### The CRAFT Solution

CRAFT changes this. It's a framework that gives AI assistants persistent memory between conversations. When you work with a CRAFT-enabled AI:

- Your project details are remembered
- Previous decisions carry forward
- Work continues where you left off
- New AI assistants can pick up exactly where the last one stopped

Think of CRAFT as giving the AI a notebook that travels between conversations. Every AI assistant who opens that notebook can see all the previous work and continue seamlessly.

#### How Is This Possible?

CRAFT works through four simple text files that travel with your project. These files contain:
- Your project's details and current state
- A record of work from previous sessions
- The rules that make CRAFT work
- Reusable instructions for common tasks

The AI reads these files at the start of each conversation and updates them as you work. It's elegant, simple, and powerful.

---

### Chapter 2: The Four Files That Make CRAFT Work

Every CRAFT project has exactly four text files. You don't need to create or edit these files - they're managed for you. But understanding what they do will help you work more effectively with CRAFT.

#### File #1: Project Implementation
**What it looks like:** `CFT-PROJ-CP-035_BEGINNERS-GUIDE-v1a.txt`

This is your project's command center. It contains:
- **PROJECT_VARIABLES**: The information that needs to be remembered (like your project name, current status, important decisions)
- **PROJECT_INSTRUCTIONS**: Rules and preferences for how the AI should work on your project
- **Custom recipes and personas**: Specialized instructions for your specific project

Think of this as your project's brain - all the specific details that make your project unique.

#### File #2: Conversation Continuity  
**What it looks like:** `CFT-PROJ-CP-035_AI-CHAT-HISTORY-v1a.txt`

This is your project's memory. After each conversation, the AI creates a "handoff" - a detailed summary of:
- What was accomplished
- Current state of the work
- Decisions that were made
- Questions that need answers
- What should happen next

The next AI reads this handoff and continues exactly where the previous one stopped. It's like passing a baton in a relay race, except the baton contains complete instructions.

#### File #3: Framework Specification
**What it looks like:** `CFT-FWK-SPEC-v0.0825g7.txt`

This is the rulebook. It defines how CRAFT works:
- The comment system for human-AI communication
- How variables are stored and retrieved
- How handoffs are structured
- Security and safety protocols

You rarely need to think about this file - it just ensures CRAFT works consistently every time.

#### File #4: Framework Cookbook
**What it looks like:** `CFT-FWK-COOKBK-CORE-v0825c7.txt`

This contains "recipes" - pre-built instructions for common tasks like:
- Starting a new session (CHAT-INIT)
- Creating handoffs (HANDOFF_SNAPSHOT)
- Setting up new projects (PROJECT_CREATOR)

Recipes ensure complex tasks are done consistently and correctly every time.

---

## Part II: Core CRAFT Concepts

### Chapter 3: The Comment System - Your Communication Channel

CRAFT uses a special comment system for clear communication between you and the AI. These comments look different from regular chat messages and serve specific purposes.

#### Human-to-AI Comments: #H->AI::

When you see `#H->AI::` at the start of a line, that's a human giving instructions to the AI. These comments can include:

- **Directive**: Direct instructions  
  `#H->AI::Directive: (Create a summary of our progress)`

- **Context**: Background information  
  `#H->AI::Context: (This project is for internal use only)`

- **Note**: Important information  
  `#H->AI::Note: (The client prefers formal language)`

#### AI-to-Human Comments: #AI->H::

When the AI responds with `#AI->H::`, it's providing structured feedback:

- **Status**: Current activity  
  `#AI->H::Status: (Loading project files...)`

- **Question**: Needs clarification  
  `#AI->H::Question: (Should I include examples in each section?)`

- **Note**: Important observation  
  `#AI->H::Note: (Found 3 unresolved questions from last session)`

#### Why Comments Matter

This comment system creates a clear record of decisions and instructions. Unlike regular chat messages that can be ambiguous, CRAFT comments are precise and purposeful. They become part of your project's history, helping future sessions understand not just what was done, but why.

---

### Chapter 4: Variables - CRAFT's Memory System

#### What Are Variables?

In CRAFT, variables are pieces of information that need to be remembered between conversations. They're stored in the PROJECT_VARIABLES section of your project file.

For example:
```python
PROJECT_VARIABLES = {
    "GUIDE_TITLE": "A Beginner's Guide to CRAFT",
    "TARGET_AUDIENCE": "Developers new to CRAFT",
    "CURRENT_SECTION": "Introduction",
    "SECTIONS_COMPLETED": ["Introduction", "Getting Started"],
    "REVIEW_STATUS": "In Progress"
}
```

#### Types of Information Stored

Variables can store:
- **Project details**: Names, descriptions, goals
- **Current state**: What's completed, what's in progress
- **Preferences**: How you want things done
- **Lists**: Collections of items, completed tasks, ideas
- **Decisions**: Choices made that affect the project

#### How Variables Help You

When you start a new conversation, the AI reads these variables and instantly knows:
- What your project is about
- What's been completed
- What decisions have been made
- Where to continue working

You never have to re-explain your project. The AI already knows.

---

### Chapter 5: Handoffs - Seamless Continuation

#### What Is a Handoff?

A handoff is created at the end of each conversation. It's a structured summary that tells the next AI assistant exactly what happened and what needs to happen next.

A typical handoff includes:

**SESSION SUMMARY**: What was accomplished in this conversation  
**CURRENT STATE**: The exact status of all work  
**KEY DECISIONS**: Important choices made with reasoning  
**UNRESOLVED QUESTIONS**: Things that need answers  
**NEXT STEPS**: Clear priorities for the next session  

#### How Handoffs Work

1. **End of Session**: When a conversation is ending, the AI creates a handoff
2. **Stored in Continuity File**: The handoff is saved with a unique ID (like H001, H002)
3. **Next Session Starts**: The new AI reads the most recent handoff
4. **Work Continues**: The new AI picks up exactly where the last one stopped

#### The Power of Handoffs

Handoffs solve the biggest problem with AI assistants - memory loss between conversations. They ensure that:
- No work is lost
- No context is forgotten
- No decisions need to be re-made
- Progress is continuous

---

## Part III: Using CRAFT Effectively

### Chapter 6: Starting a CRAFT Session

#### What You'll See

When CRAFT initializes, you'll see status messages like:

```
#AI->H::Status: (Reading CRAFT project files)
#AI->H::Status: (Loading handoff H001)
#AI->H::Status: (CRAFT initialization complete)
#AI->H::RequiredQuestion: (What would you like to work on?)
```

This tells you:
- Files are loaded
- Previous work is retrieved
- The AI is ready to continue

#### Session Types

**New Session**: Starting a fresh project
- No previous handoffs to load
- Variables are set to initial values
- Everything begins from scratch

**Continue Session**: Picking up previous work
- Loads the most recent handoff
- Retrieves all variables
- Continues from last stopping point

**Handoff Session**: Someone else's work being transferred
- Loads their final handoff
- Inherits their project state
- You continue their work

#### Your First Interaction

After initialization, the AI will usually ask what you'd like to work on. Because it has read the handoff, it knows:
- What was being worked on
- What the next steps should be
- What questions need answers

You can simply say "continue with the next priority" and the AI will know exactly what to do.

---

### Chapter 7: Working Within a CRAFT Session

#### Making Effective Requests

When working with CRAFT, you can reference previous work naturally:

- "Continue working on the introduction section"
- "What did we decide about the format?"
- "Show me the current PROJECT_VARIABLES"
- "Update the status to 'Review Complete'"

The AI understands context from:
- The loaded variables
- The previous handoff
- The session history

#### Understanding AI Responses

CRAFT-enabled AI provides structured feedback:

**Progress Updates**
```
#AI->H::Status: (Completing Section 3 of the guide)
#AI->H::Note: (Following the outline from previous session)
```

**Using Recipes**
```
#AI->H::COM::Status: (Executing READABILITY_CHECKER_RECIPE)
#AI->H::Note: (Recipe completed - all sections pass readability standards)
```

**Referencing Previous Work**
```
#AI->H::Context: (Based on handoff H003, prioritizing tutorial creation)
```

#### Building on Previous Work

Each session builds on the last:
- Completed work stays completed
- Decisions remain consistent
- The project evolves continuously

You're not starting over - you're adding another chapter to an ongoing story.

---

### Chapter 8: Understanding Recipes

#### What Are Recipes?

Recipes are pre-written, reusable instructions for common tasks. Think of them like templates or macros that ensure complex tasks are done correctly every time.

#### Common Recipes You'll Encounter

**CHAT-INIT (Session Initialization)**
- Loads your project files
- Reads the previous handoff
- Sets up the session context
- Confirms everything is ready

**HANDOFF_SNAPSHOT (Session Ending)**
- Creates a comprehensive summary
- Documents decisions and progress
- Lists next steps
- Prepares for the next session

**PROJECT_CREATOR (New Project Setup)**
- Establishes project structure
- Sets initial variables
- Creates first handoff
- Configures project preferences

#### How Recipes Execute

When a recipe runs, you'll see:
```
#AI->H::Status: (Executing CHAT-INIT recipe)
#AI->H::Note: (Recipe parameters: session_type="continue", project_id="035")
#AI->H::Status: (Recipe completed successfully)
```

Recipes can:
- Run automatically when needed
- Be triggered by specific requests
- Accept parameters for customization
- Produce consistent, reliable results

---

## Part IV: Practical Examples

### Chapter 9: Following a CRAFT Session

Let's walk through what a typical CRAFT session looks like from start to finish.

#### Session Start

You begin a conversation with an AI that has CRAFT files attached. The AI recognizes these files and initiates:

```
#H->AI::Directive: (Initialize CRAFT session with project 035)

#AI->H::Status: (Reading CRAFT project files)
#AI->H::Status: (Found 4 CRAFT files - loading in order)
#AI->H::Status: (Loading handoff H002 from previous session)

From Handoff H002:
- Last session completed the Introduction section
- Next priority: Create Getting Started tutorial
- One unresolved question about example complexity

#AI->H::Status: (CRAFT initialization complete)
#AI->H::RequiredQuestion: (Would you like to continue with the Getting Started tutorial?)
```

#### Working Through Tasks

You confirm you want to continue:

```
You: Yes, let's create the Getting Started tutorial

#AI->H::Status: (Beginning Getting Started tutorial)
#AI->H::Note: (Using guidelines from PROJECT_VARIABLES)
#AI->H::Context: (Target audience: Complete beginners)
```

The AI creates content based on:
- Previous decisions stored in variables
- Guidelines from the project file
- Context from the handoff

#### Updating Progress

As work progresses, the AI tracks changes:

```
#AI->H::Status: (Tutorial section completed)
#AI->H::Note: (Updating PROJECT_VARIABLES)

Updated:
- CURRENT_SECTION: "Getting Started"
- SECTIONS_COMPLETED: Added "Getting Started"
- LAST_MODIFIED: "Current session"
```

#### Session End

When the conversation nears its end:

```
#AI->H::Status: (Preparing session handoff)
#AI->H::COM::Status: (Executing HANDOFF_SNAPSHOT_RECIPE)

Creating Handoff H003:
- SESSION SUMMARY: Completed Getting Started tutorial...
- CURRENT STATE: Two sections complete, ten remaining...
- KEY DECISIONS: Chose simple examples over complex...
- NEXT STEPS: Create Chapter 3 on Variables...

#AI->H::Status: (Handoff H003 created - ready for next session)
```

---

### Chapter 10: Multi-Session Project Example

Let's see how a project evolves across multiple sessions, showing CRAFT's continuous memory in action.

#### First Session: Project Setup

**What happens:**
```
#AI->H::Status: (No previous handoffs found - new project)
#AI->H::COM::Status: (Executing PROJECT_CREATOR_RECIPE)

Setting up:
- PROJECT_VARIABLES initialized
- Basic structure created
- Initial goals defined

Handoff H001 created:
"Project initialized for Beginner's Guide. Framework established.
Next: Create outline."
```

**Result**: Project exists, ready for work

#### Second Session: Building the Foundation

**What happens:**
```
#AI->H::Status: (Loading handoff H001)
#AI->H::Note: (Previous session initialized project)

Continuing from H001:
- Project structure ready
- Next step: Create outline

[Work proceeds on outline...]

Handoff H002 created:
"Outline completed with 12 sections. Structure approved.
Next: Write Introduction."
```

**Result**: Outline done, project taking shape

#### Third Session: Content Creation

**What happens:**
```
#AI->H::Status: (Loading handoff H002)
#AI->H::Note: (Outline complete, beginning content)

Continuing from H002:
- Have approved outline
- Starting with Introduction

[Introduction written...]

Handoff H003 created:
"Introduction complete. Tone established as beginner-friendly.
Next: Getting Started section."
```

**Result**: Content growing, style established

#### The Continuous Thread

Notice how each session:
- Picks up exactly where the last ended
- Builds on previous decisions
- Maintains consistency
- Never loses progress

This is CRAFT's power - true continuation across conversations.

---

## Part V: Tips and Best Practices

### Chapter 11: Getting the Most from CRAFT

#### Clear Communication

Be specific about what you want:
- **Good**: "Continue writing the Variables chapter"
- **Vague**: "Keep working on the thing"

Reference previous work when relevant:
- "Use the same format as the Introduction"
- "Follow the decision from session H002"
- "Check what we stored in PROJECT_VARIABLES"

#### Understanding Persistence

**What Gets Remembered:**
- Everything in PROJECT_VARIABLES
- All handoff content
- Decisions documented in comments
- Project structure and state

**What Doesn't Persist:**
- Casual conversation
- Temporary calculations
- Undocumented decisions
- Work not saved to variables

#### Working with Recipes

When you see recipes executing:
- Let them complete
- Provide requested information
- Trust the process
- Review the results

Recipes ensure consistency and completeness.

#### Managing Sessions

**Know When to Create Handoffs:**
- Before ending a conversation
- When switching to different work
- At natural stopping points
- When decisions are made

**Provide Context When Needed:**
- If something changed externally
- When overriding previous decisions
- If clarification would help

---

### Chapter 12: Common Questions and Troubleshooting

#### Frequently Asked Questions

**Q: Why does the AI sometimes ask for confirmation?**
A: CRAFT follows the Clarifying Questions Protocol. When instructions could be interpreted multiple ways, the AI asks for clarification to ensure it does exactly what you want.

**Q: What happens if I start a new conversation without the files?**
A: Without the CRAFT files, the AI won't have access to your project's memory. Always include all four files when starting a CRAFT session.

**Q: Can I have multiple projects?**
A: Yes! Each project has its own set of four files with unique project IDs. The AI can work on different projects in different conversations.

**Q: How do I know which handoff is most recent?**
A: Handoffs are numbered sequentially (H001, H002, H003...). The highest number is the most recent. They're also listed in reverse chronological order in the continuity file.

**Q: What's a token limit?**
A: AI conversations have a maximum length. When approaching this limit, the AI will create a handoff to continue in a new conversation.

#### Understanding CRAFT Behavior

**Automatic Recipe Execution**
Some recipes run automatically:
- CHAT-INIT when sessions start
- HANDOFF_SNAPSHOT when sessions end
- Error handling when problems occur

**COM (CRAFT Operations Manager)**
You might see:
```
#AI->H::COM::Status: (Monitoring session)
```
This is the operations manager ensuring everything runs smoothly.

**Persona Switching**
```
#AI->H::PersonaSwitch: (Activating Documentation_Writer)
```
The AI can switch personas for different tasks, like technical writing or creative work.

#### Troubleshooting Common Issues

**Issue: AI seems to have forgotten previous work**
- Check that all four files are attached
- Verify the handoff was loaded
- Ensure you're using the latest file versions

**Issue: Recipe didn't execute as expected**
- Check the recipe parameters
- Verify prerequisites are met
- Review any error messages

**Issue: Variables aren't updating**
- Confirm changes were explicitly saved
- Check that the session ended properly
- Verify the handoff was created

---

## Appendices

### Appendix A: Glossary

**CRAFT**: Configurable Reusable AI Framework Technology - A system for giving AI persistent memory

**Variable**: A piece of information stored between sessions

**Handoff**: A detailed summary created at the end of each session for the next one

**Recipe**: A reusable set of instructions for common tasks

**COM**: CRAFT Operations Manager - Monitors and manages CRAFT sessions

**Persona**: A specific personality or expertise mode the AI can adopt

**Token**: A unit of text measurement in AI conversations

**Session**: A single conversation with an AI assistant

**Framework**: The underlying structure that makes CRAFT work

**Comment**: Special formatted messages for human-AI communication

### Appendix B: Quick Reference

#### Comment Format
```
#H->AI::Type: (Your message here)
#AI->H::Type: (AI's response here)
```

#### Common Types
- Directive
- Context  
- Status
- Note
- Question

#### Recipe Names
- CHAT-INIT
- HANDOFF_SNAPSHOT
- PROJECT_CREATOR

#### File Patterns
- Project: `CFT-PROJ-CP-###_NAME-v#.txt`
- History: `CFT-PROJ-CP-###_AI-CHAT-HISTORY-v#.txt`
- Framework: `CFT-FWK-SPEC-v#.txt`
- Cookbook: `CFT-FWK-COOKBK-v#.txt`

### Appendix C: Reading CRAFT Files

#### Project File Structure
```
# PROJECT_META
Basic project information

# PROJECT_INSTRUCTIONS  
How the AI should work

# PROJECT_VARIABLES
Stored information

# Recipes and Personas
Custom project tools
```

#### Handoff Structure
```
# HANDOFF H###
META information
SESSION_SUMMARY
CURRENT_STATE
KEY_DECISIONS
UNRESOLVED_QUESTIONS
NEXT_STEPS
```

#### Finding Information
- **Current status**: Check PROJECT_VARIABLES
- **Previous work**: Read latest handoff
- **Project rules**: See PROJECT_INSTRUCTIONS
- **Available tools**: Look for recipes

---

## Conclusion

You now understand the essentials of working with CRAFT. You know:

- How CRAFT gives AI persistent memory
- What the four files do
- How to communicate using comments
- How variables store information
- How handoffs enable continuation
- How recipes automate tasks

Most importantly, you understand that CRAFT transforms AI from a forgetful assistant into a reliable collaborator with continuous memory.

Every conversation builds on the last. Every session moves your project forward. No work is ever lost.

Welcome to CRAFT. Your AI assistant is ready to remember.

---

*End of Guide*
