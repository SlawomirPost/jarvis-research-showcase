# Architecture — Index

> Structural patterns for AI assistant systems

---

## Overview

These architectural patterns address **governance, security, and operational concerns** that emerge when building production AI systems.

They complement the [methodologies](../methodology/_index.md) which focus on *how to work*.

---

## Architectural Patterns

### 1. [Permissions Model (L0-L3 + C0-C3)](permissions-model.md)
**Problem:** Who can do what? Who sees what data?
**Solution:** Two-layer architecture — operator levels + data confidentiality levels

### 2. [CLAUDE.md Versioning](claude-md-versioning.md)
**Problem:** AI instructions evolve but history is lost
**Solution:** Version control for AI configuration files

### 3. [Procedures Registry](procedures-registry.md)
**Problem:** Operational knowledge scattered, inconsistent
**Solution:** Formalized procedures with IDs, statuses, and extraction mindset

---

## How They Connect

```
┌─────────────────────────────────────────────────────┐
│              PERMISSIONS MODEL                       │
│                                                      │
│  WHO: Operators (L0-L3)                             │
│  WHAT: Confidentiality (C0-C3)                      │
│                                                      │
│  → Controls access to everything below              │
└─────────────────┬───────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────┐
│            CLAUDE.md VERSIONING                      │
│                                                      │
│  AI instructions with version history               │
│  → Snapshots at significant changes                 │
│  → Changelog for decision archaeology               │
└─────────────────┬───────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────┐
│            PROCEDURES REGISTRY                       │
│                                                      │
│  Formalized operations (P-XXX-NNN)                  │
│  → Extraction Mindset: every procedure adds value   │
│  → Statuses: approved, testing, candidate           │
└─────────────────────────────────────────────────────┘
```

---

## Design Principles

### Fail-Secure
When in doubt, restrict access. Unknown operator → treat as lowest level. Unknown confidentiality → treat as highest.

### Source of Truth Separation
Permissions registry lives outside version control (OneDrive) to prevent unauthorized edits via code commits.

### Extraction Mindset
Every procedure should extract value beyond its main purpose. Document learnings, update knowledge, improve future runs.

### Version Everything
AI instructions change. Track why, not just what. Future you will thank past you.

---

## Statistics (as of 29 Jan 2026)

- **35+ procedures** defined (P-SEC, P-DOC, P-JPM, P-SESSION, etc.)
- **11 CLAUDE.md versions** archived (v1.0 → v4.3)
- **4 operator levels** (L0-L3)
- **4 confidentiality levels** (C0-C3)

---

> **Next:** Start with [Permissions Model](permissions-model.md) if security is your concern, or [CLAUDE.md Versioning](claude-md-versioning.md) for configuration management.
