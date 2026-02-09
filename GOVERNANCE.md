# Makelr Governance

This document defines how the Makelr project is governed, how decisions are made, and how contributors can participate in shaping the project.

Makelr is an open-source, workflow-first automation platform. Its governance aims to balance:

- Clear product direction
- Healthy community contribution
- Sustainable long-term development

---

## Project Mission

Makelr exists to:

- Help users **design, own, and control** their automation workflows
- Stay **workflow-first**, not a bot marketplace
- Support **Bring Your Own AI (BYO LLM)** and user-owned data
- Remain **open, extensible, and self-hostable**
- Favor **composability over magic**

All governance decisions should align with this mission.

---

## Project Structure

### 1. Project Maintainer

The project is currently led by the **Project Maintainer**:

- The original author and steward of Makelr
- Responsible for:
  - Overall product direction
  - Architecture decisions
  - Final approval of major changes
  - Release management
  - Community health and sustainability

The maintainer has final decision authority when consensus cannot be reached.

---

### 2. Core Contributors

Core Contributors are trusted contributors who:

- Have a track record of high-quality contributions
- Understand the project philosophy and architecture
- Are invited by the Maintainer (or approved by consensus)

Core Contributors can:

- Review pull requests
- Propose and discuss roadmap changes
- Help moderate issues and discussions
- Influence technical direction

They do not override the Maintainer, but they strongly shape decisions.

---

### 3. Contributors

Contributors are anyone who:

- Submits pull requests
- Reports issues
- Improves documentation
- Proposes ideas or workflows
- Helps others in discussions

All constructive contributions are welcome.

See `CONTRIBUTING.md` for contribution guidelines.

---

## Decision Making Process

### 1. Day-to-day decisions

- Handled by the Maintainer
- Includes:
  - Bug fixes
  - Small improvements
  - Refactors
  - Documentation updates

### 2. Significant changes

Examples:

- Architecture changes
- Core data model changes
- Workflow engine redesign
- Major UX direction shifts
- New platform-wide features

Process:

1. Proposal is opened as an Issue or Discussion
2. Community feedback is collected
3. Core Contributors review and discuss
4. Maintainer makes the final decision, aiming for consensus

---

## Design Principles (Non-Negotiables)

The following principles guide all decisions:

- Makelr is a **tool to build workflows**, not a content provider
- Users **own their sources, data, and AI keys**
- Defaults are **starting points**, not prescriptions
- The system should remain:
  - Modular
  - Extensible
  - Understandable
- Avoid turning Makelr into:
  - A closed SaaS trap
  - A bot marketplace
  - A black-box automation system

Any proposal violating these principles will likely be rejected.

---

## Security & Responsibility

- Security issues should follow `SECURITY.md`
- The Maintainer coordinates security fixes and disclosures
- Contributors should:
  - Avoid introducing unsafe defaults
  - Respect user data ownership
  - Avoid features that encourage abuse or deception

---

## Releases

- The Maintainer controls official releases
- Releases may include:
  - Stable releases
  - Preview / experimental features
- Not all merged features are guaranteed to ship immediately

---

## Project Evolution

Makelr’s governance may evolve as:

- The community grows
- The contributor base expands
- The project matures

Any governance changes will be:

- Proposed publicly
- Discussed openly
- Documented in this file

---

## Code of Conduct

All participants must follow:

- `CODE_OF_CONDUCT.md`

Harassment, abuse, or bad-faith behavior will not be tolerated.

---

## Contact

For governance-related questions:

- Open a GitHub Issue or Discussion
- Or contact the Maintainer through the project channels

---

Build your automation. Own your workflow.  
**Makelr — Build Your Automation, Your Way.**
