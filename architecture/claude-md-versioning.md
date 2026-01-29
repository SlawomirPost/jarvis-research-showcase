# CLAUDE.md Versioning

> Version control for AI instruction files

**Status:** Production (11 versions archived)
**Version:** 1.0

---

## The Problem

AI assistants like Claude Code are configured through instruction files (CLAUDE.md, system prompts). These evolve:

- Rules are added as patterns emerge
- Triggers are refined
- Architecture sections grow

But typically:
- **No history** — Old versions are overwritten
- **No reasoning** — Why was this changed?
- **No archaeology** — How did we get here?

---

## Core Concept

Treat CLAUDE.md like code:

```
CLAUDE_VERSIONS/
├── _CHANGELOG.md           # All changes with reasoning
├── _EVOLUTION.md           # Narrative of how system evolved
├── CLAUDE_v1.0.md          # Snapshot at significant change
├── CLAUDE_v1.1.md
├── CLAUDE_v2.0.md
├── ...
└── CLAUDE_v4.3.md          # Current
```

---

## When to Snapshot

Create new version (P-DOC-010) when:

| Trigger | Example |
|---------|---------|
| **Major structural change** | New section, removed section |
| **New mechanism added** | Triggers, integrations |
| **Philosophy shift** | Changed approach to autonomy |
| **Breaking change** | Different behavior expected |

NOT for:
- Typo fixes
- Minor wording adjustments
- Cosmetic formatting

---

## Changelog Format

```markdown
## v4.3 (2026-01-28) — Permissions Architecture

### Added
- L0-L3 operator levels
- C0-C3 confidentiality levels
- OneDrive as Source of Truth for permissions
- Fail-secure logic (P-SEC-007)

### Changed
- Triggery section: added EKA, operators triggers
- Centralne pliki: added OPERATORS/ reference

### Why
User needed formal security model for multi-operator future.
OneDrive chosen to separate permissions from code repository.

### Decided against
- Local-only registry (too easy to edit via Git)
- Per-file ACLs (too complex for current needs)
```

---

## Version Numbering

```
MAJOR.MINOR

MAJOR: Significant architectural change
MINOR: Incremental additions within architecture
```

Examples:
- 1.0 → 1.1: Added new trigger
- 1.5 → 2.0: Restructured entire section
- 3.2 → 4.0: New paradigm (e.g., introduced LCD)

---

## Benefits

### 1. Decision Archaeology

When you wonder "why is this rule here?", check the changelog:

```
v2.1 (2026-01-19) — Added "tabela = wyrównaj" trigger

### Why
User complained about inconsistent table formatting.
AI kept generating misaligned tables.

### What we tried first
- Automatic alignment in post-processing (too slow)
- Style guide reference (AI didn't read it consistently)
```

### 2. Rollback Capability

If new rule causes problems, previous version is available.

### 3. Learning History

New team member can read `_EVOLUTION.md` to understand how system matured.

### 4. Confidence in Changes

Knowing you can rollback makes experimentation safer.

---

## Evolution Document

Beyond changelog, maintain narrative:

```markdown
# CLAUDE.md Evolution

## Phase 1: Basic Structure (v1.0 - v1.5)
Started with simple rules: project context, file locations.
Main challenge: Claude kept putting things in wrong places.

## Phase 2: Triggers (v2.0 - v2.5)
Introduced "trigger → resource" pattern.
When AI hears X, it reads resource Y before acting.
Solved: AI forgetting context-specific rules.

## Phase 3: Mechanisms (v3.0 - v3.5)
Added living documents, session freeze, EKA.
System became self-documenting.

## Phase 4: Governance (v4.0 - v4.3)
Added permissions model, procedures registry.
Preparing for multi-user future.
```

---

## Procedure P-DOC-010

```
WHEN: Significant change to CLAUDE.md

1. INCREMENT version number appropriately

2. CREATE snapshot
   → Copy CLAUDE.md to CLAUDE_VERSIONS/CLAUDE_v{X.Y}.md

3. UPDATE changelog
   → Add entry with:
     - Version + date
     - Added / Changed / Removed
     - Why (reasoning)
     - Decided against (if applicable)

4. UPDATE evolution
   → If new phase or major shift, add narrative

5. COMMIT both files
   → Message: "docs(claude): snapshot v{X.Y} — {brief reason}"
```

---

## Statistics (as of 29 Jan 2026)

| Metric | Value |
|--------|-------|
| Current version | v4.3 |
| Total snapshots | 11 |
| First version date | 16 Jan 2026 |
| CLAUDE.md size | 611 lines, 34.6 KB |
| Changelog entries | 40+ |

---

## Integration

| Connects with | How |
|---------------|-----|
| [Permissions Model](permissions-model.md) | CLAUDE.md references permission levels |
| [Procedures Registry](procedures-registry.md) | P-DOC-010 is a formalized procedure |
| [Session Freeze](../methodology/session-freeze.md) | Major CLAUDE.md changes noted in session logs |

---

## Lessons Learned

1. **Snapshot before changing, not after** — You'll forget
2. **"Why" is more valuable than "what"** — Changes are visible, reasoning isn't
3. **Narrative matters** — Changelog is facts, evolution is story
4. **Don't over-snapshot** — Only significant changes, not typos
5. **Link to source** — If change came from session or zettel, reference it

---

> **Source:** Internal procedure P-DOC-010, CLAUDE_VERSIONS/ archive
