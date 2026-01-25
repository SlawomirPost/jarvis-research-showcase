# EKA — Event-Knowledge Architecture

> **Status:** Living Concept Document
> **Version:** 0.3

---

## Core Concept

EKA (Event-Knowledge Architecture) is a memory system for AI assistants inspired by how human memory actually works — not as a perfect database, but as an adaptive, confidence-weighted system.

---

## Key Principles

### 1. Events Create Knowledge

```
EVENT (something happened)
    ↓
OBSERVATION (pattern noticed)
    ↓
ATOM (knowledge unit created)
    ↓
WEIGHT (adjusted by outcomes)
```

Every interaction is an event. Events that repeat or have significant outcomes create knowledge atoms.

### 2. Confidence Over Certainty

Instead of binary "know/don't know":

| Confidence | Meaning | Behavior |
|------------|---------|----------|
| 0.9+ | High certainty | Act without asking |
| 0.7-0.9 | Good guess | Proceed but mention uncertainty |
| 0.5-0.7 | Hypothesis | Ask before acting |
| <0.5 | Speculation | Research first |

### 3. Versions, Not Overwrites

Knowledge evolves. Each atom can have multiple versions:

```
routine_morning_checklist_v1 (weight: 0.3)
routine_morning_checklist_v2 (weight: 0.7)  ← current best
routine_morning_checklist_v3 (weight: 0.5)  ← experimental
```

The system retrieves the highest-weighted version, not the newest.

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────┐
│                    EKA SYSTEM                        │
├─────────────────────────────────────────────────────┤
│                                                      │
│  ATOMS (knowledge units)                             │
│  ├── routines (how to do things)                    │
│  ├── insights (observations)                        │
│  ├── patterns (recurring behaviors)                 │
│  └── decisions (choices made)                       │
│                                                      │
│  EVENTS (what happened)                              │
│  ├── session_start                                  │
│  ├── action_taken                                   │
│  ├── outcome_observed                               │
│  └── session_end                                    │
│                                                      │
│  THREADS (context streams)                           │
│  ├── current active thread                          │
│  └── background threads (parked)                    │
│                                                      │
└─────────────────────────────────────────────────────┘
```

---

## Human Brain Analogies

| Human Memory | EKA Equivalent |
|--------------|----------------|
| "I feel like I know this" | Confidence score > 0.7 |
| "Let me think..." | Query vector database |
| "Oh, that reminds me!" | Eureka detection |
| "I've done this before" | Routine atom retrieval |
| "Something's different today" | Pattern deviation detection |

---

## Research Questions

1. **Optimal atom granularity** — How small should knowledge units be?
2. **Weight decay** — Should unused knowledge fade?
3. **Cross-session threading** — How to maintain narrative across days?
4. **Conflict resolution** — When two atoms contradict, which wins?

---

## Implementation Notes

Current implementation uses:
- PostgreSQL for structured atoms and events
- Vector embeddings for semantic retrieval
- MCP (Model Context Protocol) for AI integration

---

> **Next:** See [patterns-system.md](patterns-system.md) for how patterns are discovered and documented.
