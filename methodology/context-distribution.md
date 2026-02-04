# Context Distribution Layer (CDL)

> **Problem:** Every new AI agent, session, or deployment starts from zero — doesn't know the rules, the structure, or how to contribute back.
> **Solution:** A unified distribution mechanism with per-consumer-type Bootstrap Packages.

---

## The Problem

When a system grows beyond a single session — parallel terminals, remote Docker agents, scheduled tasks, external LLMs — each new consumer needs context. Without a distribution mechanism:

- Remote agent doesn't know output paths
- Parallel terminal doesn't know what's locked
- New session doesn't know active threads
- External LLM doesn't know security boundaries

**Result:** Inconsistent behavior, duplicated work, security leaks.

---

## The Solution: Bootstrap Packages

Every consumer type gets a **Bootstrap Package** — a checklist of references (not copies) answering 6 questions:

```
╔═══════════════════════════════════════════════════════════════╗
║                  MINIMUM VIABLE CONTEXT                        ║
╠═══════════════════════════════════════════════════════════════╣
║                                                                ║
║  1. WHO AM I         — role, constraints, level               ║
║  2. WHAT DO I READ   — ordered list of files to read          ║
║  3. WHAT DO I DO     — mission (general or per-deployment)    ║
║  4. WHERE DO I WRITE — output paths                           ║
║  5. HOW DO I REPORT  — format, frequency                      ║
║  6. WHAT'S FORBIDDEN — security boundaries                    ║
║                                                                ║
╚═══════════════════════════════════════════════════════════════╝
```

### Consumer Types

| Type | Example | Bootstrap Mechanism |
|------|---------|---------------------|
| **Local Session** | New Claude Code terminal | Automatic (reads CLAUDE.md) |
| **Parallel Terminal** | Second terminal in Federation | Manual (operator identifies persona) |
| **Remote Agent** | Docker jarvis-jpm-remote | Injected (CLAUDE.md + MISSION_BRIEF) |
| **Maintenance Agent** | GitHub updater | Task-scoped (rules + security checklist) |
| **External LLM** | Future: any LLM via API | Prompt Injection Template |

---

## Key Insight: "Looks Right" Consistency

LLMs naturally strive for consistency with their context. If the bootstrap clearly defines:
- **WHO I AM** (role + constraints)
- **WHAT I'M DOING** (mission + goals)

...the model will maintain coherence throughout the session, producing outputs that "look right" — consistent with the injected role and goals.

**This is the fundamental mechanism that makes CDL work.** No enforcement needed — just clear context injection.

---

## Architecture

```
JARVIS CORE (Source of Truth)
├── LIVING/ documents        ← What to know
├── PROCEDURES/              ← How to act
├── ZETTELKASTEN/            ← Deep knowledge
└── BOOTSTRAP/               ← Per-type packages
         │
         ├──► Local Session     (reads CLAUDE.md directly)
         ├──► Parallel Terminal (reads SHARED_STATE + persona)
         ├──► Remote Agent      (receives injected package)
         ├──► Maintenance Agent (task-scoped subset)
         └──► External LLM     (prompt injection template)
```

### Contribution Rules (Universal)

Every consumer, regardless of type, follows the same contribution format:

| What | Format | Where |
|------|--------|-------|
| New knowledge | Zettel (atomic note) | Zettelkasten/ |
| New pattern | SIGNAL → DRAFT → VALIDATED | Beaten Paths/ |
| Status update | Structured report | Per-deployment target |
| Incident | Log entry | Escalation log |

---

## Why This Works

| Without CDL | With CDL |
|-------------|----------|
| Each consumer reinvents context | Standard bootstrap per type |
| Inconsistent behavior | Predictable outputs |
| No contribution path | Clear "how to give back" |
| Security by hope | Security by explicit boundaries |
| Manual onboarding | Self-service packages |

---

## Research Context

This methodology emerged from scaling Jarvis from a single-terminal system to a multi-agent federation with:
- Parallel Claude Code terminals on the same machine
- Docker-based remote agents (jarvis-jpm-remote)
- GitHub maintenance tasks
- Future: arbitrary external LLMs

The core insight — that LLMs maintain consistency with injected context — was discovered through daily use and validated across multiple deployment types.

---

## Related Methodologies

- **[Living Concept Document](living-concept-document.md)** — self-documenting concepts that CDL distributes
- **[Beaten Paths](beaten-paths.md)** — reproducible recipes that any consumer can follow
- **[Pattern System](patterns-system.md)** — how patterns are discovered and formalized

---

> *"Tell a new agent WHO it is and WHAT to do — it will figure out the rest."*
