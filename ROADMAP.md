# Makelr Roadmap

This document outlines the public roadmap for Makelr — an open workflow designer to build, control, and own your automation using your own sources and AI models.

The roadmap is a living document and will evolve based on user feedback, community contributions, and real-world usage.

---

## Vision

Makelr aims to become:

- A **workflow-first automation platform** (not a bot marketplace)
- A tool where users **design, own, and control** their automations
- A **BYO-AI (Bring Your Own LLM)** friendly system
- A **self-hostable, extensible, open platform**
- A bridge between **sources → schedules → AI → outputs**

---

## Phase 1 — Foundations (Completed)

- Core workflow engine (Sources → Analyze → Draft → Report)
- Bot-based workflow model
- Scheduling system
- RSS & feed ingestion
- Draft & report generation
- Manual run controls
- Dashboard & bot management UI
- Basic chat / console interface
- Open-source setup (README, LICENSE, CONTRIBUTING, CODE_OF_CONDUCT, SECURITY, POLICY)

---

## Phase 2 — Stability & Data Model (Completed)

- Improved schema & storage layer
- Output history & report management
- Safer execution boundaries
- Better UI structure (Dashboard, Bots, Sources, Reports, Console)
- Error handling and validation improvements
- Topic separation and data isolation

---

## Phase 3 — BYO LLM (Completed)

- Bring Your Own LLM provider support
- Multiple provider support (OpenAI, Anthropic, Gemini, compatible APIs)
- Encrypted API key storage
- Per-bot model selection
- System-level vs bot-level LLM resolution
- Graceful fallback when system key is missing

---

## Phase 4 — Presets & Onboarding (Completed)

- Workflow recipe (preset) gallery
- Guided wizard for creating bots from templates
- Default sources per topic
- Custom source input in wizard
- Atomic bot creation flow
- Clear positioning: "Workflow Designer", not "Bot Marketplace"
- UX copy focused on “You design your own automation”

---

## Phase 6 — Command Console & Threads (Completed)

- Thread-based command console
- Per-thread active bot context
- 8 core commands:
  - list, switch, status
  - run_now, pause, resume
  - add_source, remove_source
- Approval flow for destructive or execution commands
- Low-confidence intent clarification
- Persistence across reloads
- Legacy data migration

---

## Phase 7 — UX & Productization (In Progress / Partially Done)

- Reframed UI as "Workflow Designer"
- Landing page rewrite
- Bot detail “workflow summary” card
- Console repositioned as control interface
- Template-first onboarding UX
- Improve discoverability of:
  - Scheduling
  - Reports
  - Draft approval
  - Console commands
- Better empty states and guidance UI

Planned additions:
- In-app “How to build your first workflow” guide
- Contextual tips inside Bot Settings
- Example workflows documentation

---

## Phase 8 — Extensibility & Integrations (Planned)

- Plugin / adapter system for:
  - New source types
  - New output types
  - Custom processors
- Webhook outputs
- Email / Slack / Discord delivery
- API for external triggers
- Import / export workflow configs

---

## Phase 9 — Collaboration & Teams (Planned)

- Optional team workspaces
- Role-based access control
- Shared workflows
- Audit logs
- Approval chains for teams

---

## Phase 10 — Ecosystem & Community (Planned)

- Public workflow recipe sharing (optional)
- Community-maintained presets
- Documentation site
- Example galleries
- Contributor recognition system

---

## Principles

- Makelr is a **tool to build workflows**, not a content provider
- Users **own their data, sources, and AI keys**
- The project favors **composability over magic**
- Defaults are **starting points**, not prescriptions
- Open-source first, with sustainable governance

---

## How to Contribute

If you want to help shape Makelr’s future:

- Check `CONTRIBUTING.md`
- Open an issue for ideas or bugs
- Propose features with clear use cases
- Keep changes aligned with the workflow-first philosophy

---

## Roadmap Status Disclaimer

This roadmap represents current intentions, not promises.  
Priorities may change based on:

- User feedback
- Community contributions
- Technical constraints
- Sustainability needs

---

Build your automation. Own your workflow.  
**Makelr — Build Your Automation, Your Way.**
