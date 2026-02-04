# Permissions Model — L0-L3 + C0-C3

> Two-layer security architecture for AI assistant systems

**Status:** Production (implemented)
**Version:** 1.0

---

## The Problem

As AI assistants handle more sensitive tasks, two questions arise:

1. **WHO can do what?** — Different people have different privileges
2. **WHO sees what data?** — Some data is more sensitive than others

Without a formal model, these decisions are ad-hoc and inconsistent.

---

## Core Concept

Two independent layers:

```
┌────────────────────────────────────────────────┐
│  OPERATORS (L0-L3)                             │
│  → WHO can perform actions                     │
│  → Hierarchical: higher includes lower         │
└────────────────────────────────────────────────┘

┌────────────────────────────────────────────────┐
│  CONFIDENTIALITY (C0-C3)                       │
│  → WHO can see which data                      │
│  → Fail-secure: unknown = highest restriction  │
└────────────────────────────────────────────────┘
```

---

## Operator Levels (L0-L3)

| Level | Name | Description | Sees C |
|-------|------|-------------|--------|
| **L0** | Principal | Full access, system architect | C0, C1, C2, C3 |
| **L1** | Constructor | Can build/modify system (with limits) | C0, C1 |
| **L2** | Operator | Uses system in designated scope | C0, C1 |
| **L3** | EndUser | End user (subscriber) | C0 |

### Principles

1. **Single Principal** — There is exactly one L0 (the system owner)
2. **Inheritance** — Higher levels have all permissions of lower levels
3. **Workspace Isolation** — L1-L3 see only their designated workspace

---

## Confidentiality Levels (C0-C3)

| Level | Symbol | Name | Description | Default? |
|-------|--------|------|-------------|----------|
| **C0** | 🌐 | PUBLIC | Can be shared externally | **NO** (requires decision) |
| **C1** | 📋 | INTERNAL | System operators | **YES** |
| **C2** | 🔒 | PRIVATE | Principal + designated | NO |
| **C3** | 🛡️ | CONFIDENTIAL | Principal only | NO |

### Principles

1. **Default C1** — Everything is INTERNAL unless explicitly marked
2. **C0 Requires Decision** — Nothing is PUBLIC automatically
3. **Fail-Secure** — Unknown level → treat as C3

---

## Architecture

```
┌─────────────────────────────────────────────────────────────┐
│           External Secure Storage (Source of Truth)           │
│  [secrets-folder]/operators/                                  │
│    ├── registry        ← WHO has permissions (L0-L3)         │
│    ├── principal-config ← Principal details                   │
│    └── levels-config   ← C0-C3 definitions                   │
│                                                              │
│  ⚡ AUTHORITATIVE — this is the truth                        │
└─────────────────────────────────────────────────────────────┘
                           │
                           │ (if available)
                           ▼
┌─────────────────────────────────────────────────────────────┐
│                 Local Repo (Stub + Documentation)            │
│  docs/operators/                                             │
│    ├── README           ← Level definitions (info only)      │
│    └── STUB             ← "Real registry in secure storage"  │
│                                                              │
│  ⚠️ DOES NOT CONTAIN permissions — only documentation        │
└─────────────────────────────────────────────────────────────┘
```

### Why External Storage?

| Problem | Solution |
|---------|----------|
| Someone edits local file | Doesn't grant permissions — registry is in secure storage |
| Git push exposes permissions | Secure storage is outside Git |
| Backup | Secure storage has versioning |
| Multi-device sync | Secure storage handles automatically |

---

## Fail-Secure Logic

At session start:

```
CHECK: Is secure storage available?
│
├── YES → Read OPERATORS from secure storage
│         → Normal mode
│
└── NO → FAIL-SECURE:
         → Verify Principal environment:
           • OS profile = correct user
           • Secrets folder exists
           • Project folder exists
         → If OK → limited mode
         → If NOT → NO ACCESS
```

**Key principle:** When verification fails, restrict access (don't grant it).

---

## Marking Confidentiality

### In Documents

```markdown
> **CONFIDENTIALITY:** C2 (PRIVATE)
```

### In Lists (Backlog/TODO)

```markdown
- [ ] [C2] Private task
| J-100 | [C3] Secret integration | C3 | 🔥 |
```

### In Registries

| ID | Name | C | Status |
|----|------|---|--------|
| idea-001 | Project X | C1 | 🔬 |

---

## Automatic Location Mapping

| Location | Default Level |
|----------|---------------|
| Secure external storage (secrets) | C3 |
| Secure external storage (health) | C3 |
| Knowledge base (internal) | C1 |
| Backlog (internal) | C1 |
| Public GitHub repo | C0 (after approval) |

---

## Known Risks

Security risks are documented internally. The model addresses container isolation, impersonation prevention, and privilege escalation through:
1. **Additional verification** for untrusted environments
2. **Trusted host whitelisting**
3. **Explicit remote mode** — containers operate at restricted privilege levels

---

## Integration

| Connects with | How |
|---------------|-----|
| [Procedures Registry](procedures-registry.md) | Procedures can have confidentiality levels |
| [CLAUDE.md Versioning](claude-md-versioning.md) | Instructions contain permission references |
| [Session Freeze](../methodology/session-freeze.md) | Sessions may contain confidential content |

---

## Benefits

1. **Explicit model** — No guessing who can do what
2. **Fail-secure** — Defaults to restriction, not access
3. **Separated storage** — Permissions stored outside codebase
4. **Auditable** — Changes to registry are tracked
5. **Scalable** — Works for single user or small team

---

## Limitations

- **Overhead** — More complexity than "just trust everyone"
- **Single Principal** — Designed for one owner, not committees
- **External storage dependency** — Requires cloud or secure storage
- **No fine-grained ACLs** — Levels, not per-item permissions

---

> **Source:** Internal knowledge base (Permissions Architecture)
