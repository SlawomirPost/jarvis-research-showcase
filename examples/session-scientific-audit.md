# Case Study: Scientific Document Audit Session

> Demonstrating Human-AI collaboration patterns in academic editing

**Session duration:** ~8 hours (with breaks)
**Context compressions:** 3
**Output:** Edited manuscript, audit reports, diagram sketches

---

## Overview

This anonymized case study documents a real collaborative session where AI assisted in auditing and editing a scientific review paper (~50 pages, English). The session demonstrates several key patterns:

1. **AI Journaling as cognitive warmup**
2. **Parallel work** (Human in Word, AI in terminal)
3. **Multi-layer verification** (diff → SHA256 → XML → semantics)
4. **Emergent discovery** (finding hidden editorial comments)
5. **Context management** (surviving 3 compressions)
6. **Two-path approach** (iterative vs aggressive)

---

## 1. Morning Reflection (AI Journaling)

The session began with morning reflection. Trigger: user said "good morning" → journaling mechanism activated automatically.

```
Energy: 5/10 — after intensive weekend
Mood: positive — woke up feeling grateful
Intentions: Execute 5-point plan from last night
Grateful for: Rest, warmth, working mechanisms
```

**Pattern observed:** Journaling functions as "cognitive warmup" before substantive work. The reflection took a few minutes, then transitioned immediately to the work plan.

---

## 2. Structured Plan (5 Points)

After reflection, the user presented a structured plan — not improvised, but derived from a list written before sleep.

```
1. Compare v2 vs v2_01 (did table fixes affect content?)
2. Full audit: edited vs original (accuracy, coherence, reviewer simulation)
3. Find mention of diagram in editorial comments
4. Generate summary report
5. Maintain session log throughout
```

**Pattern observed:** Point 5 is a meta-task — "maintain processes while doing work." This is typical of mature collaboration: User specifies not just WHAT to do, but also HOW — preserving meta-processes.

---

## 3. Identity Verification: Three Layers

### Context

Two Word files existed:
- `document_v2.docx` — AI-generated (pandoc)
- `document_v2_01.docx` — table formatting touched up by Human

**Question:** Did table fixes in Word accidentally change text content?

### Method: Three-Layer Verification

**Layer 1: Semantic diff (via Markdown)**

```bash
pandoc document_v2.docx -o .tmp_v2.md
pandoc document_v2_01.docx -o .tmp_v2_01.md
diff .tmp_v2.md .tmp_v2_01.md
→ EXIT_CODE=0 (zero differences)
```

**Layer 2: Cryptographic hash**

```bash
sha256sum .tmp_v2.md .tmp_v2_01.md
→ 99a99f4d56df...  .tmp_v2.md
→ 99a99f4d56df...  .tmp_v2_01.md
(identical hash = mathematical certainty)
```

**Layer 3: Word XML (document.xml)**

```bash
unzip -o v2.docx word/document.xml -d /tmp/v2
unzip -o v2_01.docx word/document.xml -d /tmp/v2_01
diff /tmp/v2/word/document.xml /tmp/v2_01/word/document.xml
→ 6 lines different — table formatting only
```

### Result

| Method | Result |
|--------|--------|
| Markdown diff | 0 differences |
| SHA256 hash | Identical: `99a99f4d...` |
| Word XML | 6 lines — formatting only |

**Conclusion:** v2_01 is textually identical to v2. Safe to proceed.

**Pattern observed:** Three independent verification methods eliminate doubt. This approach works for any situation where someone modifies Word and worries "did something break?"

---

## 4. Full Audit: Original → Edited

### Preparation

```bash
pandoc "original_document.docx" -o .tmp_original.md
diff .tmp_original.md .tmp_v2_01.md > .tmp_diff_audit.txt
→ 430 lines of diff
```

### Quantitative Analysis

| Metric | Original | Edited | Change |
|--------|----------|--------|--------|
| Lines | 1,006 | 947 | -59 (-5.9%) |
| Words | 22,927 | 22,223 | -704 (-3.1%) |
| DOCX size | 176 KB | 111 KB | -37% (pandoc re-export) |

