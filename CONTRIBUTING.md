# Contributing to CRAFT (Alpha)

> **Status:** Early **Alpha** • **Sole maintainer** with **0–2 hrs/week** • Org-wide policy for [CRAFTFramework](https://github.com/CRAFTFramework)  
> **TL;DR:** We’re keeping the contribution surface **very small** for now so we can focus on building. More avenues will open as we move from **Alpha → Beta → GA**.

---

## Why contributions are limited right now

CRAFT is a brand-new framework with evolving foundations (four-file model, comment system, cookbook, etc.). With limited weekly time (generally Mondays) I need to prioritize shipping core functionality and docs. To keep maintenance overhead near **zero**, I’m opening only the lowest-touch channels at this stage.

---

## At-a-glance: What’s open in Alpha

| Area | Alpha policy | Notes |
|---|---|---|
| **GitHub Discussions** | ✅ **Open** | Use for Q&A, ideas, and roadmap input. |
| **Issues (Bug Reports)** | ✅ **Open via Issue Form** | Must use the **Bug** form (see required fields below). |
| **Pull Requests (code/features)** | ❌ **Closed to unsolicited PRs** | PRs require **pre-approval** on a linked Issue/Discussion. |
| **PRs (tiny docs typos ≤ 5 lines)** | ✅ **Allowed** | No prior approval required; may be merged at maintainer discretion. |
| **Security reports** | ✅ **Email only** | Send to **rich.ketelsen@bestbuy.com**. Public security issues will be closed. |

**Triage cadence:** *Best-effort; we typically review on **Mondays**.*

---

## How to help **today**

### 1) Start or join a **Discussion**
- Ask questions, propose ideas, or discuss patterns/workflows you’d like to see.
- Please search first to avoid duplicates.

### 2) File a **Bug Report** (Issue Form)
Use the **Bug** issue form. The following fields are **required** so I can reproduce quickly:
- **Steps to reproduce**
- **Which four CRAFT files & versions you used** (Project file, AI-CHAT-HISTORY file, Framework Spec, Core Cookbook)
- **Expected vs actual behavior**
- **Minimal reproduction** (link to a gist or paste the exact prompts/sections you used)
- **Environment** (chat model and date of run)

> Feature requests should go to **Discussions (Ideas)** for now—**not** Issues.

### 3) Submit a **tiny docs typo PR** (≤ 5 changed lines)
- Fixes for wording/typos are welcome without pre-approval.
- For larger docs changes, please open a Discussion first.

---

## What is **not** open yet

- **Unsolicited code/feature PRs** (will be closed with a friendly note to discuss first).  
- **New example projects** via PR (will open in Beta; for now, please suggest ideas in Discussions).  
- **Expansive docs rewrites** (please discuss first).

If you believe your change is small, self-contained, and time-saving for maintainers, open a Discussion describing scope; I may tag it **approved-for-pr** before you open a PR.

---

## Security policy (summary)

- Please **email** all security or responsible disclosure reports to **rich.ketelsen@bestbuy.com**.  
- For confidentiality, **do not** open public Issues or Discussions about security.  
- Public security reports will be closed with a note to email.

---

## Maintainer bandwidth & acknowledgement

- I maintain this project **part-time** and typically review activity on **Mondays**.  
- I’m a **beginner to GitHub** and will be learning (with AI assistance) as the project evolves.  
- If replies are slow, it’s because I’m prioritizing core stability so we can welcome broader contributions sooner.

---

## Roadmap for opening contributions

**Alpha (now)**  
- Discussions open; Bug Issues via form; tiny docs typo PRs allowed.  
- No unsolicited code PRs.

**Beta (later)**  
- Open **small Docs/Examples PRs** (style & structure guidelines provided).  
- Publish **good first issues** for docs/examples.  
- Light review SLA (e.g., weekly).

**GA (later)**  
- Open **code PRs** with tests/examples, review checklist, and CI requirements.  
- Clear maintainer review & merge policy, broader labels, and contributor recognition.

---

## Low-touch templates & guardrails (either enabled now or planned)

To keep overhead near **0–2 hrs/week**, we use (or plan to use) the following:

- **Issue Forms**: *Bug* (required fields listed above) and *Docs Typo*.  
- **PR Template**: Politely explains our **Alpha** policy and asks for prior approval via linked Discussion/Issue.  
- **CODEOWNERS**: Assigns review to the maintainer by default.  
- **Branch Protection**: Requires at least one approval for merges.  
- **Stale bot (planned)**: Inactive issues auto-closed after **30 days** with a friendly reminder.

> If any of the above isn’t enabled yet, it’s on the near-term checklist; the policy still applies.

---

## How to request **pre-approval** for a PR
1. Open a **Discussion** titled `Proposal: <short name>`.  
2. Include scope, why it’s needed now, and (if bug fix) a link to the Bug Issue.  
3. I’ll label it **approved-for-pr** if it’s ready; otherwise we’ll clarify next steps.

---

## Code of Conduct & License

- **Code of Conduct:** This project follows an org-wide CoC. Please read and abide by it.  
- **License:** Unless noted otherwise, contributions land under the repository’s **Business Source License 1.1 (BSL)** with the stated future change date (Apache 2.0 on conversion). See `LICENSE` at the repo root.

---

## Thank you

Even simple acts—asking a good question, filing a high-quality bug, fixing a typo—help move CRAFT forward. Thanks for understanding the constraints during Alpha and for helping us build toward a welcoming, full-featured contribution process. 🙏

---

### Quick reference

- **Discussions:** Q&A, ideas, proposals  
- **Issues:** **Bug reports** only (form required)  
- **PRs:** Tiny docs typos only (≤ 5 lines) • All others need **pre-approval**  
- **Security:** Email **rich.ketelsen@bestbuy.com**  
- **Acknowledgement:** *Best-effort; typically **Mondays***  
- **Org-wide:** Applies to all repos under **CRAFTFramework** unless overridden locally
