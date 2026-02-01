# Jarvis

🇵🇱 [Polska wersja](PL/README.md)

> **"Tell Jarvis what you want. He'll do the rest."**

**Project start:** January 16, 2026 | [Timeline](docs/timeline.md) | [Metrics](resources/metrics.md) | [→ Knowledge Threads](#knowledge-threads) | [→ Architecture Vision](#target-architecture-vision)

---

## Problem

Claude Code is powerful. But every session starts from zero.

You have projects spanning months. You have contexts that need to be remembered. You have routines you repeat every week. And Claude — forgets. Again.

**Claude starts from zero. Jarvis continues.**

---

## What is Jarvis?

Jarvis is not an assistant. Jarvis is a **concierge** — private, professional, scientific, and creative.

| Traditional AI Assistant | Jarvis |
|--------------------------|--------|
| Answers questions | Leads projects |
| Forgets after session | Remembers context |
| Executes commands | Understands intent |
| Tool | Partner |

---

## Status

**Active development.** Jarvis is used daily in real work.

### Autonomy

```
Human-in-the-loop ────────●──────── Human-out-of-loop
      PHASE 1           PHASE 2           PHASE 3
    (suggests)     (acts within limits) (decides alone)
                        ▲
                    WE ARE HERE
```

### Technological Maturity

```
TRL 5/9 — Component validated in real environment
━━━━━━━━━━━━━━━━░░░░░░░░░░░░░░
```

### Readiness for Use

```
Daily driver          ████████░░  85%
Team deployment       ██░░░░░░░░  20%
Public release        █░░░░░░░░░  10%
```

> **Transparency:** Jarvis works for the creator daily. For broader use — not yet.

---

## What Jarvis Knows Now (as of 1 February 2026, Day 17)

| Metric | Value |
|--------|-------|
| **Zettels (atomic knowledge)** | 173 notes, avg. confidence 0.85 |
| **Tracked sessions** | 50+ (100% compression survival) |
| **Procedures** | 47+ (32 approved) |
| **AI Personas** | 17 (7 confirmed) |
| **Persistent threads** | 25+ (8 strategic, 10 operational, 7 infra) |
| **Triggers in CLAUDE.md** | 80+ |
| **Knowledge graph** | 300+ links, 15 clusters |
| **Architectural concepts** | 12 (including Linguistic OS, Total Memory) |

**Knowledge quality (self-audit):** 88% verified, 9% partial, 3% needs correction.

→ [Full metrics](resources/metrics.md)

---

## What Job Do You "Hire" Jarvis For?

### 1. Remembers Projects and Helps Lead Them

You don't need to explain context. Jarvis knows what you're working on, what changed, what happened before.

> *"Resume project X"* → Jarvis reads history and continues.

### 2. "Program" with Words (Linguistic OS)

You say what you want — Jarvis does the rest.

```
"From now on, when an invoice comes from X, add it to folder Y"
→ Jarvis configures the rule.

"Remind me about the report on Friday"
→ Jarvis remembers.

"Do the same as last time for Kowalski"
→ Jarvis knows what that means.
```

This isn't a chatbot. This is **word agency**.

**Linguistic OS** — words build workflows, including conditionals and loops. Based on verbal formalism: "say what you'll do, and if it sounds right — do it."

### 3. External Brain for Thinking

Jarvis thinks with you. Connects the dots. Sees patterns. Proposes — but doesn't decide for you.

> *"What we're discussing now might solve the problem from that other project..."*

### 4. Automates Boring Tasks

Routines, formatting, templates, reminders — Jarvis takes over what consumes time but doesn't require creativity.

### 5. Partner for Creative Work

Jarvis isn't just an organizer — it's a partner for intellectual work:

- **Write a book with it** — remembers characters, plot threads, previous chapters
- **Conduct scientific research** — gathers sources, tracks hypotheses, connects conclusions
- **Create a vision** — customize it to your work, load skills, methodologies

And most importantly:

> **None of your knowledge is ever forgotten.**

What you discovered in January, Jarvis remembers in July. What you wrote in one project, you can use in another. Your intellectual work compounds — doesn't start from zero.

---

## Who Is It For?

**Jarvis isn't for everyone.**

Jarvis is for people who:
- Run multiple projects in parallel
- Think faster than they organize
- Need a thinking partner, not just a tool
- Want to say what to do, not how to do it
- **Create** — write, research, design — and need memory bigger than their own

### Potential Target Groups (research)

We're exploring whether Jarvis mechanisms can also support:

| Group | Need | How Jarvis Helps |
|-------|------|------------------|
| **Scientists** | Source tracking, bibliographies | EKA + Living Concept Docs |
| **Neurodiverse people** | External working memory | Total Memory + "thought parking" |
| **Seniors** | Patient assistant, repeatability | Procedures + context persistence |
| **Creators / Visionaries** | Total knowledge accumulation | Total Memory + Zettelkasten |
| **Non-technical builders** | Building without coding | Linguistic OS + word agency |

---

## Foundational Concepts

Three pillars on which Jarvis stands:

| Concept | Description |
|---------|-------------|
| **Linguistic OS** | Layer -1: Words build workflows. Verbal formalism inspired by Roman law. |
| **Total Memory** | Linear access to entire conversation history. CHECKPOINT + DELTA model. |
| **Progressive Enrichment** | Every system use improves it. "Walking the map and coloring." |

### Linguistic OS — How It Works

```
┌───────────────────────────────────────────────────────────────────────┐
│                         LINGUISTIC OS                                  │
│                     (Layer -1: Word Agency)                           │
│                                                                        │
│                                                                        │
│   USER ────────► NORMALIZE ──► WORKFLOW ──► NATURALIZE ──► USER       │
│   (any            (detect       (words       (result        (any      │
│    language)      intent)       build        back to        language) │
│                                 logic)       human)                   │
│                                                                        │
│   ┌─────────────────────────────────────────────────────────────────┐ │
│   │  "From now on, when an invoice comes from X, add it to folder Y"│ │
│   │                           ↓                                      │ │
│   │  IF (event X) THEN action(Y)                                    │ │
│   └─────────────────────────────────────────────────────────────────┘ │
│                                                                        │
│   PRINCIPLE: Verbal formalism (Roman Law inspiration)                 │
│   "Say what you'll do — if it sounds right, do it."                   │
│                                                                        │
└───────────────────────────────────────────────────────────────────────┘
```

---

## Knowledge Threads

> **Every session is a thread — a frozen thought process that can be queried at any moment.**

### What Are Knowledge Threads?

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  THREAD = FROZEN THOUGHT PROCESS                                        │
│                                                                          │
│  ────●────●────●────●────●────●────●────●────●────●────►  time          │
│      │    │    │    │    │    │    │    │    │    │                     │
│      ▼    ▼    ▼    ▼    ▼    ▼    ▼    ▼    ▼    ▼                     │
│    idea  →  discussion  →  decision  →  implementation  →  reflection  │
│                                                                          │
│  Each point = moment in creative process                                │
│  Entire thread = full LLM context that created something                │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Querying Threads

Thanks to **Total Memory** we're certain every thread is complete. We can enter any point and ask:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  USER: "How did we reach decision X in project Y?"                      │
│              │                                                           │
│              ▼                                                           │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │  JARVIS searches Threads:                                        │    │
│  │                                                                  │    │
│  │  THREAD: project-Y                                               │    │
│  │  ────●────●────●────●────●────●────►                            │    │
│  │            ▲                                                     │    │
│  │            │                                                     │    │
│  │      [ENTRY POINT]                                              │    │
│  │      "Here was the discussion about X"                          │    │
│  │                                                                  │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│              │                                                           │
│              ▼                                                           │
│  JARVIS: "In session 2026-01-15 we considered A, B, C.                  │
│           We chose X because [context from thread]..."                  │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Modeling the Creative Process

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  YOUR OWN HEAD              vs              KNOWLEDGE THREADS           │
│  ─────────────                              ─────────────────           │
│                                                                          │
│  "How did I build this?"      →      "Query the project X thread"       │
│  "Why did I decide that?"     →      "Find decision point in thread"    │
│  "What was I thinking then?"  →      "Restore context from moment T"    │
│                                                                          │
│  ┌─────────────────┐              ┌─────────────────┐                   │
│  │ Human memory:   │              │ Knowledge       │                   │
│  │ • fleeting      │              │ Threads:        │                   │
│  │ • fragments     │              │ • persistent    │                   │
│  │ • distorts      │              │ • complete      │                   │
│  └─────────────────┘              │ • accurate      │                   │
│                                   └─────────────────┘                   │
│                                                                          │
│  EFFECT: External process memory — not just the result, but HOW         │
│          we got there.                                                   │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Thread Graph

Threads connect into a knowledge graph:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│                         KNOWLEDGE THREAD GRAPH                           │
│                                                                          │
│            ┌─────────────────────────────┐                              │
│            │      THREAD: jarvis-core    │                              │
│            │  ────●────●────●────●────►  │                              │
│            └──────────────┬──────────────┘                              │
│                           │                                              │
│              ┌────────────┼────────────┐                                │
│              │            │            │                                 │
│              ▼            ▼            ▼                                 │
│  ┌───────────────┐ ┌───────────────┐ ┌───────────────┐                  │
│  │THREAD: session│ │THREAD:        │ │THREAD: total- │                  │
│  │       -logs   │ │ linguistic-os │ │       memory  │                  │
│  │ ──●──●──●──►  │ │ ──●──●──●──►  │ │ ──●──●──●──►  │                  │
│  └───────────────┘ └───────────────┘ └───────────────┘                  │
│         │                 │                 │                            │
│         └─────────────────┴─────────────────┘                           │
│                           │                                              │
│                           ▼                                              │
│                  ┌─────────────────┐                                    │
│                  │ THREAD: showcase│                                    │
│                  │ ──●──●──●──●──► │                                    │
│                  └─────────────────┘                                    │
│                                                                          │
│  Each thread = separate topic with full context                         │
│  Links between threads = semantic relationships                         │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Why Does This Work?

| Traditional | Knowledge Threads |
|-------------|-------------------|
| You save **the result** | You save **the process** |
| You lose decision context | You preserve full context |
| "I don't remember why" | "Query the thread from that day" |
| You reconstruct from fragments | You replay exactly |

**Total Memory** = certainty that every thread is complete
**Knowledge Threads** = ability to query any point in the process

---

## Greenfield Advantage (No Legacy)

> **Starting from zero — we can use the latest.**

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  TRADITIONAL PROJECT              vs              JARVIS (GREENFIELD)   │
│  ───────────────────                              ──────────────────    │
│                                                                          │
│  ┌─────────────────┐              ┌─────────────────┐                   │
│  │ Legacy code     │              │ Clean slate     │                   │
│  │ Old dependencies│              │ Latest LLMs     │                   │
│  │ Technical debt  │              │ MCP standard    │                   │
│  │ Migrations      │              │ Docker/K8s      │                   │
│  └─────────────────┘              └─────────────────┘                   │
│         ↓                                  ↓                            │
│  Every change = risk              Every change = opportunity            │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Snowball Effect

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  OUR OWN WORK                +              GLOBAL TRENDS               │
│  ─────────────                              ─────────────               │
│                                                                          │
│  • Procedures                +              • LLMs getting better       │
│  • Zettels                   +              • MCP standard growing      │
│  • Personas                  +              • Tool use maturing         │
│  • Routines                  +              • Agent autonomy            │
│         ↓                                          ↓                    │
│         └──────────────────┬───────────────────────┘                    │
│                            │                                             │
│                            ▼                                             │
│                 ╔═══════════════════════╗                               │
│                 ║  MUTUAL REINFORCEMENT ║                               │
│                 ║     (1 + 1 = 3)       ║                               │
│                 ╚═══════════════════════╝                               │
│                            │                                             │
│                            ▼                                             │
│              • System builds itself                                     │
│              • Costs drop (cheaper LLMs)                                │
│              • Value rises (more capabilities)                          │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

**Why it works:**

| Factor | Effect |
|--------|--------|
| **No legacy** | We can adopt latest solutions immediately |
| **Trends favor us** | LLM, MCP, agents — everything moves our way |
| **Our work compounds** | Every procedure, zettel, persona = lasting asset |
| **External progress = free upgrade** | Better Claude = better Jarvis (zero effort) |

---

## Target Architecture (Vision)

Jarvis evolves toward a distributed system:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                              USER                                        │
│                    "Turn on the light and summarize project"            │
│                                  │                                       │
│                                  ▼                                       │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                         JARVIS CORE                              │    │
│  │                                                                  │    │
│  │   Linguistic OS ──► Total Memory ──► Task Delegation            │    │
│  │                                                                  │    │
│  └──────────────────────────────┬──────────────────────────────────┘    │
│                                 │                                        │
│                    ┌────────────┴────────────┐                          │
│                    ▼                         ▼                          │
│  ┌─────────────────────────┐   ┌─────────────────────────┐              │
│  │      MESSAGE HUB        │   │    CLOUDFLARE TUNNEL    │              │
│  │      (NATS/MQTT)        │   │   (secure access)       │              │
│  └───────────┬─────────────┘   └─────────────────────────┘              │
│              │                                                           │
│   ┌──────────┼──────────┬──────────────┬──────────────┐                 │
│   ▼          ▼          ▼              ▼              ▼                 │
│ ┌─────┐  ┌─────┐    ┌─────┐       ┌─────────┐    ┌─────────┐           │
│ │ LLM │  │Tool │    │ DB  │       │ DRIVER  │    │ Remote  │           │
│ │Agent│  │Agent│    │Agent│       │  HUB    │    │Computer │           │
│ └──┬──┘  └──┬──┘    └──┬──┘       └────┬────┘    └────┬────┘           │
│    │        │          │               │              │                 │
│ ┌──┴──┐  ┌──┴──┐    ┌──┴──┐       ┌────┴────┐    ┌────┴────┐           │
│ │Docker│ │Docker│   │Docker│      │ Docker  │    │Playwright│          │
│ │ LLM  │ │ git  │   │Postgres│    │ drivers │    │ Browser │           │
│ └─────┘  └─────┘    └──────┘      └────┬────┘    └─────────┘           │
│                                        │                                │
│                    ┌───────────────────┼───────────────────┐            │
│                    ▼                   ▼                   ▼            │
│              ┌──────────┐       ┌──────────┐        ┌──────────┐        │
│              │  Smart   │       │Industrial│        │  Custom  │        │
│              │  Home    │       │ (Modbus, │        │  (REST,  │        │
│              │(Hue,Tuya)│       │  OPC-UA) │        │  serial) │        │
│              └──────────┘       └──────────┘        └──────────┘        │
│                                                                          │
│            ═══════════════════════════════════════════                  │
│                        KUBERNETES / DOCKER COMPOSE                       │
│                         (orchestration layer)                            │
│            ═══════════════════════════════════════════                  │
└─────────────────────────────────────────────────────────────────────────┘
```

### Star Topology — Jarvis Remote Host

```
┌─────────────────────────────────────────────────────────────┐
│                                                              │
│                    ┌─────────────────┐                      │
│                    │  JARVIS REMOTE  │                      │
│                    │      HOST       │                      │
│                    │    (Docker)     │                      │
│                    └────────┬────────┘                      │
│                             │                                │
│                    ┌────────┴────────┐                      │
│                    │   MESSAGE HUB   │                      │
│                    │  + CLOUDFLARE   │                      │
│                    └────────┬────────┘                      │
│                             │                                │
│         ┌───────────────────┼───────────────────┐           │
│         │           │       │       │           │           │
│         ▼           ▼       ▼       ▼           ▼           │
│    ┌────────┐ ┌────────┐ ┌─────┐ ┌─────┐ ┌──────────┐      │
│    │   PC   │ │Terminal│ │ iOS │ │Andr.│ │ Web App  │      │
│    │        │ │  CLI   │ │     │ │     │ │          │      │
│    └────────┘ └────────┘ └─────┘ └─────┘ └──────────┘      │
│                                                              │
│    KUBERNETES / DOCKER COMPOSE                               │
│    (everything in containers)                               │
└─────────────────────────────────────────────────────────────┘
```

**Architecture:**
- **Jarvis Remote Host** — hosted in Docker at our location (central node)
- **Message Hub + Cloudflare** — secure communication
- **Terminals** — PC, CLI, iOS, Android, Web App (each = interface)
- **Star topology** — all terminals connect to single node
- **Kubernetes** — orchestration of all containers

### Key Components

| Layer | Description |
|-------|-------------|
| **Jarvis Remote Host** | Central node in Docker (star topology) |
| **Message Hub** | NATS/MQTT — pub/sub, event sourcing |
| **Cloudflare Tunnel** | Secure access from anywhere |
| **Mobile Agents** | Docker containers with specialized agents |
| **Driver Hub** | Universal gateway to devices via existing drivers |
| **Terminals** | PC, CLI, iOS, Android, Web App |
| **Orchestration** | Kubernetes / Docker Compose |
| **PostgreSQL + pgvector** | Semantic search, embeddings, knowledge graph |

### Knowledge Base — PostgreSQL + pgvector

```
┌─────────────────────────────────────────────────────────────┐
│  POSTGRESQL + PGVECTOR                                       │
│                                                              │
│  ┌─────────────────────────────────────────────────────────┐│
│  │  TEXT                       EMBEDDING                    ││
│  │  ────                       ─────────                    ││
│  │  "Jarvis is a concierge"  → [0.23, -0.45, 0.12, ...]    ││
│  │  "Total Memory model"     → [0.56, 0.11, -0.33, ...]    ││
│  │  "Linguistic OS"          → [0.78, -0.22, 0.44, ...]    ││
│  └─────────────────────────────────────────────────────────┘│
│                              │                               │
│                              ▼                               │
│  ┌─────────────────────────────────────────────────────────┐│
│  │  SEMANTIC SEARCH                                         ││
│  │                                                          ││
│  │  Query: "how does memory work?"                         ││
│  │         ↓                                                ││
│  │  Result: "Total Memory model" (cosine similarity: 0.89) ││
│  │          "Knowledge Threads" (cosine similarity: 0.82)  ││
│  │          ...                                             ││
│  └─────────────────────────────────────────────────────────┘│
│                                                              │
│  We don't search words — we search MEANING                  │
└─────────────────────────────────────────────────────────────┘
```

**Capabilities:**
- **pgvector** — storing embeddings (1536+ dimensions)
- **Semantic search** — "find similar" instead of "find exact"
- **Knowledge graph** — relations between zettels, threads, projects
- **RAG ready** — foundation for Retrieval Augmented Generation

### Supported Protocols (via Docker drivers)

| Category | Protocols / Standards |
|----------|----------------------|
| **Smart Home** | Zigbee, Z-Wave, WiFi, Bluetooth (Hue, Tuya, Shelly) |
| **Industrial** | Modbus TCP/RTU, OPC-UA, MQTT, BACnet |
| **Computers** | REST API, WebSocket, SSH, Playwright |
| **Custom** | Serial (RS-232/485), GPIO, custom APIs |

> **Philosophy:** We don't build drivers from scratch — we use existing ones, wrapped in Docker.

### Host-Terminal Model

Every resource = **environment** (host) + **interface** (terminal):

```
┌─────────────────────────────────────────┐
│  RESOURCE (e.g., LLM Agent)             │
│  ┌─────────────────────────────────────┐│
│  │ HOST: Docker container + local LLM  ││
│  │ TERMINAL: REST API / MCP            ││
│  └─────────────────────────────────────┘│
└─────────────────────────────────────────┘
```

### Local LLMs for Tasks

Agents can have **their own, specialized LLMs**:

```
┌─────────────────────────────────────────────────────────────┐
│  ORCHESTRATOR                                                │
│  (manages resource pool)                                    │
│                                                              │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐       │
│   │ LLM     │  │ LLM     │  │ LLM     │  │ LLM     │       │
│   │ (chat)  │  │ (code)  │  │ (reason)│  │ (fast)  │       │
│   └────┬────┘  └────┬────┘  └────┬────┘  └────┬────┘       │
│        │            │            │            │             │
│        └────────────┴────────────┴────────────┘             │
│                          │                                   │
│                    RESOURCE POOL                             │
│              (allocation on demand)                          │
└─────────────────────────────────────────────────────────────┘
```

### Usage Modes

| Mode | Description | Example |
|------|-------------|---------|
| **Own needs** | Agents work for me | Research, projects, automation |
| **External interfaces** | Agents as service for others | Client chatbot, API |
| **Data collection** | Agents gather information | Monitoring, scraping, aggregation |
| **Subscription** | Army of agents manageable | Custom agent-role-on-demand |

### Agents at Every Project Stage

```
┌─────────────────────────────────────────────────────────────┐
│  PROJECT LIFECYCLE                                           │
│                                                              │
│  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐  ┌───────┐ │
│  │RESEARCH│→ │ DESIGN │→ │  MVP   │→ │  TEST  │→ │ LAUNCH│ │
│  └────┬───┘  └────┬───┘  └────┬───┘  └────┬───┘  └───┬───┘ │
│       │           │           │           │          │      │
│       ▼           ▼           ▼           ▼          ▼      │
│  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐  ┌───────┐ │
│  │Recon   │  │Customer│  │Prototype│ │Pre-user│  │ Demo  │ │
│  │scouts  │  │journey │  │builder │  │testers │  │agents │ │
│  │(army)  │  │mapper  │  │        │  │        │  │       │ │
│  └────────┘  └────────┘  └────────┘  └────────┘  └───────┘ │
│                                                              │
│  Agents = scouts at every stage                             │
│  Gathering data, testing assumptions, reporting             │
└─────────────────────────────────────────────────────────────┘
```

| Stage | Agent Role | Value |
|-------|------------|-------|
| **Research** | Army of scouts | Market data gathering |
| **Design** | Customer journey mapping | How the product should look |
| **MVP** | Prototype builders | Quick assumption testing |
| **Test** | Pre-user testers | Validation before users |
| **Launch** | Demo agents | Presentation, onboarding |

### Subscription Model (Vision)

```
┌─────────────────────────────────────────────────────────────┐
│                    JARVIS PLATFORM                           │
│                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐       │
│  │    USER      │  │    USER      │  │    USER      │       │
│  │      A       │  │      B       │  │      C       │       │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘       │
│         │                 │                 │                │
│         ▼                 ▼                 ▼                │
│  ┌──────────────────────────────────────────────────────┐   │
│  │              ORCHESTRATOR (shared)                    │   │
│  └──────────────────────────────────────────────────────┘   │
│         │                 │                 │                │
│         ▼                 ▼                 ▼                │
│  ┌────────────┐    ┌────────────┐    ┌────────────┐         │
│  │ Pool A     │    │ Pool B     │    │ Pool C     │         │
│  │ • 3 agents │    │ • 10 agents│    │ • 1 agent  │         │
│  │ • LLM: own │    │ • LLM: mix │    │ • LLM: API │         │
│  └────────────┘    └────────────┘    └────────────┘         │
│                                                              │
│  Subscription:  Basic       Pro          Enterprise         │
│                $10/mo      $50/mo        Custom              │
└─────────────────────────────────────────────────────────────┘
```

### Self-Building + LLM Programming

Jarvis can **program its own resources**, including LLMs in agents:

```
┌─────────────────────────────────────────────────────────────┐
│  JARVIS CORE                                                 │
│       │                                                      │
│       ▼                                                      │
│  "I need an agent for invoice analysis"                     │
│       │                                                      │
│       ├──► Creates Docker container                         │
│       ├──► Selects base LLM (small/local)                   │
│       ├──► Fine-tunes on invoice examples                   │
│       ├──► Injects CLAUDE.md with role                      │
│       └──► Registers in Resource Pool                       │
│                                                              │
│  RESULT: New agent "jarvis-invoices" ready to work          │
└─────────────────────────────────────────────────────────────┘
```

**Capabilities:**
- Creates new Docker agent on demand
- **Programs LLMs** (fine-tuning, LoRA, prompt engineering)
- Injects knowledge and role via CLAUDE.md
- Matches model to task (cheap/fast vs expensive/smart)
- System grows with needs

### Knowledge Transfer Between Agents

```
┌────────────┐         ┌────────────┐
│  Agent A   │ ──────► │  Agent B   │
│ (expert)   │ knowledge│ (learner)  │
└────────────┘         └────────────┘
      │
      ▼
 Zettelkasten (shared base)
```

- Agent discovers pattern → saves to Zettelkasten
- Another agent reads and applies
- **Knowledge compounds** — doesn't die with agent

### Work Pattern Modeling (NLP)

```
┌─────────────────────────────────────────────────────────────┐
│  USER works normally                                         │
│       │                                                      │
│       ▼                                                      │
│  JARVIS OBSERVES (Total Memory)                             │
│       │                                                      │
│       ├──► How do they formulate problems?                  │
│       ├──► How do they search for solutions?                │
│       ├──► What questions do they ask?                      │
│       ├──► When do they make decisions?                     │
│       └──► What do they skip/forget?                        │
│       │                                                      │
│       ▼                                                      │
│  COGNITIVE MODEL                                             │
│  "How this person thinks and works"                         │
└─────────────────────────────────────────────────────────────┘
```

**What Jarvis catches:**

| Pattern | Example | Value |
|---------|---------|-------|
| **Thinking style** | Visionary vs analyst vs practitioner | Personalized help |
| **Decision process** | What they check before deciding | Proactive suggestions |
| **Cognitive gaps** | What they regularly skip | Reminders |
| **Peak productivity** | When they work best | Task scheduling |

### Automatic Thought Capture

```
┌─────────────────────────────────────────────────────────────┐
│                                                              │
│  USER: "Hey, you know what, maybe we could..."              │
│         (5 seconds and it would be gone)                    │
│              │                                               │
│              ▼                                               │
│  JARVIS: Detected potential idea                            │
│         → Saving to DISCUSSION_QUEUE                        │
│         → Linking to current project                        │
│         → Marking context                                   │
│              │                                               │
│              ▼                                               │
│  "Noted. Want to come back to this?"                        │
│                                                              │
│  RESULT: Nothing is lost. Thought is in the system.         │
└─────────────────────────────────────────────────────────────┘
```

**JARVIS-AGENT as business assistant:**
- Public functions (for team)
- Private functions (personal notes, reflections)
- **Automatic capture** — thought → system in background
- Linking to projects without interrupting flow

### Multi-Jarvis (Vision)

```
┌─────────────────────────────────────────────────────────────┐
│                                                              │
│   JARVIS-A              JARVIS-B              JARVIS-C      │
│   (creator)             (company X)           (company Y)   │
│      │                     │                     │          │
│      └─────────────────────┼─────────────────────┘          │
│                            │                                 │
│                     FEDERATION HUB                           │
│              (pattern exchange, not data)                   │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

**Vision:** Multiple Jarvis instances exchanging **patterns** (not data):
- Jarvis-A discovers better aggregation method → publishes pattern
- Jarvis-B and C adopt the pattern
- **Network effect** — more instances = better patterns

---

## Methodologies (Research)

This project documents patterns and solutions discovered while building Jarvis:

→ [**Methodology Index**](methodology/_index.md) — full navigation

### Core Methodologies

| Methodology | Problem | Solution |
|-------------|---------|----------|
| [**EKA**](methodology/eka-architecture.md) | AI treats memory as binary | Knowledge with confidence weights |
| [**Total Memory**](methodology/total-memory.md) | Context lost on compression | CHECKPOINT + DELTA model |
| [**Living Concept Document**](methodology/living-concept-document.md) | Documentation gets stale | Self-documenting with §BOOTSTRAP |
| [**Zettelkasten**](methodology/zettelkasten-approach.md) | RAG loses relations | Atomic notes with links |
| [**Pattern System**](methodology/patterns-system.md) | Implicit behaviors | Systematic observation → validation |
| [**Unified Idea-Project**](methodology/unified-idea-project.md) | One-way idea→project flow | PRINCE2 + IDEO with backflow |

### Architectural Patterns

→ [**Architecture Index**](architecture/_index.md)

| Pattern | Description |
|---------|-------------|
| [**Permissions Model**](architecture/permissions-model.md) | Operators L0-L3 + confidentiality C0-C3 |
| [**CLAUDE.md Versioning**](architecture/claude-md-versioning.md) | Version control for AI instructions |
| [**Procedures Registry**](architecture/procedures-registry.md) | Formalized operations with Extraction Mindset |

---

## Repository Structure

```
jarvis-research-showcase/
├── README.md                          # This file (English)
├── PL/
│   └── README.md                      # Polish version
│
├── methodology/                       # HOW to work with AI
│   ├── _index.md                      # Methodology navigator
│   ├── eka-architecture.md            # Event-Knowledge Architecture
│   ├── total-memory.md                # Total Memory (NEW)
│   ├── living-concept-document.md     # LCD Methodology
│   ├── zettelkasten-approach.md       # Atomic knowledge
│   ├── patterns-system.md             # Pattern discovery
│   └── unified-idea-project.md        # Hybrid PRINCE2 + IDEO
│
├── architecture/                      # HOW system is built
│   ├── _index.md                      # Architecture navigator
│   ├── permissions-model.md           # L0-L3, C0-C3
│   ├── claude-md-versioning.md        # AI config versioning
│   └── procedures-registry.md         # P-XXX-NNN system
│
├── examples/
│   ├── sample-session.md              # Short example: Research → Documentation
│   └── session-scientific-audit.md    # Case study: 8h session, 3 compressions
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

You are free to share and adapt this material for any purpose, including commercially, provided you give appropriate credit.

Details in [LICENSE](LICENSE).

---

## Changes from Previous Version

| Element | Was | Is |
|---------|-----|-----|
| **Session Freeze** | Separate methodology | Replaced by **Total Memory** |
| **Neurodiverse people** | Session Freeze + parking | Total Memory + parking |
| **Metrics** | "state after 17 days" | "as of 1 February 2026, Day 17" |
| **Foundational Concepts** | Missing from English | **Full translation** included |
| **Knowledge Threads** | Not present | **Complete section** with diagrams |
| **Greenfield Advantage** | Not present | **Full section** with snowball effect |
| **PostgreSQL + pgvector** | Not mentioned | **Architecture section** added |
| **Star Topology** | Not present | **Jarvis Remote Host** documented |
| **Lifecycle Agents** | Not present | **Agents at every stage** added |

---

> **Note on naming:** "Jarvis" is a working title. This project has no affiliation with Marvel Entertainment or Disney.

---

> *"Words have power. Jarvis listens and acts."*
