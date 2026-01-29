# Unified Idea-Project System

> PRINCE2 Agile + IDEO Design Thinking hybrid for managing ideas and projects

**Status:** Production (implemented)
**Version:** 1.2

---

## The Problem

Traditional idea-to-project flows are **one-directional**:

```
idea → evaluation → project → done
```

Real creative work doesn't work this way:
- Projects get stuck and need to return to ideation
- Knowledge discovered in projects should feed back to ideas
- Ideas don't always enter through a single "capture" point

**What's missing:** Bidirectional flow between ideas and projects, connected to a knowledge system.

---

## Core Concept

Combine:
- **PRINCE2 Agile** — Gates, business cases, exception management
- **IDEO Design Thinking** — Empathize, Define, Ideate, Prototype, Test

Into a **bidirectional system** where:
- Ideas can become projects
- Projects can return to ideas (with preserved history)
- Both connect to a knowledge layer

---

## Architecture: Two Layers + Knowledge

```
┌─────────────────────────────────────────────────────┐
│                   KNOWLEDGE LAYER                    │
│  Zettelkasten ← → Backlog ← → TODO ← → Journal      │
└───────────┬─────────────────────────────┬───────────┘
            │ IN/OUT                      │ IN/OUT
            ▼                             ▼
┌───────────────────────────────────────────────────────┐
│                   IDEAS (incubator)                    │
│   🌱 Raw ↔ 🔬 Exploration ↔ 📋 Concept               │
└─────────────────────┬─────────────────────────────────┘
                      │ ↕ Gates
┌─────────────────────┴─────────────────────────────────┐
│                  PROJECTS (delivery)                   │
│   🎯 Pre-Project → ⚙️ Delivery → ✅ Done / ⏸️ Hold   │
└───────────────────────────────────────────────────────┘
```

---

## Layer 1: IDEAS (Incubation)

| Phase | PRINCE2 Element | IDEO Element |
|-------|-----------------|--------------|
| 🌱 **Raw** | Starting Up | Empathize |
| 🔬 **Exploration** | Initiation | Define + Ideate |
| 📋 **Concept** | Business Case draft | Prototype |

Ideas live here until they're ready for project status — or until they're archived.

## Layer 2: PROJECTS (Delivery)

| Phase | PRINCE2 Element | IDEO Element |
|-------|-----------------|--------------|
| 🎯 **Pre-Project** | Initiation | Test (market fit) |
| ⚙️ **Delivery** | Managing Stages | Test (iterate) |
| ✅ **Done** | Closing | — |
| ⏸️ **Hold** | Exception | — |

Projects can return to IDEAS (with history preserved).

---

## Flows

### Flow A: Classic (Capture → Project)

```
Raw note/inspiration
    │
    ▼
🌱 Raw idea
    │ [Worth exploring?]
    ▼
🔬 Exploration
    │ [Worth building?]
    ▼
📋 Concept ready
    │ [GATE: Business Case]
    ▼
🎯 Pre-Project → ⚙️ Delivery → ✅ Done
```

### Flow B: Knowledge → Idea

```
Zettel (knowledge)
    │ [I see practical application]
    ▼
🌱 New idea with knowledge link
```

### Flow C: Project → Idea (Backflow)

```
⚙️ Project in delivery (hit obstacle)
    │ [Gate: Exception — no resources/priority change]
    ▼
⏸️ Hold (hibernation)
    │
    ├─► [Option 1] Wait for better moment
    │
    └─► [Option 2] Return to IDEAS with history
        │
        ▼
    🌱/🔬 Back in incubation (but with lessons learned)
```

**This is the key innovation** — projects don't just die, they can return to incubation.

### Flow D: Note → Multiple Destinations

```
Raw note (from anywhere)
    │ [Analysis: what is this?]
    │
    ├──► Knowledge → Zettelkasten
    ├──► Improvement → Backlog
    ├──► Action → TODO
    ├──► Idea → IDEAS
    └──► Reflection → Journal
```

Not everything becomes an idea. The routing mechanism decides.

---

## Gates (Decision Points)

