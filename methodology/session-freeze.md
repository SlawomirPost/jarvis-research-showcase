# Session Freeze & Conversation Log

> Persistence mechanisms for AI sessions across context compression

**Status:** Production (used daily)
**Version:** 1.3

---

## The Problem

AI assistants have context limits. When context is compressed (automatically or manually), valuable information is lost:

- What the user actually said (their exact words)
- The reasoning that led to decisions
- Partially completed work
- The "thread" of thought connecting multiple sessions

**Critical asymmetry:** AI's actions can be reconstructed from files and commits. The user's words cannot — once compression happens, they're gone forever.

---

## Core Concept: Three Layers of Persistence

```
┌─────────────────────────────────────────────────────────┐
│  LAYER 1: In-Memory (survives recent compression)       │
│                                                         │
│  🧵 SESSION: 031 | THREAD: S5-consolidation             │
│                                                         │
│  Marker at end of each response                         │
│  → Future AI sees which session it's in                 │
└─────────────────────────────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────────┐
│  LAYER 2: TODO Anchor (survives all compression)        │
│                                                         │
│  First TODO item includes session identifier            │
│  → Persistent even when context is minimal              │
└─────────────────────────────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────────┐
│  LAYER 3: Disk (survives everything)                    │
│                                                         │
│  Session file: FROZEN_SESSIONS/{name}-{date}.md         │
│  Terminal dump: zrzuty/{NNN}/                           │
│  → Survives crash, new conversation, restart            │
└─────────────────────────────────────────────────────────┘
```

---

## Conversation Log Format

### Log Entry Structure

```markdown
### [~HH:MM] ROLE: Brief description

**User said (verbatim):**
> exact user message preserved

**Key insights:** (optional)
1. ...

**→ JARVIS ACTION:**
- What was done in response
- Files created/modified
- Decisions made
```

### Principles

| Principle | Why |
|-----------|-----|
| **Verbatim logging** | User's words are irreproducible — preserve literally |
| **Immediate write** | Log before responding (file first, terminal second) |
| **Testimony not summary** | Don't "improve" or paraphrase — preserve the voice |
| **Never delete** | Even "useless" sessions may contain valuable patterns |

---

## Session States

```
[no session] ─"new session"─► 🟢 ACTIVE ─"freeze"─► 🔵 CHECKPOINT
                                  │                      │
                                  │          (still logging!)
                                  │                      │
                            "resume session"◄────────────┘
                                  │
                            🟢 ACTIVE (continued)
```

| Status | Meaning |
|--------|---------|
| 🟢 **Active** | Log updated in real-time |
| 🔵 **Frozen** | Checkpoint saved, **but still logging if conversation continues** |
| 📁 **Archive** | Moved to archive (file remains, learning preserved) |

### Key Distinction

"Freeze" ≠ "Stop logging"

Users often say "freeze" as a checkpoint — "save state, but I might continue." Only explicit session end stops logging.

---

## After Context Compression

When AI detects it's resuming after compression:

1. Check for session marker (`🧵 SESSION: XXX`) in recent context
2. If not found: read `_INDEX.md` to find active sessions
3. Read session log file
4. Continue logging as if nothing happened

The session file becomes the "memory" that survives compression.

---

## Persistent Threads

Sessions can belong to **persistent threads** — long-running work areas:

```
FROZEN_SESSIONS/
├── S4-meta-mechanisms/          # Strategic thread
│   ├── _BOOTSTRAP.md            # Thread context
│   ├── 018_2026-01-23.md        # Session 018
│   ├── 019_2026-01-23.md        # Session 019
│   └── ...
├── O4-publication-butyrate/     # Operational thread
└── I6-reconnaissance/           # Infrastructure thread
```

**Thread types:**
- **S** (Strategic) — How the system works (architecture, meta)
- **O** (Operational) — Actual work with clients/content
- **I** (Infrastructure) — System maintenance (docs, review, debug)

---

## Why This Matters

### The Asymmetry Problem

| Element | Reconstructable? | Why |
|---------|------------------|-----|
| **User's words** | ❌ NO | Compression destroys them. Even user can't remember exactly what they said. |
| **AI's actions** | ✅ YES | Files, commits, artifacts remain. Can be reconstructed. |

**Implication:** Real-time logging is essential for preserving user intent and context.

### Testimony vs Summary

| Approach | What it does | Result |
|----------|--------------|--------|
| **Summary** (typical AI) | Corrects typos, approximates times, shortens | Loses user's voice |
| **Testimony** (this system) | Preserves literally, precisely, with sources | Preserves user's voice |

When you return to a session weeks later, you hear **yourself** — not the AI's interpretation of you.

---

## Practical Commands

| User says | AI does |
|-----------|---------|
| "new session [topic]" | Create file, ask for goal, start logging |
| "freeze session" | Checkpoint (status → 🔵), **keep logging** if continuing |
| "end session" | Stop logging, status → 🔵 |
| "resume session 024" | Read log, continue appending |
| "what sessions?" | Show list (active + frozen) |
| "this isn't for the session" | Execute without logging |

---

## Statistics (as of 29 Jan 2026)

- **27 tracked sessions** (2 active, 25 frozen)
- **19 persistent threads** (6 strategic, 7 operational, 6 infrastructure)
- **Session 031:** 12 context compressions survived, 10h continuous work

---

## Lessons Learned

1. **Write to file before responding** — terminal output is as ephemeral as memory
2. **Log immediately** — waiting for "good moment" means lost context
3. **Preserve typos** — they're part of the authentic voice
4. **Never delete sessions** — even failed attempts contain patterns
5. **Three layers is enough** — if all three fail, terminal dump is last resort

---

## Integration

| Connects with | How |
|---------------|-----|
| [EKA](eka-architecture.md) | Sessions feed events into knowledge atoms |
| [Zettelkasten](zettelkasten-approach.md) | Session insights become zettels |
| [Pattern System](patterns-system.md) | Sessions are source material for pattern discovery |

---

> **Source:** Internal zettel 202601-090 (CONVERSATION_LOG), procedures P-SESSION-005/007/008
