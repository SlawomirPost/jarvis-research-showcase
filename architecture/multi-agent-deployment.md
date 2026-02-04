# Multi-Agent Deployment Architecture

> **Problem:** A single AI assistant can only handle one conversation at a time. Scaling requires multiple agents — each needing context, role, and security boundaries.
> **Solution:** Docker-based agents with per-role Bootstrap Packages and a Context Distribution Layer.

---

## Overview

Jarvis scales from a single terminal to a fleet of agents through three mechanisms:

1. **Federation** — multiple terminals on the same machine, coordinated via shared state
2. **Remote Agents** — Docker containers with injected context, operating independently
3. **Bootstrap Packages** — per-consumer-type context injection ensuring consistent behavior

```
┌─────────────────────────────────────────────────────────────┐
│                      JARVIS ECOSYSTEM                        │
│                                                              │
│  LOCAL MACHINE                    REMOTE HOST (Docker)       │
│  ─────────────                    ────────────────────       │
│  ┌──────────────┐                 ┌──────────────┐           │
│  │ Terminal 1   │                 │ Agent:       │           │
│  │ (Principal)  │                 │ research     │           │
│  └──────────────┘                 └──────────────┘           │
│  ┌──────────────┐                 ┌──────────────┐           │
│  │ Terminal 2   │                 │ Agent:       │           │
│  │ (research)   │                 │ devops       │           │
│  └──────────────┘                 └──────────────┘           │
│  ┌──────────────┐                 ┌──────────────┐           │
│  │ Terminal 3   │                 │ Agent:       │           │
│  │ (writer)     │                 │ maintenance  │           │
│  └──────────────┘                 └──────────────┘           │
│                                                              │
│           SHARED STATE                 MISSION BRIEF         │
│         (coordination)              (per-deployment)         │
└─────────────────────────────────────────────────────────────┘
```

---

## Federation (Local Parallel Terminals)

Multiple Claude Code terminals running simultaneously, coordinated through shared state files:

### Coordination Mechanisms

| Mechanism | Purpose | Implementation |
|-----------|---------|----------------|
| **Persona Registry** | Who is running | JSON: persona ID, skills, status |
| **Task Queue** | What to do | JSON: task assignments, priorities |
| **Locks** | Prevent conflicts | File-based: resource.lock |
| **Handoff** | Transfer work | Markdown: context + next steps |
| **Calendar** | Availability | JSON: who is active when |

### Flow

```
1. Terminal opens
2. Operator identifies persona ("I am research")
3. System confirms: persona registered, skills loaded
4. System checks task queue: "You have 1 task: [description]"
5. Work begins (with scope limited to persona's skills)
6. On completion: update task status, release locks, handoff if needed
```

### Rules

- Each persona works within its **skill scope** (research doesn't do DevOps)
- Shared state modifications require **locks** (prevent race conditions)
- Artifacts go to **type-specific locations** (zettels → Zettelkasten/, docs → OUT/)
- Task Queue is the **source of truth** for work allocation

---

## Remote Agents (Docker)

Docker containers running Claude Code with injected context, operating on a remote host:

### Architecture

```
┌─────────────────────────────────────────────┐
│  DOCKER HOST                                 │
│                                              │
│  ┌────────────────────────────────────────┐  │
│  │  OPERATOR TERMINAL                     │  │
│  │  (Claude Code + secrets + CLAUDE.md)   │  │
│  │                                        │  │
│  │  Reads: MISSION_BRIEF.md               │  │
│  │  Knows: role, scope, security          │  │
│  │  Reports: structured output            │  │
│  └────────────────────────────────────────┘  │
│                                              │
│  Volumes:                                    │
│  ├── /workspace/       (project files)       │
│  ├── /secrets/         (API keys, read-only) │
│  └── /output/          (results)             │
│                                              │
└─────────────────────────────────────────────┘
```

### MISSION_BRIEF (Per-Deployment Document)

Each remote agent receives a MISSION_BRIEF defining:

| Section | Content |
|---------|---------|
| **Identity** | Role name, specialization, constraints |
| **Mission** | What to accomplish (specific, measurable) |
| **Resources** | Available tools, APIs, data sources |
| **Output** | Expected deliverables, format, location |
| **Reporting** | How/when to report progress |
| **Boundaries** | What NOT to do, security limits |

---

## Bootstrap Packages

The Context Distribution Layer provides standardized context injection per consumer type:

| Consumer | Gets | Contributes | Constraints |
|----------|------|-------------|-------------|
| **Local Session** | Full CLAUDE.md | Everything | Full access per operator level |
| **Parallel Terminal** | Persona scope | Task artifacts | Limited to persona skills |
| **Remote Agent** | MISSION_BRIEF | Deliverables + reports | Isolated, no cross-access |
| **Maintenance Agent** | Task rules | Status updates | Read-mostly, push-only |
| **External LLM** | Prompt template | Structured output | Sandboxed, no file access |

### The "Looks Right" Principle

LLMs naturally maintain consistency with their context. A well-crafted Bootstrap Package doesn't need enforcement mechanisms — the model will produce outputs that align with the injected role, mission, and constraints.

This means:
- **No complex guardrails needed** — clear context = consistent behavior
- **Delegation is cheap** — write a good brief, get good results
- **Scaling is linear** — same package format, different content per role

---

## Security Model

### Confidentiality Levels

| Level | Access | Example |
|-------|--------|---------|
| **C0 (Public)** | Everyone | Published methodologies |
| **C1 (Internal)** | System only | Procedures, architecture |
| **C2 (Private)** | Principal only | Personal notes, reflections |
| **C3 (Confidential)** | Encrypted | API keys, credentials |

### Agent Isolation

- Each Docker agent runs in its **own container** (no cross-access)
- Secrets mounted as **read-only volumes** (can't modify or exfiltrate)
- Output goes to **designated paths** (can't write elsewhere)
- No agent can **escalate privileges** beyond its MISSION_BRIEF

---

## Scaling Path

```
PHASE 1 (Current)       PHASE 2 (Next)          PHASE 3 (Future)
─────────────────       ──────────────           ────────────────
Single machine          Docker Compose           Kubernetes
2-3 parallel terminals  5-10 remote agents       N agents on demand
Manual coordination     Shared state + locks     Message hub (NATS)
File-based handoff      Structured reports       Event sourcing
```

---

## Key Learnings

1. **Start simple** — file-based coordination works for small federations
2. **Bootstrap is everything** — the quality of context injection determines agent quality
3. **Scope prevents chaos** — personas with limited skills produce better results than omniscient agents
4. **Locks are essential** — even at small scale, race conditions on shared files cause problems
5. **MISSION_BRIEF > long instructions** — structured, focused briefs outperform verbose system prompts

---

## Related Patterns

- **[Context Distribution](../methodology/context-distribution.md)** — the distribution mechanism
- **[Permissions Model](permissions-model.md)** — L0-L3 operator levels, C0-C3 confidentiality
- **[Procedures Registry](procedures-registry.md)** — formalized operations that agents follow

---

> *"Scale by multiplication, not complication."*
