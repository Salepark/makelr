# Makelr Design Principles

This document describes the product and UX design principles of Makelr.

Makelr is a **workflow-first automation builder**.  
Design decisions should always reinforce clarity, user ownership, and composability.

---

## 1. Design Goals

Makelr’s design aims to:

- Make workflows **visible and understandable**
- Keep users **in control** of data, sources, and AI
- Reduce **cognitive load** without hiding complexity
- Encourage **exploration and customization**
- Avoid **opinionated or prescriptive** automation
- Scale from **beginner-friendly** to **power-user capable**

---

## 2. Core Product Philosophy

### 2.1 Workflow First

- The primary mental model is a **workflow**, not a bot personality.
- Users should always be able to see:
  - Inputs (Sources)
  - Timing (Schedule)
  - Processing steps (Pipeline)
  - Outputs (Format / Reports)
- The UI should never suggest that “magic happens somewhere else”.

### 2.2 Ownership First

- Users own:
  - Their sources
  - Their schedules
  - Their configurations
  - Their LLM providers and API keys
- The UI must:
  - Avoid vendor lock-in language
  - Make switching providers or sources feel normal and safe
  - Never hide where data or AI comes from

### 2.3 Defaults Are Starting Points

- Presets and templates are **onboarding helpers**, not “best answers”.
- The UI should:
  - Encourage modification
  - Make customization obvious
  - Avoid implying that defaults are optimal or final

---

## 3. UX Principles

### 3.1 Clarity Over Cleverness

- Prefer explicit labels over smart guesses
- Prefer visible configuration over hidden automation
- Prefer readable layouts over compact but cryptic ones

If a feature is powerful but confusing, it must be simplified or better explained.

---

### 3.2 Progressive Disclosure

- Beginners should see:
  - Simple, safe defaults
  - Clear next steps
- Advanced users should be able to:
  - Dive deeper
  - Customize more
  - Override defaults easily

Complexity should be **available**, not **forced**.

---

### 3.3 No “Black Box” UX

- The UI must always answer:
  - What will happen?
  - When will it run?
  - Where does data come from?
  - Which AI is used?
- Avoid:
  - Vague labels like “Smart Mode”
  - One-click actions that hide consequences
  - Hidden background automation

---

### 3.4 Control Plane, Not Chat Toy

- The Console is a **control interface**, not a chatbot.
- It should:
  - Feel like operating a system
  - Support inspection, control, and execution
  - Emphasize safety (confirmation for destructive actions)
- The UI should not:
  - Pretend the system is “thinking”
  - Anthropomorphize workflows
  - Encourage blind trust in AI outputs

---

## 4. Information Architecture

### 4.1 Primary Objects

The UI revolves around these concepts:

- Workflows (Bots)
- Sources
- Schedules
- Outputs (Reports)
- Presets (Recipes)
- Console (Control)

Navigation and screens should always map back to these objects.

---

### 4.2 Bot Detail Page as the “Control Center”

The Bot detail page should:

- Summarize the entire workflow at a glance:
  - Sources
  - Schedule
  - Format
  - LLM
- Make it obvious that:
  - Everything is editable
  - Nothing is locked in
- Act as the main place for:
  - Inspection
  - Configuration
  - Manual execution

---

## 5. Preset & Onboarding Design

### 5.1 Presets Are Recipes

- Presets should be presented as:
  - “Ways to start”
  - Not “the correct solution”
- Language should emphasize:
  - Customization
  - Ownership
  - Experimentation

### 5.2 Wizard Design Principles

- The wizard should:
  - Explain what each step does
  - Show defaults clearly
  - Allow easy modification
- Source selection:
  - Should start with neutral, well-known defaults
  - Must allow user-added sources
  - Must avoid “recommended vs optional” value judgments

---

## 6. Language & Tone

- Avoid:
  - Marketing hype
  - Anthropomorphic AI language
  - “Magic”, “genius”, “auto-everything” claims
- Prefer:
  - Practical, calm, engineering-oriented language
  - Clear cause-and-effect explanations
  - Honest limitations

Example:
- Bad: “Let AI think for you”
- Good: “This workflow analyzes your sources using your selected AI model”

---

## 7. Visual Design Principles

- Favor:
  - Clean layouts
  - Clear grouping of concepts
  - Readable typography
- Avoid:
  - Overly decorative UI
  - Gamification
  - Noisy dashboards

The UI should feel like:
> A workbench, not a toy.

---

## 8. Safety & Trust by Design

- Destructive or state-changing actions must:
  - Be explicit
  - Be confirmable
- The UI should:
  - Show errors clearly
  - Explain missing configuration (e.g., no LLM provider)
  - Never silently fail

Trust is built by **predictability and transparency**.

---

## 9. Anti-Patterns (What We Avoid)

- “One-click magic” with hidden consequences
- Hard-coded opinions about “best” sources or models
- Forcing users into specific providers or workflows
- Treating bots as personalities instead of systems
- Turning Makelr into:
  - A bot store
  - A prompt store
  - A black-box AI service

---

## 10. Design Review Checklist

Before shipping a UI change, ask:

- Does this make the workflow more visible or more hidden?
- Does this increase or reduce user control?
- Is this a default or a decision?
- Can the user understand what will happen next?
- Are we adding “magic” instead of clarity?

If the answer trends toward opacity, rethink the design.

---

## 11. Summary

Makelr’s design exists to serve one principle:

> **Users should understand, control, and own their automation.**

Every screen, button, and flow should reinforce that:

- This is your workflow
- This is your data
- This is your AI
- This is your system

---

Makelr — Build Your Automation, Your Way.