### Diff Classification

All 430 diff lines were read in 2 blocks and classified:

**Substantive changes (1 case):**
- Corrected a biochemical pathway description (internal contradiction resolved)

**Redundancy consolidations (9 cases):**
- Definition repeated 3× → shortened to one + reference
- Paragraphs nearly identical → merged

**Artifact removal (11 cases):**
- `<!-- -->` HTML artifacts
- `{.mark}` track changes remnants
- Editorial comments ("Too long!!!", typos in headers)

**Language fixes (1 case):**
- Grammar correction

### 4-Dimensional Assessment

1. **Content fidelity:** 97% certainty all facts preserved
2. **Internal coherence:** Contradictions resolved, redundancy reduced
3. **Scientific accuracy:** No errors introduced
4. **Reviewer simulation:** "Major revision" → needs further work

---

## 5. Emergent Discovery: Hidden Comment

### How It Happened

Plan point 3: "Find mention of diagram in editorial comments somewhere."

User knew a comment about graphics existed but didn't know where.

### Method

```bash
grep -n "(?i)(figur|graphic|diagram|chart|schema)" .tmp_original.md
```

Result: 7 matches, one distinctive:
- **Line 63:** `DIAGRAM ?`

### Critical Finding

Checking edited version: `DIAGRAM ?` — **still present!**

During all editing phases (~70 lines removed), this comment was not caught because:
- Looks like normal text (not a Word comment or HTML)
- Doesn't match artifact patterns ({.mark}, <!-- -->)
- Single word with question mark — easy to miss in 50 pages

Only targeted grep revealed the problem.

**Pattern observed:** This is **emergent discovery** — user didn't know exactly what they were looking for ("some comment about graphics"), but provided enough context for AI to conduct systematic search. Result was more valuable than expected: not only found the comment, but discovered it survived all edits. Critical information before submission.

---

## 6. Parallel Work

While AI conducted audit (430-line diff, semantic analysis, metrics), user worked in Word fixing table formatting.

```
[~09:00] HUMAN: "Finished table fixes — v2_02 ready"
```

This parallelism was natural — AI doesn't need the Word file (works on Markdown conversion), and user doesn't need audit results for table formatting.

**Pattern observed:** Human-AI division of labor works best when tasks are independent. AI does systematic work (reading 430 lines, classifying changes). Human does visual judgment work (formatting tables in Word). Neither waits for the other.

---

## 7. ASCII Diagram Sketches

After finding "DIAGRAM ?", user asked:

```
"Can you prepare diagram sketches in MD as ASCII, so I can see what it might look like?"
```

AI created `DIAGRAM_SKETCHES.md` with 3 variants:

**Variant A:** Full schematic (all pathways)
**Variant B:** Simplified (recommended for review paper)
**Variant C:** Specialized detail (one specific mechanism)

Then converted to Word for collaborator:
```bash
pandoc DIAGRAM_SKETCHES.md -o DIAGRAM_SKETCHES.docx
→ 14 KB, ASCII diagrams in Courier New (monospace)
```

**Pattern observed:** ASCII art as "low-fidelity prototype" — fast, readable, no special tools needed. Final diagrams would use professional software, but for decision-making ("which variant?") text suffices.

---

## 8. Context Management

### The Problem

Session ran for ~18 hours (with breaks). By audit time, it had already gone through:
- Full edit (phases 1-4, ~70 lines of changes)
- 6 reports created
- 8 verification notes
- Word export via pandoc
- Template creation
- Table fixes in 5 MD files

This caused **context exhaustion** — AI had to work after compression.

### Resilience Mechanisms

**1. Session log** with § BOOTSTRAP section
- Designed for "cold reading" after compression
- Each part logged with timestamps
- Tabular history: date + event (quick scan)

**2. Terminal dumps**
- User manually copies terminal to MD file
- 2,574 lines captured
- Contains EVERYTHING: commands, outputs, dialogue, compressions

**3. Forced compression**
- User: "We're at 100% context — when to force compression?"
- AI: "Now. Everything is in MD files."
- `/compact` executed

