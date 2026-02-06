# Makelr Glossary

This document defines the key terms used in the Makelr project.  
The goal is to ensure that contributors, users, and maintainers share the same language and mental model.

If a term is not listed here, it should be proposed and added to keep the vocabulary consistent.

---

## Automation

A repeatable process that runs on a schedule or trigger.  
In Makelr, automation is always expressed as an explicit **workflow**, not a hidden script or magic action.

---

## Workflow

The core concept of Makelr.

A workflow is a visible, configurable pipeline composed of:

- Sources (inputs)
- Schedule (when it runs)
- LLM processing (analysis, drafting, reporting)
- Output format (what it produces)

In Makelr, workflows are implemented as **Bots**.

---

## Bot

A **workflow configuration**, not a chat agent.

A Bot defines:

- Which sources to read
- When to run
- Which LLM provider/model to use
- How to process data
- How to format outputs

A Bot does not “think” or “talk”.  
It executes a pipeline.

---

## Preset

A **workflow recipe**.

A Preset contains:

- Suggested default sources
- Default schedule
- Default output format
- Default sections or filters

Presets are **starting points**, not final solutions.  
Creating a bot from a preset copies and customizes these defaults into a user-owned Bot.

---

## Source

An **input channel** for a workflow.

Examples:

- RSS feeds
- News sites
- Community forums
- Any structured or semi-structured feed

Sources define **where data comes from** in a workflow.

---

## Schedule

Defines **when a Bot runs**.

Examples:

- Daily at 9:00
- Every 6 hours
- Manually only

The Schedule controls the timing of pipeline execution.

---

## Pipeline

The multi-stage processing flow that runs a Bot.

Default stages:

1. Collect — fetch data from Sources  
2. Analyze — use LLM to analyze and classify  
3. Draft — use LLM to generate intermediate content  
4. Report — use LLM to generate final output  

Each stage is:

- Bot-scoped
- Re-runnable
- Explicit

---

## Collect

The pipeline stage responsible for **fetching raw data** from Sources.

It does not use LLMs.  
It only gathers input items.

---

## Analyze

The pipeline stage that uses an LLM to:

- Classify items
- Score relevance
- Extract signals
- Summarize content

---

## Draft

The pipeline stage that uses an LLM to:

- Generate intermediate text
- Prepare candidate replies or summaries
- Structure content before final output

---

## Report

The pipeline stage that uses an LLM to:

- Produce the final user-facing output
- Generate briefs, summaries, or reports

---

## Output

The **result** produced by a pipeline run.

Examples:

- Daily brief
- Summary report
- Draft responses
- Analysis notes

Outputs are stored and can be reviewed later.

---

## LLM (Large Language Model)

An AI model used for text analysis and generation.

Examples:

- OpenAI models
- Anthropic Claude
- Google Gemini
- Other OpenAI-compatible models

Makelr treats LLMs as **replaceable components**, not a core dependency.

---

## LLM Provider

A configured connection to an LLM service.

A provider includes:

- API endpoint
- API key (encrypted at rest)
- Optional model override

Users can bring their own LLM providers (BYO LLM).

---

## BYO LLM (Bring Your Own LLM)

A core Makelr principle:

Users provide and control their own AI providers and API keys, instead of being locked into a single vendor.

---

## System LLM

The default LLM provider configured at the system level.

Used when:

- A bot does not specify its own provider
- System-level jobs need to run

---

## Bot LLM

An LLM provider configured **specifically for a bot**.

Takes priority over the System LLM.

---

## Console

A **command-based control interface**.

The Console is not a chatbot.  
It is used to:

- Inspect bots
- Switch active bot
- Run workflows
- Pause/resume bots
- Add/remove sources

---

## Thread

A **conversation context** inside the Console.

Each Thread has:

- Its own message history
- Its own active Bot context

Threads allow multiple independent control sessions.

---

## Command

A structured instruction entered in the Console.

Examples:

- list bots
- switch bot
- status
- run now
- pause
- add source
- remove source

Commands may require confirmation before execution.

---

## Confirmation

A safety step for **destructive or state-changing actions**.

Examples:

- Running a workflow
- Pausing a bot
- Removing a source

The system asks for explicit approval before executing.

---

## User Scope

A security boundary.

All data (bots, sources, threads, outputs) is always:

- Owned by a single user
- Queried with user-level isolation
- Never shared across users by default

---

## Workflow Designer

The main UI concept of Makelr.

It emphasizes:

- Designing workflows
- Understanding pipelines
- Customizing behavior
- Owning configuration

Not browsing bots.  
Not buying prompts.

---

## Automation Workbench

A conceptual term for what Makelr aims to be:

A place where users:

- Design
- Inspect
- Modify
- Control
- And evolve

their automation workflows.

---

## Summary

Makelr uses precise language on purpose.

- Bots are workflows
- Presets are recipes
- The Console is a control plane
- LLMs are replaceable components
- Users own their automation

This glossary exists to keep that mental model consistent as the project grows.

---

Makelr — Build Your Automation, Your Way.
