# Changelog

All notable changes to Makelr will be documented in this file.

This project follows:
- Semantic Versioning (https://semver.org/)
- Keep a Changelog format (https://keepachangelog.com/)

---

## [Unreleased]

### Added
- Placeholder for upcoming features and improvements.

### Changed
- Placeholder for changes to existing functionality.

### Fixed
- Placeholder for bug fixes.

### Deprecated
- Placeholder for features planned for removal.

### Removed
- Placeholder for removed features.

### Security
- Placeholder for security-related changes.

---

## [0.7.0] - 2026-02-07

### Added
- Workflow Designer UX:
  - Dashboard reframed as workflow builder
  - Preset Gallery as “Workflow Recipes”
  - Bot Detail page shows workflow summary card (sources, schedule, format)
  - Chat renamed to Console and repositioned as control interface
- Preset Gallery & Onboarding Wizard:
  - Create bots from templates with guided steps
  - Pre-filled default workflow settings per preset
  - Custom source URL input during creation
  - Atomic bot creation via transaction
- BYO LLM (Bring Your Own LLM):
  - Support for Anthropic, OpenAI, Google, and OpenAI-compatible providers
  - Encrypted API key storage (AES-256-GCM)
  - Per-bot provider selection and optional model override
- Thread-based Console:
  - Multiple threads per user
  - Each thread has its own active bot context
  - 8 supported commands: list, switch, status, run_now, pause, resume, add_source, remove_source
  - Confirmation step for destructive or state-changing actions
  - Clarification step for low-confidence commands
- Default Sources Simplification:
  - Presets now include only neutral, widely-used public sources
  - All default sources checked ON by default
  - “Recommended / Optional” split removed
  - Clear disclaimer about user responsibility for custom sources

### Changed
- “Profiles” terminology unified to “Bots” across UI and routes (with backward-compatible alias)
- Presets repositioned from “source recommendations” to “workflow starting points”
- Daily Brief and Report prompts simplified to reduce heavy formatting and symbols
- Scheduler now gracefully handles missing system LLM key

### Fixed
- Provider deletion now safely falls back to system default
- Manual run commands now guard against missing system LLM key with clear errors
- Legacy chat messages migrated to thread-based structure
- Various UI layout and accessibility issues (gap/flex-wrap, loading states, test IDs)

### Security
- API keys for LLM providers are encrypted at rest
- Sensitive Console actions require explicit user confirmation
- Thread and user scoping enforced on command execution endpoints

---

## [0.6.0] - 2026-02-01

### Added
- Initial Bot system:
  - Sources (RSS)
  - Items collection
  - Analyze and Draft pipeline
  - Daily Brief generation
- Admin UI for:
  - Bots
  - Sources
  - Drafts
  - Reports
- Basic scheduling with node-cron
- Initial LLM integration (system-level key)

### Changed
- Introduced bot status workflow: new → analyzed → drafted → approved → posted

### Fixed
- Various stability and parsing issues in RSS ingestion

---

## [0.5.0] - 2026-01-25

### Added
- Project scaffolding:
  - React + TypeScript frontend
  - Express + TypeScript backend
  - Drizzle ORM + PostgreSQL
- Basic authentication and session handling
- Initial storage layer and schema
- First working end-to-end pipeline prototype

---

## Versioning Policy

- MAJOR version: Incompatible API or architecture changes
- MINOR version: Backward-compatible feature additions
- PATCH version: Backward-compatible bug fixes

---

Makelr — Build Your Automation, Your Way.
