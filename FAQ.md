# Makelr FAQ

This document answers common questions about Makelr: what it is, what it is not, and how to use it.

---

## What is Makelr?

Makelr is a **workflow-first automation builder**.

It helps you design, run, and control automation workflows using:
- Your own sources
- Your own schedules
- Your own AI providers (BYO LLM)
- Your own output formats

In Makelr, a “bot” is not a chat personality.  
A “bot” is a **workflow configuration**.

---

## What problem does Makelr solve?

Most automation and AI tools today:
- Hide their pipelines
- Lock users into vendors
- Turn workflows into black boxes
- Encourage copy-paste “magic” instead of understanding

Makelr solves this by making automation:
- Visible
- Configurable
- User-owned
- Composable

You always know:
- What runs
- When it runs
- Where data comes from
- Which AI is used

---

## Is Makelr a chatbot platform?

No.

Makelr includes a **Console**, but it is a **control interface**, not a chatbot.

You use it to:
- Inspect bots
- Switch active bot
- Run workflows
- Pause or resume schedules
- Add or remove sources

It is designed for **operating workflows**, not chatting with AI.

---

## What is a “Bot” in Makelr?

A Bot is a **workflow configuration**.

It defines:
- Which sources to read
- When to run
- How to process data
- Which AI provider/model to use
- How to format outputs

It does not “think” or “talk”.  
It executes a pipeline.

---

## What is a Preset?

A Preset is a **workflow recipe**.

It provides:
- Default sources
- Default schedule
- Default output format
- Default structure

Presets are **starting points**, not final answers.  
When you create a bot from a preset, you can change everything.

---

## Do I have to use the default sources?

No.

Default sources are:
- Just common, neutral starting points

You can:
- Remove them
- Add your own
- Fully replace them

Makelr does not enforce any source choices.

---

## What does “BYO LLM” mean?

BYO LLM means **Bring Your Own LLM**.

Instead of being locked into a single AI provider:
- You can connect your own OpenAI, Anthropic, Gemini, or compatible API
- Each bot can use a different provider
- You control your own API keys

Your AI, your rules, your costs.

---

## Do you store my API keys?

Yes, but:
- They are **encrypted at rest**
- They are **never returned in plaintext**
- They are only used to execute your workflows

Makelr is designed so that **you remain the owner of your AI access**.

---

## What happens if I don’t configure any LLM?

If no LLM is available:
- LLM-dependent steps (Analyze, Draft, Report) will not run
- The UI will show a clear error and tell you what is missing

You can still:
- Configure workflows
- Manage sources
- Use non-LLM features

---

## Is Makelr a SaaS or can I self-host it?

Currently, Makelr is developed as an application, but:

- The architecture is designed to be **self-hostable**
- The project is being developed in the open
- Avoiding SaaS-only lock-in is a core design goal

Self-hosting support is part of the long-term direction.

---

## Is Makelr a bot marketplace?

No.

Makelr is:
- A **workflow builder**
- A **control plane**
- An **automation workbench**

It is not:
- A bot store
- A prompt marketplace
- A template-selling platform

Presets exist only to help you get started.

---

## Can I use Makelr for marketing / posting / promotion?

Makelr is a **general workflow tool**.

What you do with it is up to you, but:
- The product does not encourage spam or manipulation
- The Console includes confirmation steps for risky actions
- You are responsible for how you use your workflows

Makelr focuses on **building tools**, not enforcing use cases.

---

## Is there an approval step before actions run?

Yes, for sensitive or state-changing actions.

In the Console:
- Destructive or impactful commands require explicit confirmation
- Low-confidence commands trigger clarification instead of guessing

This is a **safety feature by design**.

---

## Can I run workflows manually?

Yes.

You can:
- Run a bot manually from the UI or Console
- Pause or resume scheduled runs
- Inspect previous outputs and reports

---

## How is this different from “no-code automation tools”?

Most no-code tools:
- Hide logic behind blocks
- Lock you into vendors
- Make debugging hard
- Turn workflows into opaque graphs

Makelr:
- Keeps workflows explicit
- Keeps data and AI ownership with the user
- Focuses on inspectability and control
- Treats automation as a system, not a trick

---

## Is Makelr open source?

Yes, Makelr is being developed in the open.

- The repository includes:
  - Architecture docs
  - Design principles
  - Contribution guidelines
- The goal is:
  - Transparency
  - Extensibility
  - Community-driven evolution

Check the repository for the current license and contribution model.

---

## Who is Makelr for?

Makelr is for:

- Builders who want automation without losing control
- Researchers who need repeatable, inspectable workflows
- Creators who want systems, not hacks
- Teams who care about transparency and ownership
- Individuals who don’t want black-box automation

---

## Where should I start?

Start with:

1. The Preset Gallery
2. Pick a workflow recipe
3. Customize sources and schedule
4. Connect your AI provider
5. Run and iterate

Remember:
> Presets are starting points. The workflow is yours.

---

## Summary

Makelr is:

- A workflow-first automation builder
- Focused on transparency, ownership, and control
- Not a bot marketplace or black-box AI tool
- Designed to grow with your workflows, not replace them

---

Makelr — Build Your Automation, Your Way.