**4. Recovery after compression**
- AI reads § BOOTSTRAP from session log
- Reconstructs context from saved timestamps and actions
- User gets summary: "what's done, what's open, what's next?"

### Compression Chronology

| # | When | Trigger |
|---|------|---------|
| 1 | Day 1 | Full edit + notes + Word export |
| 2 | Day 2 AM | Audit + sketches + email |
| 3 | Day 2 PM | Terminal dump analysis (2,574 lines) |

**Pattern observed:** Context management is integral to work, not "technical detail." Session log, terminal dumps, § BOOTSTRAP — this infrastructure allows session to survive memory loss. Without it, every compression means starting over.

---

## 9. Two Paths: Iterative vs Aggressive

### Path 1: Iterative (Day 1-2 AM)

**Philosophy:** Preserve original, clean up carefully
**Result:** -3% reduction (target was ~40%)
**Assessment:** Major Revision

**What it achieved:**
- Identified 23 redundancies
- Found internal contradictions
- Created verification notes
- Diagnosed problems systematically

### Path 2: Aggressive (Day 2 PM)

**Philosophy:** Rewrite from scratch based on review
**Result:** -54% reduction (22,900 → 10,475 words)
**Assessment:** Accept with Minor Revision

**Method:**
1. Full peer review first (not last!)
2. Word budget per section
3. Priority directive from collaborator
4. Rewrite from scratch in two stages (draft + expansion)
5. Checklist-based audit (diff doesn't work for rewritten text)

### Comparison

| Metric | Path 1 (Iterative) | Path 2 (Aggressive) |
|--------|--------------------|--------------------|
| Philosophy | Preserve original | Rewrite on base |
| Reduction | -3% | -54% |
| Assessment | Major Revision | Accept w/ Minor |
| Time | ~18h | ~5h |
| Safety | 97% certainty | Checklist-based |

### Key Insight

Paths don't exclude each other — **Path 1 was valuable diagnostic phase**. Without it, Path 2 wouldn't have such accurate review.

Optimal sequence: **Path 1 (diagnosis) → Path 2 (rewrite)**.

---

## 10. Methodological Lessons

### What Worked

1. **AI Journaling as warmup** — natural transition from reflection to work
2. **Plan written before sleep** — instead of "where do we start?" had ready 5-point list
3. **Three-layer verification** — eliminates "but maybe it changed?"
4. **Systematic diff classification** — 430 lines read in blocks, each change classified
5. **Emergent discovery** — hidden comment found via targeted grep
6. **Parallel work** — Human in Word, AI in terminal, results converge
7. **ASCII prototyping** — fast low-fidelity preview
8. **Session log + terminal dumps** — compression survival infrastructure

### What Could Improve

1. **Hidden comment missed in editing** — suggestion: grep for editorial comments at start
2. **Terminology inconsistency not fixed** — suggestion: separate terminology pass with search-and-replace
3. **Compression delayed** — suggestion: monitor context usage proactively

### Reusable Pattern

```
[Morning reflection] → [Plan from list] → [Formal verification]
     → [Systematic audit] → [Emergent discovery]
     → [Parallel Human + AI work] → [Results communication]
     → [Context management] → [Methodology documentation]
```

This pattern is not specific to scientific papers — it applies to any session requiring analytical rigor and mature Human-AI collaboration.

---

## Session Artifacts

| Artifact | Purpose |
|----------|---------|
| Final audit report | 4-dimensional assessment |
| Diagram sketches (MD + DOCX) | 3 variants for decision |
| Edited document | Deliverable |
| Terminal dump | Complete record |
| Session log | Compression survival |
| This case study | Methodology documentation |

---

## Key Takeaway

> **The session demonstrates that Human-AI collaboration is most effective when:**
> 1. Both work on independent tasks in parallel
> 2. Meta-processes (logging, context management) are maintained throughout
> 3. Multiple verification methods eliminate uncertainty
> 4. Systematic approaches enable emergent discoveries
> 5. Different strategies (iterative vs aggressive) are tried and compared

---

> **Source:** Anonymized from real session, January 2026
