# Jarvis

> **"Powiedz Jarvisowi co chcesz. On zrobi resztę."**

**Project started:** 16 January 2026 | [Timeline](docs/timeline.md) | [Metrics](resources/metrics.md)

---

## Problem

Claude Code jest potężny. Ale każda sesja zaczyna od zera.

Masz projekty rozciągnięte na miesiące. Masz konteksty, które trzeba pamiętać. Masz rutyny, które powtarzasz co tydzień. A Claude — zapomina. Znowu.

**Claude zaczyna od zera. Jarvis kontynuuje.**

---

## Co to jest Jarvis?

Jarvis to nie jest asystent. Jarvis to **concierge** — prywatny, zawodowy, naukowy i twórczy.

| Tradycyjny AI assistant | Jarvis |
|-------------------------|--------|
| Odpowiada na pytania | Prowadzi projekty |
| Zapomina po sesji | Pamięta kontekst |
| Wykonuje polecenia | Rozumie intencje |
| Tool | Partner |

---

## Status

**Aktywny development.** Jarvis jest używany codziennie w realnej pracy.

### Autonomia

```
Human-in-the-loop ────────●──────── Human-out-of-loop
      PHASE 1          PHASE 2          PHASE 3
    (sugeruje)    (działa w ramach)  (sam decyduje)
                        ▲
                    JESTEŚMY TU
```

### Dojrzałość technologiczna

```
TRL 5/9 — Component validated in relevant environment
━━━━━━━━━━━━━━━━░░░░░░░░░░░░░░
```

### Gotowość do użycia

```
Personal daily driver  ████████░░  85%
Team deployment        ██░░░░░░░░  20%
Public release         █░░░░░░░░░  10%
```

> **Transparentność:** Jarvis działa dla twórcy codziennie. Dla szerszego użycia — jeszcze nie.

---

## Co Jarvis teraz wie (stan po 13 dniach)

| Metryka | Wartość |
|---------|---------|
| **Zettele (atomowa wiedza)** | 126 notatek, avg confidence 0.72 |
| **Sesje śledzone** | 32 (100% przetrwanie kompresji) |
| **Procedury** | 35+ (28 zatwierdzonych) |
| **Persony AI** | 16 (5 potwierdzonych) |
| **Trwałe wątki** | 19 (6 strategicznych, 7 operacyjnych, 6 infra) |
| **Triggery w CLAUDE.md** | 60+ |
| **Graf wiedzy** | 200+ linków, 12 clusters |

**Jakość wiedzy (self-audit):** 85% zweryfikowane, 12% częściowo, 3% do korekty.

→ [Pełne metryki](resources/metrics.md)

---

## Na jaką pracę "wynajmujesz" Jarvisa?

### 1. Pamięta projekty i pomaga je prowadzić

Nie musisz wyjaśniać kontekstu. Jarvis wie nad czym pracujesz, co się zmieniło, co było wcześniej.

> *"Wznów projekt X"* → Jarvis czyta historię i kontynuuje.

### 2. "Zaprogramować" słowem

Mówisz co chcesz — Jarvis robi resztę.

```
"Od teraz, gdy przychodzi faktura od X, dodaj ją do folderu Y"
→ Jarvis konfiguruje regułę.

"Przypomnij mi o raporcie w piątek"
→ Jarvis pamięta.

"Rób to samo co ostatnio dla Kowalskiego"
→ Jarvis wie co to znaczy.
```

To nie jest chatbot. To **sprawczość słowa**.

### 3. Zewnętrzny mózg do myślenia

Jarvis myśli razem z Tobą. Łączy punkty. Widzi wzorce. Proponuje — ale nie decyduje za Ciebie.

> *"To o czym teraz mówimy może rozwiązać problem z tamtego projektu..."*

### 4. Automatyzuje nudne zadania

Rutyny, formatowanie, szablony, przypomnienia — Jarvis przejmuje to, co zabiera czas, a nie wymaga kreatywności.

### 5. Partner do pracy twórczej

Jarvis to nie tylko organizator — to partner do pracy intelektualnej:

