# Makelr Development Guide

This document explains how to set up the Makelr development environment, understand the codebase, and contribute safely and effectively.

Makelr is a workflow-first automation platform. The codebase is designed to be readable, extensible, and contributor-friendly.

---

## 1. Tech Stack (Current)

- Frontend: React + TypeScript
- Backend: Node.js + TypeScript
- API: REST (JSON)
- Database: PostgreSQL
- ORM: Drizzle
- Migrations: Drizzle Kit
- Auth: (Project-configured auth provider)
- LLM Providers: OpenAI, Anthropic, Gemini, OpenAI-compatible
- Package Manager: npm (or pnpm / yarn depending on setup)
- Runtime: Node.js 18+ recommended

---

## 2. Repository Structure (High Level)

Typical structure:

- client/ (or frontend/)
  - UI components
  - Pages (Dashboard, Bots, Presets, Console, Settings, etc.)
  - API client & hooks
- server/
  - API routes
  - Auth & user scoping
  - Pipeline jobs (collect, analyze, draft, report)
  - LLM abstraction layer
  - Storage layer
- shared/
  - Shared types (e.g. chat commands, schemas)
  - Validation & constants used by both sides
- drizzle/ or migrations/
  - Database schema & migrations
- scripts/
  - Utility scripts (if any)

Exact folder names may evolve, but the separation of concerns should remain.

---

## 3. Prerequisites

Before starting:

- Node.js 18+ installed
- PostgreSQL installed and running
- Git installed
- An API key for at least one LLM provider (optional for some tasks)

---

## 4. Environment Setup

1. Clone the repository:

   git clone https://github.com/your-org/makelr.git  
   cd makelr

2. Install dependencies:

   npm install

3. Create environment file:

   Copy `.env.example` to `.env` (if provided), or create `.env` manually.

4. Configure required environment variables:

   - DATABASE_URL=postgresql://user:password@localhost:5432/makelr
   - LLM_API_KEY=your_system_default_key (optional but recommended)
   - Any auth-related keys required by the project

5. Run database migrations:

   npx drizzle-kit push

6. Start the development server:

   npm run dev

The frontend and backend should now be running in development mode.

---

## 5. Running the App

Typical commands:

- Start dev server:
  npm run dev

- Build:
  npm run build

- Start production build:
  npm start

- Run tests (if present):
  npm test

Check `package.json` for the exact scripts.

---

## 6. Key Concepts for Developers

### Bots

- A Bot is a workflow configuration, not a chat agent.
- Bots define:
  - Sources
  - Schedule
  - Output format
  - LLM provider
  - Filters / sections

### Presets

- Presets are workflow recipes.
- They are used only for onboarding / bootstrapping.
- Creating a bot from a preset is transactional.

### Pipeline

- The pipeline is multi-stage:
  - Collect → Analyze → Draft → Report
- Each stage:
  - Is bot-scoped
  - Is idempotent
  - Can be re-run

### LLM Abstraction

- Do not call providers directly from business logic.
- Always go through the provider-agnostic LLM client.
- Resolution order:
  - Bot-specific provider
  - System provider
  - Error if none available

### Console (Command System)

- The Console is not a chatbot.
- It is a command interface with:
  - Thread-based context
  - Active bot per thread
  - Confirmation flow for destructive actions

---

## 7. Database & Migrations

- Schema is defined using Drizzle.
- Migrations are managed via Drizzle Kit.
- Rules:
  - Never edit production tables manually.
  - Always create or update schema through migrations.
  - Keep migrations small and focused.

Typical workflow:

- Modify schema file
- Run:
  npx drizzle-kit push
- Verify locally
- Commit both schema and migration changes

---

## 8. Security Guidelines

- Never log or return plaintext API keys.
- All secrets must be encrypted at rest.
- All API routes must:
  - Validate user identity
  - Scope queries by userId
- Console commands must:
  - Validate intent
  - Confirm destructive actions

If you find a security issue, follow `SECURITY.md`.

---

## 9. Contribution Workflow

1. Fork the repository
2. Create a feature branch:
   git checkout -b feature/my-change
3. Make your changes
4. Ensure:
   - Code builds
   - App runs
   - No user-scope violations are introduced
5. Commit with a clear message
6. Open a Pull Request

Please read `CONTRIBUTING.md` before submitting large changes.

---

## 10. Design Principles (For Contributors)

When adding or modifying features:

- Prefer explicit workflows over hidden automation
- Avoid introducing “magic” behavior
- Preserve user ownership of data and configuration
- Keep bots understandable and inspectable
- Do not turn Makelr into:
  - A bot marketplace
  - A prompt marketplace
  - A black-box AI product

---

## 11. Where to Start Reading the Code

Recommended entry points:

- Backend:
  - server/routes (API surface)
  - server/storage (data access)
  - server/llm (provider abstraction)
  - server/jobs (pipeline stages)

- Frontend:
  - Main app/router entry
  - Preset gallery & wizard
  - Bot detail page
  - Console UI

- Shared:
  - shared types for commands and schemas

---

## 12. Philosophy Reminder

Makelr is not about shipping “smart bots”.

Makelr is about building a **transparent, user-owned automation workbench**.

When in doubt, choose:
- Clarity over cleverness
- Control over convenience
- Composability over monoliths

---

## 13. Summary

This document should help you:

- Set up the dev environment
- Understand the core architecture
- Contribute safely
- Avoid breaking core principles

If something is unclear, open an Issue or Discussion.

---

Makelr — Build Your Automation, Your Way.
