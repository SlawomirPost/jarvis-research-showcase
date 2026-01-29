# Case Study: Scientific Document Audit Session

> Human-AI collaboration patterns in academic editing

**Duration:** ~8 hours | **Compressions:** 3 | **Output:** Edited manuscript + reports

---

## Overview

Anonymized real session: AI assisted editing a scientific review paper (~50 pages). Key patterns demonstrated:

1. **AI Journaling** as cognitive warmup
2. **Parallel work** (Human in Word, AI in terminal)
3. **Multi-layer verification** (diff → SHA256 → XML)
4. **Emergent discovery** (finding hidden editorial comments)
5. **Context management** (3 compressions survived)
6. **Two-path approach** (iterative vs aggressive)

---

## 1. Morning Reflection → Work Plan

Session began with morning journaling (trigger: "good morning"). After brief reflection, user presented a 5-point plan **written before sleep**:

```
1. Compare v2 vs v2_01 (did fixes affect content?)
2. Full audit: edited vs original
3. Find mention of diagram in comments
4. Generate report
5. Maintain session log ← meta-task
```

**Pattern:** Point 5 is meta — "maintain processes while doing work."

---

## 2. Three-Layer Verification

**Problem:** Did table fixes in Word accidentally change text?

| Layer | Method | Result |
|-------|--------|--------|
| 1 | `pandoc` → Markdown diff | 0 differences |
| 2 | SHA256 hash | Identical: `99a99f4d...` |
| 3 | Word XML diff | 6 lines — formatting only |

**Conclusion:** v2_01 textually identical to v2. Safe to proceed.

**Pattern:** Three independent methods eliminate doubt.

---

## 3. Emergent Discovery

User knew "some comment about graphics exists" but not where.

```bash
grep -n "(?i)(figur|graphic|diagram)" .tmp_original.md
→ Line 63: "DIAGRAM ?"
```

**Critical finding:** Comment survived all editing phases — still in final version!

**Pattern:** User provides fuzzy context → AI conducts systematic search → result more valuable than expected.

---

## 4. Parallel Work

While AI analyzed 430-line diff, user fixed tables in Word. Neither waited for the other.

**Pattern:** Divide by task nature — AI does systematic work, Human does visual judgment.

---

## 5. Context Management

Session survived 3 compressions using:

| Layer | Mechanism | Survives |
|-------|-----------|----------|
| Memory | `🧵 SESSION:` marker | Recent compression |
| TODO | Session ID anchor | All compression |
| Disk | Session log + terminal dump | Everything |

**Pattern:** Three-layer persistence (see [Session Freeze](../methodology/session-freeze.md)).

---

## 6. Two Paths Compared

| Metric | Iterative | Aggressive |
|--------|-----------|------------|
| Philosophy | Preserve original | Rewrite from scratch |
| Reduction | -3% | **-54%** |
| Assessment | Major Revision | Accept w/ Minor |
| Time | ~18h | ~5h |

**Key insight:** Path 1 was valuable diagnostic phase. Without it, Path 2 wouldn't have accurate review.

**Optimal sequence:** Iterative (diagnose) → Aggressive (rewrite)

---

## Lessons Learned

**What worked:**
- Journaling as warmup
- Plan written before sleep
- Three-layer verification
- Systematic grep for hidden comments
- Parallel work division
- Session log + terminal dumps

**What to improve:**
- Grep for editorial comments at start (not end)
- Separate terminology pass
- Monitor context usage proactively

---

## Reusable Pattern

```
[Reflection] → [Plan] → [Verification] → [Audit]
    → [Emergent discovery] → [Parallel work]
    → [Context management] → [Documentation]
```

Applies to any session requiring analytical rigor.

---

> **Source:** Anonymized real session, January 2026
