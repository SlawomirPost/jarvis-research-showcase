# Living Concept Document (LCD)

> Self-documenting concepts that enable rapid AI resumption

**Status:** Production
**Version:** 1.0

---

## The Problem

Traditional documentation has two failure modes when working with AI:

1. **Stale documentation** — Written once, becomes outdated as understanding evolves
2. **Missing context** — AI can't quickly understand where a concept "is" — what's decided, what's open, what's the current thinking

When resuming work after context compression or a new session, the AI must re-learn everything from scratch.

---

## Core Concept

A Living Concept Document (LCD) is:

> A document designed **for AI consumption** — not primarily for humans — that enables rapid context restoration and continued evolution of a concept.

Key insight: This is **memory for AI**, not just documentation for humans.

---

## Structure

Every LCD follows this pattern:

```markdown
# Concept Name

**confidence:** [0.0-1.0]
**status:** 🔴 LIVING DOCUMENT — open for expansion

---

## § BOOTSTRAP — read this first

> **For future AI:** This section lets you enter this concept's
> thinking state in 30 seconds.

### Current state (date)
Where are we: [summary]

### Core idea:
> "One sentence capturing the essence"

### How I work with this:
[Operational instructions]

### Quick comprehension test:
- [x] Key fact 1
- [x] Key fact 2

---

## § USER VOICE — what the human said

Direct quotes from user, preserved literally.
This is the "source of truth" for intent.

---

## § SHARED UNDERSTANDING — our current model

What we've agreed on, structured knowledge.

---

## § OPEN TENSIONS — unresolved questions

What's still being figured out.

---

## § EVOLUTION — how this changed

Version history with decisions and reasoning.

---

## § IMPLEMENTATION — technical details

If applicable: code, schemas, configurations.

---

## § INSTRUCTIONS — how to use this

Operational guidance for the AI.
```

---

## Key Sections Explained

### § BOOTSTRAP

**Purpose:** Let future AI enter the mental state of this concept in <30 seconds.

Contains:
- **Current state** — Where are we right now?
- **Core idea** — One-sentence essence
- **How I work** — Operational instructions
- **Quick test** — Checklist to verify understanding

This is the **most important section** — it's what gets read after every context compression.

### § USER VOICE

**Purpose:** Preserve literal user statements.

Why it matters:
- User words are **irreproducible** (unlike AI actions)
- Direct quotes capture **intent**, not just meaning
- Avoids AI interpretation drift

### § OPEN TENSIONS

**Purpose:** Document what's unresolved.

Better than pretending certainty. Explicitly tracking uncertainty:
- Prevents premature decisions
- Enables productive future discussions
- Shows intellectual honesty

### § EVOLUTION

**Purpose:** Track how thinking changed.

Not just "what changed" but **why**. Captures:
- Decisions and their reasoning
- Abandoned approaches (and why)
- Version history

---

## When to Use LCD

| Situation | Use LCD? |
|-----------|----------|
| Complex concept that evolves over time | ✅ Yes |
| Technical specification (stable) | ❌ No — traditional docs |
| Multi-session exploration | ✅ Yes |
| One-off task | ❌ No |
| Concept AI needs to "resume" later | ✅ Yes |

---

## LCD vs Traditional Documentation

| Aspect | Traditional Docs | LCD |
|--------|------------------|-----|
| **Primary audience** | Humans | AI (then humans) |
| **Update frequency** | Infrequent | Continuous |
| **Structure** | Topic-based | State-based |
| **Handles uncertainty** | Poorly | Explicitly |
| **Resumption support** | None | § BOOTSTRAP |
| **User voice** | Interpreted | Preserved literally |

---

## Example: EKA-LIVING.md

The Event-Knowledge Architecture is documented as an LCD:

```
EKA-LIVING.md
├── § BOOTSTRAP — current state, 5 pillars summary, quick test
├── § USER VOICE — 20+ literal quotes from discussions
├── § SHARED UNDERSTANDING — architecture, schema, patterns
├── § OPEN TENSIONS — unsolved problems
├── § EVOLUTION — v1.0 → v2.0 → v3.0 progression
└── § IMPLEMENTATION — SQL schema, MCP tools
```

When AI resumes EKA work, it reads § BOOTSTRAP first, then relevant sections as needed.

---

## Maintenance

### During Active Work
- Update § SHARED UNDERSTANDING as agreements form
- Add to § USER VOICE when user says something significant
- Track changes in § EVOLUTION

### After Session
- Refresh § BOOTSTRAP with current state
- Update confidence score if needed
- Note date of last significant change

### Periodic Review
- Are § OPEN TENSIONS still relevant?
- Is § BOOTSTRAP accurate?
- Should any sections be archived?

---

## Benefits

1. **Rapid resumption** — AI can continue after compression
2. **Preserved intent** — User's actual words, not interpretation
3. **Explicit uncertainty** — Known unknowns are documented
4. **Evolutionary history** — Understanding how we got here
5. **Self-documenting** — The document maintains itself

---

## Limitations

- **Overhead** — More structure than simple notes
- **AI-centric** — May be harder for humans to read casually
- **Requires discipline** — Must be maintained during work, not after
- **Best for complex concepts** — Overkill for simple things

---

## Integration

| Connects with | How |
|---------------|-----|
| [Session Freeze](session-freeze.md) | Session logs feed into LCDs |
| [Zettelkasten](zettelkasten-approach.md) | LCDs can spawn atomic zettels |
| [EKA](eka-architecture.md) | LCDs document the EKA system itself |

---

> **Source:** Internal zettel 202601-072 (Living Concept Document methodology)
