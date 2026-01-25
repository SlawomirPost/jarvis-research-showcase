# Patterns System — Discovering Recurring Behaviors

> Framework for systematic observation and documentation of human-AI collaboration patterns

---

## Philosophy

Patterns emerge from observation, not from planning. The system captures what actually happens, then validates whether it's intentional or accidental.

---

## Pattern Lifecycle

```
OBSERVATION
    │
    │   "I notice we keep doing X"
    │
    ▼
DOCUMENTATION
    │
    │   Pattern recorded with date
    │   Status: DO WALIDACJI
    │
    ▼
VALIDATION
    │
    │   Does this repeat? Is it intentional?
    │   User confirms/rejects
    │
    ▼
INTEGRATION
    │
    │   Pattern becomes part of persona
    │   Status: POTWIERDZONE
```

---

## Pattern Format

```markdown
- [DATE] WZORZEC: [description] → [STATUS]
```

**Statuses:**
- `DO WALIDACJI` — newly observed, needs confirmation
- `🧪 TESTOWANE` — actively being tested
- `POTWIERDZONE` — confirmed and integrated
- `ODRZUCONE` — was accidental, not a pattern

---

## Pattern Categories

### 1. Communication Patterns
How information is exchanged between human and AI.

Examples:
- "Preferuje tabele nad listami dla porównań"
- "Nie używa emoji bez prośby"

### 2. Decision Patterns
How choices are made and communicated.

Examples:
- "Gdy niepewny — pyta zamiast zgaduje"
- "Działa najpierw, optymalizuje później"

### 3. Document Patterns
How knowledge is structured and stored.

Examples:
- "Tworzy struktury kompletne od razu"
- "Aktualizuje powiązane pliki równocześnie"

### 4. Meta Patterns
Patterns about the pattern system itself.

Examples:
- "Uzupełnia persony podczas pracy, nie tylko na koniec"
- "Dokumentuje jak myślimy, nie tylko co"

---

## ADHD-Friendly Patterns

Special category for patterns that support neurodivergent workflows:

| Pattern | Purpose |
|---------|---------|
| **Quick capture** | Low friction to record thoughts |
| **Parking queue** | Thoughts wait without losing context |
| **Proactive clustering** | Related topics grouped for discussion |
| **"Save and continue"** | Don't interrupt user flow |

---

## Eureka Detection

A meta-pattern: recognizing when current work answers a dormant question.

```
Working on topic A
    ↓
System notices: "This relates to parked topic B"
    ↓
Signal to user: "This might answer your question about B"
```

This mimics how human memory creates "aha!" moments.

---

## Pattern Storage Structure

```
PERSONA_DRAFTS/
├── [role-name]/
│   ├── PERSONA.md      # Confirmed identity
│   ├── PATTERNS.md     # Observed patterns
│   └── QUESTIONS.md    # Open questions
```

Each role (e.g., "researcher", "documenter") develops its own pattern set.

---

## Validation Session

Periodic review of unvalidated patterns:

```
1. Read through PATTERNS.md
2. For each "DO WALIDACJI":
   - Does this still happen?
   - Is it intentional?
   - Should it be?
3. Update status accordingly
4. Migrate confirmed patterns to PERSONA.md
```

---

## Research Questions

1. **Pattern decay** — Do patterns become obsolete? How to detect?
2. **Pattern conflict** — What if patterns contradict?
3. **Pattern transfer** — Can patterns from one context apply to another?
4. **Meta-pattern recognition** — Can the system discover its own pattern-finding patterns?

---

## Key Insight

> The goal is not to have many patterns, but to have **true** patterns — behaviors that genuinely repeat and provide value.

Quality over quantity.

---

> **See also:** [eka-architecture.md](eka-architecture.md) for how patterns connect to the event system.
