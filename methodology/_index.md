# Methodologies — Index

> Research patterns and frameworks developed during Jarvis construction

---

## Overview

These methodologies emerged from **daily use of AI assistants** over months of real work — not from isolated experiments. Each addresses a specific problem encountered when building a persistent, context-aware AI system.

---

## Core Methodologies

### 1. [Event-Knowledge Architecture (EKA)](eka-architecture.md)
**Problem:** AI treats memory as binary (know/don't know)
**Solution:** Confidence-weighted knowledge with event-driven updates

### 2. [Session Freeze & Conversation Log](session-freeze.md)
**Problem:** Context lost when AI sessions compress or restart
**Solution:** Three-layer persistence (memory → TODO → disk)

### 3. [Living Concept Document (LCD)](living-concept-document.md)
**Problem:** Documentation becomes stale, AI can't quickly resume complex topics
**Solution:** Self-documenting concepts with bootstrap sections for AI resumption

### 4. [Zettelkasten for AI Memory](zettelkasten-approach.md)
**Problem:** Traditional storage loses structure; RAG loses relationships
**Solution:** Atomic notes with explicit links and confidence levels

### 5. [Pattern Discovery System](patterns-system.md)
**Problem:** Behavioral patterns are implicit and unvalidated
**Solution:** Systematic observation → validation → integration lifecycle

### 6. [Unified Idea-Project System](unified-idea-project.md)
**Problem:** Ideas and projects are disconnected; no backflow from projects
**Solution:** PRINCE2 Agile + IDEO Design Thinking hybrid with bidirectional flows

### 7. [Context Distribution Layer (CDL)](context-distribution.md)
**Problem:** Every new agent, session, or deployment starts from zero
**Solution:** Bootstrap Packages per consumer type with 6-question Minimum Viable Context

### 8. [Beaten Paths System](beaten-paths.md)
**Problem:** Valuable work patterns are implicit and lost between sessions
**Solution:** Lifecycle system: SIGNAL → DRAFT → VALIDATED → MATURE for reproducible recipes

---

## How They Connect

```
User works with AI
        │
        ▼
┌─────────────────────────────────────────────────┐
│         SESSION FREEZE (persistence)             │
│                                                  │
│   Conversation Log → survives compression        │
│   Frozen Sessions → resume days/weeks later      │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│            EKA (memory system)                   │
│                                                  │
│   Events → Observations → Atoms                  │
│   Confidence scores → adaptive recall            │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│         ZETTELKASTEN (storage)                   │
│                                                  │
│   Atomic notes + links + confidence              │
│   Three-layer model: Quick → Deep → Graph        │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│    UNIFIED IDEA-PROJECT (workflow)               │
│                                                  │
│   Ideas ↔ Projects ↔ Knowledge                   │
│   Gate-based decisions + exception handling      │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│    CONTEXT DISTRIBUTION (scaling)                │
│                                                  │
│   Bootstrap Packages → per consumer type         │
│   "Looks Right" consistency via context injection│
└─────────────────┬───────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────┐
│    BEATEN PATHS (reproduction)                   │
│                                                  │
│   SIGNAL → DRAFT → VALIDATED → MATURE            │
│   Recipes for repeatable work                    │
└─────────────────────────────────────────────────┘
```

---

## Research Context

All methodologies are:
- **Lived Experience Research** — developed through months of daily use
- **Iteratively refined** — each has version history
- **Documented with confidence** — uncertainty is explicit
- **Open for adaptation** — designed to be modified for different contexts

---

> **Next:** Start with [EKA](eka-architecture.md) for the core memory concept, or [Context Distribution](context-distribution.md) for the scaling strategy.
