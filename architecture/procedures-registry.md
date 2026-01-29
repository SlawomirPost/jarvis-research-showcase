# Procedures Registry

> Formalizing operational knowledge with the Extraction Mindset

**Status:** Production (35+ procedures)
**Version:** 1.0

---

## The Problem

Operational knowledge tends to be:
- **Scattered** — in different documents, people's heads
- **Inconsistent** — different styles, levels of detail
- **Static** — written once, never updated
- **Wasteful** — procedures complete their main task but don't capture learnings

---

## Core Concept

Formalize procedures with:

1. **Standard ID format** — `P-{CATEGORY}-{NNN}`
2. **Clear statuses** — approved, testing, candidate
3. **Extraction Mindset** — every procedure extracts value beyond its main purpose

---

## The Extraction Mindset

```
Traditional Procedure:
  Do task → Done

Extraction Mindset:
  Do task → Extract value → Update knowledge → Done

"Every interaction is an opportunity to improve the system."
```

What to extract:
- **New knowledge** → Zettel
- **Improvement idea** → Backlog
- **Pattern observed** → Persona/Pattern file
- **Problem solved** → Troubleshooting record

---

## Procedure ID Format

```
P-{CATEGORY}-{NNN}

P         = Procedure (fixed prefix)
CATEGORY  = Domain (3-4 letters)
NNN       = Sequential number
```

### Categories

| Code | Domain | Examples |
|------|--------|----------|
| **SEC** | Security | P-SEC-001 Operator management, P-SEC-007 Verification |
| **DOC** | Documentation | P-DOC-010 CLAUDE.md versioning |
| **JPM** | Project Management | P-JPM-004 New idea, P-JPM-005 Project backflow |
| **SESSION** | Sessions | P-SESSION-005 Thread marker, P-SESSION-008 New session |
| **INGEST** | Data ingestion | P-INGEST-006 AI Research processing |
| **HEALTH** | Health domain | P-HEALTH-001 Patient onboarding |

---

## Procedure Statuses

| Status | Symbol | Meaning |
|--------|--------|---------|
| **Approved** | ✅ | Tested and working, follow it |
| **Testing** | 🧪 | Being tested, may change |
| **Candidate** | 💡 | Proposed, not yet tested |
| **Deprecated** | ⚠️ | Don't use, kept for reference |

---

## Procedure Template

```markdown
# P-XXX-NNN: Procedure Name

**Status:** ✅ Approved | 🧪 Testing | 💡 Candidate
**Version:** 1.0
**Last updated:** YYYY-MM-DD
**Owner:** [who maintains this]

---

## Purpose

What this procedure accomplishes.

---

## Trigger

When to use this procedure.

---

## Prerequisites

What must be true before starting.

---

## Steps

1. First step
   - Detail
   - Detail

2. Second step

3. ...

---

## Extraction (what to capture)

| If you observe... | Then... |
|-------------------|---------|
| New knowledge | Create zettel |
| Improvement idea | Add to backlog |
| Pattern | Update persona/patterns |

---

## Outputs

What this procedure produces.

---

## Related

- P-XXX-NNN: Related procedure
- Zettel 202601-XXX: Related knowledge

---

## History

| Date | Version | Change |
|------|---------|--------|
| ... | 1.0 | Initial |
```

---

## Registry Structure

```
PROCEDURES/
├── _REGISTRY.md              # Index of all procedures
├── P-SEC-001_operator-management.md
├── P-SEC-007_verification.md
├── P-DOC-010_claude-versioning.md
├── P-JPM-004_new-idea.md
├── P-JPM-005_project-backflow.md
├── P-SESSION-005_thread-marker.md
├── P-SESSION-007_folder-structure.md
├── P-SESSION-008_new-session.md
├── P-INGEST-006_ai-research.md
└── ...
```

---

## Registry Format

```markdown
# Procedures Registry

| ID | Name | Status | Category |
|----|------|--------|----------|
| P-SEC-001 | Operator Management | ✅ | Security |
| P-SEC-007 | Session Verification | ✅ | Security |
| P-DOC-010 | CLAUDE.md Versioning | ✅ | Documentation |
| P-JPM-004 | New Idea Capture | ✅ | Project Management |
| P-JPM-005 | Project → Idea Return | ✅ | Project Management |
| P-SESSION-005 | Thread Marker | ✅ | Sessions |
| ... | ... | ... | ... |
```

---

## Example: P-INGEST-006 with Extraction

```markdown
# P-INGEST-006: AI Research Ingestion

## Steps

1. Receive material (link, PDF, video, etc.)

2. Archive source
   - Copy to REPO/ with metadata
   - Note: original URL, date, author

3. Process content
   - Extract key concepts
   - Identify relevant to current work

4. Route outputs:
   - Knowledge → ZETTELKASTEN (new zettel)
   - Idea → IDEAS (if sparks something)
   - Improvement → BACKLOG (if suggests enhancement)

5. ** EXTRACTION ** (mandatory):
   - What was surprising?
   - What contradicts existing knowledge?
   - What patterns connect to other work?

6. Update related documents
   - Link from relevant zettels
   - Update knowledge graph if significant
```

---

## Benefits

### 1. Consistency
Same format, same expectations across all procedures.

### 2. Discoverability
Registry makes it easy to find relevant procedures.

### 3. Continuous Improvement
Extraction Mindset means procedures improve over time.

### 4. Onboarding
New person can read procedures to understand operations.

### 5. Audit Trail
Status and version history show evolution.

---

## Statistics (as of 29 Jan 2026)

| Metric | Value |
|--------|-------|
| Total procedures | 35+ |
| Categories | 6 (SEC, DOC, JPM, SESSION, INGEST, HEALTH) |
| Approved | 28 |
| Testing | 5 |
| Candidate | 2+ |

---

## Integration

| Connects with | How |
|---------------|-----|
| [CLAUDE.md Versioning](claude-md-versioning.md) | P-DOC-010 defines versioning procedure |
| [Permissions Model](permissions-model.md) | P-SEC-* procedures |
| [Unified Idea-Project](../methodology/unified-idea-project.md) | P-JPM-* procedures |
| [Zettelkasten](../methodology/zettelkasten-approach.md) | Extraction outputs become zettels |

---

## Lessons Learned

1. **Start simple** — Don't over-document; add detail as needed
2. **Extraction is the key** — Procedures that don't extract value are half-done
3. **Status matters** — Know whether to trust a procedure fully
4. **Review periodically** — Deprecated procedures accumulate if ignored
5. **Link everything** — Procedures reference zettels, zettels reference procedures

---

> **Source:** Internal zettel 202601-114 (Procedures Registry), PROCEDURES/_REGISTRY.md
