# Makelr Architecture

This document describes the code-level and system-level architecture of Makelr: how the repository is structured, how components interact, and how data flows through the system.

Makelr is a **workflow-first automation platform** designed to let users design, control, and own their automation using their own sources and AI providers.

---

## 1. Architectural Goals

Makelr is built with the following goals:

- Workflow-first: automation is an explicit, configurable pipeline, not a black box.
- User-owned: users own their sources, schedules, data, and LLM API keys.
- Composable: sources + schedules + AI + outputs = workflow.
- Extensible: new sources, providers, and steps can be added.
- Understandable: prefer transparency over hidden magic.
- Future self-hostable: avoid SaaS-only lock-in patterns.

---

## 2. High-Level System Overview

At a high level, Makelr consists of:

- Frontend (Workflow Designer UI + Console)
- Backend API (Bots, Sources, Presets, Settings, Execution control)
- Pipeline Workers (Collect → Analyze → Draft → Report)
- Storage Layer (Database + encrypted secrets)
- LLM Abstraction Layer (BYO LLM support)
- Console (Thread-based command interface)

High-level data flow:

[ User ]
   |
   v
[ Frontend (Workflow Designer / Console) ]
   |
   v
[ Backend API ]
   |
   +--> [ Storage Layer (DB + Encryption) ]
   |
   +--> [ Pipeline Jobs ]
   |          |
   |          +--> Collect (Sources)
   |          +--> Analyze (LLM)
   |          +--> Draft (LLM)
   |          +--> Report (LLM)
   |
   +--> [ LLM Provider Abstraction ]
              |
              +--> OpenAI
              +--> Anthropic
              +--> Gemini
              +--> Custom OpenAI-compatible

---

## 3. Repository Structure (Conceptual)

The repository is organized roughly into:

- client/ (or frontend/)
  - React UI
  - Workflow Designer
  - Preset Gallery & Wizard
  - Bot Detail pages
  - Console (thread-based command UI)

- server/
  - API routes
  - Auth & user scoping
  - Pipeline jobs
  - LLM abstraction layer
  - Storage access layer

- shared/
  - Shared types (e.g. chat commands, schemas)
  - Validation and constants used by both frontend and backend

- migrations/ or drizzle/
  - Database schema and migrations

This separation enforces a clear boundary between UI, API, domain logic, and persistence.

---

## 4. Frontend Architecture

The frontend acts as a **Workflow Designer and Control Plane**.

Responsibilities:

- Preset gallery & onboarding wizard
- Bot (workflow) management
- Source management
- Schedule & format configuration
- Bot detail & status views
- Report & output browsing
- Console (command-based control interface)

Key UI concepts:

- Workflow Designer: the main mental model, not a bot marketplace.
- Bots: user-owned workflow configurations.
- Presets: starting points (recipes), not final answers.
- Console: a control interface for inspecting and operating workflows.

The frontend communicates exclusively with the Backend API via HTTP/JSON.

---

## 5. Backend Architecture

The backend provides:

- Authentication & user scoping
- Bot CRUD (create, update, delete workflows)
- Source CRUD (RSS and other feed types)
- Bot settings management (schedule, format, filters, LLM config)
- Preset-based bot creation (transactional)
- Pipeline execution triggers
- Console command parsing & execution
- LLM provider resolution per bot

Key principles:

- All data is user-scoped.
- There are no global bots or shared workflows between users.
- Bot is the unit of automation.
- Topic is just a key, not a global controller.

---

## 6. Storage Layer

The storage layer manages:

- Users
- Bots
- Bot settings
- Sources
- Bot–Source links
- Presets
- Threads & chat messages
- Outputs & reports
- LLM providers (with encrypted secrets)

Security properties:

- LLM API keys are encrypted at rest (AES-256-GCM).
- User isolation is enforced at query level.
- Deleting an LLM provider safely falls back to system default or null.

Rule:

Storage never assumes a global context. Everything is scoped by user and, where relevant, by bot or thread.

---

## 7. Bot Model (Core Concept)

In Makelr, a Bot is not a chat agent.

A Bot is a workflow configuration composed of:

- Sources: where data comes from
- Schedule: when the workflow runs
- Format: how results are generated
- LLM Config: which provider & model to use
- Filters / Sections: what to include or exclude

Execution is performed by pipeline jobs, not by the bot itself.

---

## 8. Pipeline Architecture

Makelr uses a multi-stage pipeline:

1. Collect
   - Fetches items from Sources (RSS, feeds, etc.)

2. Analyze
   - Uses LLM to analyze relevance, categorize, and extract signals

3. Draft
   - Uses LLM to generate intermediate drafts (e.g., summaries, replies)

4. Report
   - Uses LLM to generate final reports or briefs

Each stage:

- Is idempotent
- Can be re-run
- Is bot-scoped
- Uses either:
  - System LLM (for system-level jobs)
  - Bot-resolved LLM (for bot-specific jobs)

---

## 9. LLM Abstraction Layer (BYO LLM)

Makelr does not hardcode a single AI provider.

Instead:

- There is a provider-agnostic interface.
- Each bot can select:
  - System default provider, or
  - A user-provided provider.
- Supported:
  - OpenAI
  - Anthropic
  - Gemini
  - Any OpenAI-compatible endpoint

Resolution flow:

1. Check bot-specific provider
2. If null, fall back to system provider
3. If still missing, block LLM-dependent operations with a clear error

---

## 10. Console (Thread-Based Command System)

The Console is a control interface, not a chatbot.

Features:

- Thread-based conversations
- Each thread maintains its own active bot context
- Supported commands:
  - list bots
  - switch bot
  - status
  - run now
  - pause / resume
  - add source / remove source
- Safety:
  - Low-confidence commands trigger clarification
  - Destructive actions require explicit confirmation

Threads and messages are persisted and scoped per user.

---

## 11. Preset System

Presets are workflow recipes, not bots.

They contain:

- Default sources
- Default schedule
- Default format
- Default sections / filters

Creating a bot from a preset:

- Runs in a single database transaction
- Creates the bot
- Creates settings
- Creates sources (including custom ones)
- Links everything atomically

Presets are onboarding tools, not opinions.

---

## 12. Security Model

- All API routes are user-scoped.
- All bot, source, thread, and message access is user-validated.
- Secrets:
  - Encrypted at rest
  - Never returned in plaintext
- Console commands:
  - Validated
  - Scoped to active thread + user
  - Protected by confirmation flows

---

## 13. What Makelr Is NOT

- Not a bot marketplace
- Not a prompt marketplace
- Not a black-box automation service
- Not a growth-hacking spam engine
- Not a shared multi-tenant bot network

Makelr is:

A tool to design, control, and own your automation workflows.

---

## 14. Future Evolution

Planned directions include:

- Plugin system for sources
- Additional pipeline stages
- Visual workflow graphs
- Self-hosting support
- Team / organization workspaces (optional)
- Workflow export / import

All future changes must preserve:

- User ownership
- Workflow transparency
- Composability
- BYO AI principle

---

## 15. Summary

Makelr’s architecture is built around one core idea:

Automation should be designed, owned, and understood by the user.

Everything else — bots, presets, console, pipelines, providers — exists to serve that principle.

---

Makelr — Build Your Automation, Your Way.
