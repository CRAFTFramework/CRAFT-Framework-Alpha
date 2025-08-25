# CRAFT Tutorial Project (/tutorial)

Welcome to the beginner's tutorial for CRAFT — Configurable Reusable AI Framework Technology.

## 1) What it is

This `/tutorial` folder contains the official CRAFT Tutorial Project designed for absolute beginners. It demonstrates CRAFT's four-file architecture through an interactive, self-guided learning experience with AutoStart functionality that activates whenever you mention CRAFT to your AI assistant. See the repo's `core/` for the framework files that power this tutorial.

## 2) Why it's useful

The CRAFT Tutorial helps newcomers understand structured AI workflows through:

- **AutoStart activation** that begins automatically when you mention CRAFT.
- **Adaptive learning paths** with Quick Start (3 features) or Standard (5 features at a time) options.
- **Context-aware help system** activated anytime with "HELP" command.
- **Progress tracking** that remembers what you've learned across sessions via handoffs.
- **Beginner-friendly explanations** assuming zero prior CRAFT knowledge.

## 3) Install / Quick Start

No build step required — CRAFT runs through Python-compatible text files you share with your AI assistant.

1. **Clone / open the repo** and review its layout:
   ```
   core/        # Framework spec & cookbook (CRAFT core)
   tutorial/    # You are here (tutorial project files)
   docs/        # Documentation hub
   examples/    # Additional sample projects
   .github/     # Issue/PR templates, workflows, config
   ```

2. **Load the four CRAFT tutorial files** with your AI assistant:
   - `CFT-FWK-SPEC-v*.txt` – Framework Specification (CRAFT rules & patterns)
   - `CFT-FWK-COOKBK-CORE-v*.txt` – Core Cookbook (base recipes)
   - `CFT-PROJ-TUT-001_CRAFT-TUTORIAL-BASICS-v*.txt` – Tutorial Project Implementation
   - `CFT-PROJ-TUT-001_AI-CHAT-HISTORY-v*.txt` – Tutorial Chat Handoff file

3. **Start learning** by simply mentioning CRAFT to your AI:
   - Say something like "Let's use CRAFT" or "Initialize CRAFT"
   - The AutoStart feature will detect this and initialize the tutorial
   - Choose Quick Start (5 minutes) or Standard Tutorial (10 minutes)

4. **Use the help system** whenever you need:
   - Type "HELP" at any point for context-aware assistance
   - Say "start tutorial" to begin or resume the tutorial
   - Progress is tracked automatically between sessions

5. **Review handoff H001** in the Chat History file to see:
   - Tutorial structure and learning paths
   - Key decisions about tutorial design
   - Next steps for your learning journey

**Tip:** Start with the Quick Start mode to learn the three essential CRAFT features (Comment System, Recipe Basics, Project Structure), then explore deeper with the Standard Tutorial.

## 4) Links to docs/

- **Getting Started** → `../docs/getting-started.md`
- **Framework Overview** (four-file model & roles) → `../docs/framework-overview.md`
- **CRAFT Comment System** (H->AI / AI->H patterns) → `../docs/comment-system.md`
- **Project File Guide** → `../docs/project-file.md`
- **Chat Handoff Guide** → `../docs/handoff-guide.md`
- **Core Cookbook Guide** → `../docs/cookbook-core.md`
- **Framework Spec Reference** → `../docs/framework-spec-reference.md`
- **Examples Index** → `../examples/README.md`
- **Core Index** → `../core/README.md`

## 5) Tutorial Features

### AutoStart System
- Monitors for ANY mention of "CRAFT" in initial prompts
- Automatically executes `CHAT_SESSION_INITIALIZATION_RECIPE`
- Provides clear feedback: "CRAFT Tutorial System detected! Initializing..."

### Learning Modes
1. **Quick Start Mode** (3 essential features, ~5 minutes)
   - Comment System basics
   - Recipe fundamentals  
   - Project file structure

2. **Standard Mode** (5 features at a time, ~10 minutes)
   - Adaptive selection based on your needs
   - Examples and practice for each feature
   - Progress tracking between sessions

3. **Help Mode** (always available)
   - Context-aware assistance
   - Menu of common topics
   - Responds to "HELP" in any variation

### Core Features Covered
- Comment System (H->AI and AI->H)
- Recipe System
- Project Structure (4 files)
- Handoff System
- CRAFT-OPERATIONS-MANAGER (COM)
- Personas and Roles
- Global Instructions
- Project Variables
- Security Protocols
- Token Management
- Artifact Creation
- Framework Specification
- Cookbook Recipes
- Session Initialization
- Content Type Detection

## 6) How to contribute

1. **Read** `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md` at the repo root.
2. **For tutorial improvements**, create a branch and edit files under `/tutorial`.
3. **Test changes** with actual beginners to ensure clarity.
4. **Open an Issue** for proposals; link it in your PR.
5. **Follow style**: patient explanations, zero assumed knowledge, practical examples.
6. **Keep synced** with core framework updates and best practices.

## 7) License

This repository uses the **Business Source License 1.1 (BSL 1.1)**.

- **Non-commercial use** (research, educational, experimental) is permitted.
- **Commercial use** requires a separate license from Ketelsen Digital Solutions LLC.
- **On or after 2029-01-01**, applicable files are set to relicense to Apache 2.0.

See the root `LICENSE` for the full legal text. For commercial use, please contact Ketelsen Digital Solutions LLC to obtain a commercial license.

## 8) Alpha Software Notice

⚠️ **IMPORTANT:** CRAFT is currently in ALPHA phase. This tutorial reflects the current state as of August 2025. Features, syntax, and functionality may evolve. The tutorial focuses on stable, core features that are fundamental to CRAFT's design.

---

**Ready to start?** Load the tutorial files with your AI assistant and say "Let's use CRAFT" to begin your journey!