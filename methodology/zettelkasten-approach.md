# Zettelkasten Approach for AI Memory

> Adapting Niklas Luhmann's methodology for AI knowledge persistence

---

## Why Zettelkasten for AI?

Traditional approaches to AI memory:
- **Full context loading** — expensive, hits limits
- **RAG with chunks** — loses structure and relationships
- **Summarization** — loses detail

Zettelkasten offers:
- **Atomic units** — each note is self-contained
- **Rich linking** — relationships are explicit
- **Emergent structure** — clusters form organically
- **Confidence-aware** — each note has certainty level

---

## Zettel Structure

Each knowledge unit (zettel) contains:

```markdown
# [ID]: [Title]

**confidence:** [0.0-1.0]
**source:** [where this came from]
**version:** [iteration number]
**tags:** [@topic, @project, @type]
**status:** [stable | evolving | deprecated]

---

## Content

[The actual knowledge, kept atomic]

---

## Powiązania (Links)

- → [ID]: [why this relates]
- ← [ID]: [what points here]

---

## Historia wersji

| Version | Date | Changes |
|---------|------|---------|
| 1 | ... | Initial |
```

---

## Three-Layer Model

```
LAYER 1: Quick Reference (KNOWLEDGE.md)
    │
    │   Fast lookup, tips, settings
    │   Updated frequently
    │
    ▼
LAYER 2: Deep Knowledge (ZETTELKASTEN/)
    │
    │   Atomic notes with confidence
    │   Linked network
    │
    ▼
LAYER 3: Meta/Graph (KNOWLEDGE_GRAPH.md)
    │
    │   Relationships, clusters
    │   Emergent patterns
```

---

## Confidence Levels in Practice

| Level | Meaning | Use Case |
|-------|---------|----------|
| **0.9+** | Verified multiple times | Core procedures |
| **0.7-0.9** | Worked well, some edge cases | Standard patterns |
| **0.5-0.7** | Promising hypothesis | Experimental approaches |
| **0.3-0.5** | Initial observation | Fresh insights |
| **<0.3** | Speculation | Research directions |

---

## AI-Specific Adaptations

### 1. Living Documents

Some zettels are marked as "living" — they are expected to evolve and should not be considered finished.

```
**status:** 🔴 LIVING DOCUMENT — otwarty do rozbudowy
```

### 2. Deprecation Over Deletion

When knowledge becomes outdated:
```
**deprecated:** true
**superseded_by:** [new-zettel-id]
```

The old zettel remains for historical context.

### 3. Tag-Based Retrieval

Tags enable cross-cutting queries:
- `@_jarvis` — related to this project
- `@pattern` — behavioral pattern
- `@decision` — architectural choice
- `@wip` — work in progress

---

## Integration with EKA

Zettelkasten provides the **storage structure**.
EKA provides the **update mechanism**.

```
EVENT occurs
    ↓
EKA decides: new atom or update existing?
    ↓
Zettelkasten stores with proper linking
    ↓
Confidence adjusted based on outcome
```

---

## Lessons Learned

1. **Atomic is harder than it sounds** — tendency to over-stuff notes
2. **Links are the value** — isolated notes lose power
3. **Confidence must be updated** — stale confidence is misleading
4. **Tags need discipline** — proliferation reduces usefulness

---

> **Next:** See [patterns-system.md](patterns-system.md) for how patterns emerge from zettel analysis.