### Gate 1: Raw → Exploration
| Question | Answer |
|----------|--------|
| Worth exploring? | YES / NO |
| Do I have time for exploration? | YES / NO |

### Gate 2: Exploration → Concept
| Question | Answer |
|----------|--------|
| Problem defined? | YES / NO |
| Solution outlined? | YES / NO |
| MVP specified? | YES / NO |

### Gate 3: Concept → Pre-Project (Business Case)
| Question | Answer |
|----------|--------|
| Problem worth solving? | YES / NO |
| Resources available? | YES / NO |
| Priority sufficient? | YES / NO |
| Definition of Done clear? | YES / NO |

### Gate 4: Exception Handling
| Situation | Action |
|-----------|--------|
| Out of tolerance (time/budget) | Escalate |
| No resources | ⏸️ Hold |
| Priority change | Return to IDEAS |
| No longer relevant | ❌ Archive |

---

## Status Symbols

| Symbol | Status | Can transition to |
|--------|--------|-------------------|
| 🌱 | Raw | 🔬, ❌ |
| 🔬 | In exploration | 📋, 🌱, ❌ |
| 📋 | Concept ready | 🎯, 🔬, ⏸️, ❌ |
| 🎯 | Pre-Project | ⚙️, 📋, ⏸️ |
| ⚙️ | Delivery | ✅, ⏸️, 🔬 |
| ✅ | Done | — |
| ⏸️ | Hold | 🌱, 🔬, 📋, ❌ |
| ❌ | Archive | — |

**Note:** Most arrows are **bidirectional**.

---

## Procedures

### New Idea (P-JPM-004)

```
1. CAPTURE: Record idea (🌱)
   - Minimum: name + spark (2-3 sentences)

2. CLASSIFY: Determine type
   - A: Just spark → ideas/
   - B: With research → ideas/ + knowledge link
   - C: With sprint design → workspace/

3. CONNECT: Find relationships
   - Related zettel?
   - Related backlog item?
   - Similar idea?

4. REGISTER: Add to registry

5. NOTIFY: If hot → TODO or discussion
```

### Project → Idea Return (P-JPM-005)

```
1. EXCEPTION: Project hits obstacle

2. GATE: Principal decision
   - ⏸️ Hold (keep as project, wait)
   - 🔬 Regress (return to exploration)
   - 🌱 Reincarnate (return as new idea)
   - ❌ Archive (close)

3. PRESERVE: Keep history
   - Work log → linked
   - Lessons learned → zettel
   - Artifacts → project archive

4. UPDATE: Registry + change log
```

---

## Why This Works

### 1. Life isn't linear — projects shouldn't be either

Allowing projects to return to ideation means:
- Stuck projects get incubated, not abandoned
- Value of completed work is preserved
- No "zombie projects" that drag on forever

### 2. Knowledge feeds ideas (and vice versa)

Connecting to Zettelkasten means:
- Reading a knowledge article can spark an idea
- Completed projects produce lessons learned
- Ideas don't exist in isolation

### 3. PRINCE2 + IDEO = Structure + Creativity

| PRINCE2 provides | IDEO provides |
|------------------|---------------|
| Decision gates | Empathize with users |
| Business case rigor | Rapid prototyping |
| Exception management | Ideation techniques |
| Resource control | Learn from failure |

Together: **don't lose ideas** (PRINCE2) + **don't kill creativity** (IDEO).

### 4. Gates prevent "zombie projects"

Every transition requires conscious decision:
- Gate 1: Worth exploring?
- Gate 2: Problem and MVP clear?
- Gate 3: Business case positive?
- Gate 4: Continue despite obstacles?

---

## Integration

| Connects with | How |
|---------------|-----|
| [Zettelkasten](zettelkasten-approach.md) | Ideas link to knowledge; projects produce zettels |
| [Session Freeze](session-freeze.md) | Sessions can work on ideas or projects |
| [Pattern System](patterns-system.md) | Patterns discovered during projects |

---

> **Source:** Internal zettel 202601-113 (Unified Idea-Project System)
