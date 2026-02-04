# Beaten Paths System

> **Problem:** Valuable work patterns are implicit — when you need to repeat something, you either guess or start from zero.
> **Solution:** A lifecycle system for capturing, validating, and maturing reproducible recipes.

---

## The Problem

Every project produces two outputs:
1. **The result** (artifact, document, system)
2. **The process** (how it was built — usually lost)

When you need to do something similar again:
- You remember fragments, not the full process
- You don't remember what pitfalls to avoid
- You can't delegate because the knowledge is in your head

---

## The Solution: Beaten Paths

A **Beaten Path** is a documented recipe for reproducing a specific type of work. It captures not just WHAT to do, but also:

- **Prerequisites** — what you need before starting
- **Steps** — ordered actions with expected outputs
- **Pitfalls** — what went wrong and how to avoid it
- **Validation** — how to know it worked

### Lifecycle

```
SIGNAL → DRAFT → VALIDATED → MATURE → ARCHIVED
  │        │         │          │         │
  │        │         │          │     Superseded
  │        │         │      Proven in 3+ uses
  │        │     Confirmed by 1 use
  │     Documented recipe
  Noticed repeatable pattern
```

| Status | Meaning | Action |
|--------|---------|--------|
| **SIGNAL** | "This might be repeatable" | Note it, attach context |
| **DRAFT** | Documented but unproven | Can be followed, expect adjustments |
| **VALIDATED** | Confirmed in at least 1 real use | Safe to delegate |
| **MATURE** | Proven in 3+ uses | Can be automated |
| **ARCHIVED** | Superseded by better approach | Keep for reference |

---

## Structure of a Beaten Path

Each path follows a standard format:

```
BP-NNN: [Name]
├── Context      — when to use this path
├── Prerequisites — what you need
├── Steps        — ordered actions
│   ├── Step 1: [action] → [expected output]
│   ├── Step 2: [action] → [expected output]
│   └── ...
├── Pitfalls     — what to watch for
├── Validation   — how to verify success
└── History      — when created, by whom, status changes
```

---

## Key Insight: Blueprints Before Proof

Beaten paths don't have to be proven to be valuable. A **DRAFT** path captures the designer's intent — even if never executed, it documents HOW something should be done, preventing the loss of design thinking.

This is especially important for:
- **Long-term projects** where execution happens weeks after design
- **Delegation** where the executor isn't the designer
- **AI agents** who need explicit instructions, not implicit knowledge

---

## Examples

### Types of Beaten Paths

| Category | Example | Value |
|----------|---------|-------|
| **Infrastructure** | "Set up new Docker agent" | Repeatable deployment |
| **Process** | "Conduct deep research session" | Consistent quality |
| **Integration** | "Connect new MCP tool" | No guesswork |
| **Documentation** | "Write methodology for showcase" | Standard output |
| **Governance** | "Create new procedure" | Follows meta-rules |

### Growth Pattern

```
Week 1:  0 paths  (building, not documenting)
Week 2:  3 paths  (first extractions)
Week 3:  23 paths (systematic capture)
```

**Observation:** Path production accelerates once the system exists — retroactive capture of existing knowledge is fast.

---

## Why This Works

| Without Beaten Paths | With Beaten Paths |
|----------------------|-------------------|
| "How did we do this last time?" | BP-015: follow steps 1-7 |
| Implicit knowledge in one person | Documented, delegatable |
| Each repetition starts fresh | Each repetition improves the path |
| Can't delegate complex work | Agent follows the recipe |

### Snowball Effect

Every beaten path:
1. Makes the NEXT similar task faster
2. Can be delegated to an AI agent
3. Captures pitfalls so mistakes aren't repeated
4. Becomes input for automation (when mature)

---

## Integration with Other Methodologies

- **[Context Distribution](context-distribution.md)** — beaten paths are part of what gets distributed to new consumers
- **[Pattern System](patterns-system.md)** — patterns become beaten paths when they're actionable
- **[Living Concept Document](living-concept-document.md)** — living docs describe concepts; beaten paths describe HOW TO DO things

---

## Research Context

The Beaten Paths system was formalized in Week 3 of the Jarvis project, after recognizing that:
1. Valuable process knowledge was being lost between sessions
2. AI agents need explicit recipes, not "figure it out"
3. The overhead of documenting is low once the format is standard
4. Retroactive capture (documenting past work) is surprisingly effective

---

> *"A beaten path is a gift from your past self to your future self."*
