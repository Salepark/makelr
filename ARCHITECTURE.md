# Makelr Architecture

This document describes the high-level architecture of Makelr: how the system is structured, how data flows, and how the main components interact.

Makelr is designed as a **workflow-first automation platform** where users own their sources, schedules, and AI providers.

---

## 🎯 Architectural Goals

Makelr is built to be:

- **Workflow-first**: Bots are workflows, not magic black boxes
- **User-owned**: Users own sources, data, and LLM API keys
- **Composable**: Sources + Schedules + AI + Outputs = Workflow
- **Extensible**: New sources, providers, and steps can be added
- **Understandable**: No hidden pipelines, no opaque automation
- **Self-hostable** (future-proof): Architecture avoids SaaS lock-in

---

## 🧱 High-Level Overview

At a high level, Makelr consists of:

- Frontend (Workflow Designer UI)
- Backend API (Workflow + Bot + Source management)
- Pipeline Workers (Collect → Analyze → Draft → Report)
- Storage Layer (Database + encrypted secrets)
- LLM Abstraction Layer (BYO LLM support)
- Console (Thread-based command interface)