- **Napiszesz z nim książkę** — pamięta postaci, wątki, wcześniejsze rozdziały
- **Poprowadzisz badania naukowe** — gromadzi źródła, śledzi hipotezy, łączy wnioski
- **Stworzysz wizję** — dostosujesz go do swojej pracy, wgrasz skille, metodologie

I najważniejsze:

> **Żadna Twoja wiedza już nie zostaje zapomniana.**

Co odkryłeś w styczniu, Jarvis pamięta w lipcu. Co zapisałeś w jednym projekcie, możesz wykorzystać w innym. Twoja praca intelektualna się kumuluje — nie zaczyna od zera.

---

## Dla kogo?

**Jarvis nie jest dla wszystkich.**

Jarvis jest dla ludzi którzy:
- Prowadzą wiele projektów równolegle
- Myślą szybciej niż organizują
- Potrzebują partnera do myślenia, nie tylko narzędzia
- Chcą mówić co zrobić, a nie jak to zrobić
- **Tworzą** — piszą, badają, projektują — i potrzebują pamięci większej niż własna

---

## Metodologie (research)

Ten projekt dokumentuje wzorce i rozwiązania odkryte podczas budowy Jarvisa:

→ [**Methodology Index**](methodology/_index.md) — pełna nawigacja

### Core Methodologies

| Methodology | Problem | Solution |
|-------------|---------|----------|
| [**EKA**](methodology/eka-architecture.md) | AI treats memory as binary | Confidence-weighted knowledge |
| [**Session Freeze**](methodology/session-freeze.md) | Context lost on compression | Three-layer persistence |
| [**Living Concept Document**](methodology/living-concept-document.md) | Documentation becomes stale | Self-documenting with §BOOTSTRAP |
| [**Zettelkasten**](methodology/zettelkasten-approach.md) | RAG loses relationships | Atomic notes with explicit links |
| [**Pattern System**](methodology/patterns-system.md) | Behaviors implicit | Systematic observation → validation |
| [**Unified Idea-Project**](methodology/unified-idea-project.md) | One-way idea→project flow | PRINCE2 + IDEO with backflow |

### Architectural Patterns

→ [**Architecture Index**](architecture/_index.md)

| Pattern | Description |
|---------|-------------|
| [**Permissions Model**](architecture/permissions-model.md) | L0-L3 operators + C0-C3 confidentiality |
| [**CLAUDE.md Versioning**](architecture/claude-md-versioning.md) | Version control for AI instructions |
| [**Procedures Registry**](architecture/procedures-registry.md) | Formalized operations with Extraction Mindset |

---

## Repository Structure

```
jarvis-research-showcase/
├── README.md                          # This file
│
├── methodology/                       # HOW to work with AI
│   ├── _index.md                      # Methodology navigator
│   ├── eka-architecture.md            # Event-Knowledge Architecture
│   ├── session-freeze.md              # Conversation persistence
│   ├── living-concept-document.md     # LCD methodology
│   ├── zettelkasten-approach.md       # Atomic knowledge
│   ├── patterns-system.md             # Pattern discovery
│   └── unified-idea-project.md        # PRINCE2 + IDEO hybrid
│
├── architecture/                      # HOW the system is built
│   ├── _index.md                      # Architecture navigator
│   ├── permissions-model.md           # L0-L3, C0-C3
│   ├── claude-md-versioning.md        # AI config versioning
│   └── procedures-registry.md         # P-XXX-NNN system
│
├── examples/
│   ├── sample-session.md              # Short example: Research → Documentation
│   └── session-scientific-audit.md    # Deep case study: 8h session, 3 compressions
│
├── docs/
│   ├── vision.md                      # Long-term research vision
│   └── timeline.md                    # Project history
│
├── resources/
│   └── metrics.md                     # Quantitative measures
│
└── LICENSE                            # CC-BY-4.0
```

---

## License

This work is licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/).

You are free to share and adapt this material for any purpose, including commercial, as long as you give appropriate credit.

See [LICENSE](LICENSE) for details.

---

> **Note on naming:** "Jarvis" is a working title. This project has no affiliation with Marvel Entertainment or Disney.

---

> *"Słowo ma moc. Jarvis słucha i działa."*
