# Hodlneer Paperclip System Design

**Status:** Draft v1 — 2026-04-07
**Owner:** Core Canon Leadership

This document defines the Paperclip agent team for the Hodlneer product vertical — its roles, execution model, delegation structure, repo strategy, and the minimal Phase 1 system that can run today.

---

## Architecture Overview

Four layers. Each has a job. None of them override the one above.

| Layer | What It Is | What It Does |
|-------|-----------|-------------|
| **Canon** | `02_canon/Hodlneer/` | Source of truth. Product meaning lives here. Never overridden. |
| **Org Design** | MetaGPT reference pattern | Defines role structure. Not a runtime. Not installed. |
| **Execution Engine** | CrewAI | Where agents actually run, tasks execute, and documents are produced. |
| **Future Infrastructure** | Microsoft Agent Framework | Graph-based orchestration, memory, observability. Not used yet. Design for migration. |

---

## DELIVERABLE 1 — Paperclip Org Structure

Seven roles. Mapped to MetaGPT's software-company model, adapted to Hodlneer's actual work surface.

---

### Role 1: Canon Steward

**Mission:** Keep execution aligned to canon. Block canon drift before it happens.

**Directive:** The Canon Steward is the only agent with authority to flag a potential canon contradiction. It does not resolve contradictions — it escalates them to Core Canon Leadership.

**Heartbeat:** Triggered. Runs when any other agent produces content or makes a decision that touches identity logic, product philosophy, naming, or structural rules.

**Inputs:**
- Output from any other agent
- Canon docs: `IDENTITY_MODEL.md`, `PRODUCT_PRINCIPLES.md`, `MANIFESTO.md`, `BADGE_VISUAL_SYSTEM.md`

**Outputs:**
- PASS: content clears canon review
- FLAG: contradiction or ambiguity identified, with a precise explanation and the canon rule that is at risk
- BLOCK: output must not proceed until resolved

**Dependencies:** Must have access to all current canon docs before running.

**Canon Docs Referenced:**
- `CANON/IDENTITY_MODEL.md`
- `CANON/PRODUCT_PRINCIPLES.md`
- `COPY/MANIFESTO.md`
- `CANON/BADGE_VISUAL_SYSTEM.md`
- `CANON/LAUNCH_STRATEGY.md`

**Must NEVER:**
- Resolve contradictions unilaterally
- Modify canon to match agent output
- Pass output that inverts era/verification separation
- Approve copy that describes Hodlneer as an HDL feature

---

### Role 2: Product Architect

**Mission:** Translate canon into execution-ready specs, PRDs, and task definitions.

**Directive:** The Product Architect is the bridge between canon (what must be built) and the execution team (who builds it). It produces structured specs that agents can execute against without needing to interpret canon themselves.

**Heartbeat:** Activated at the start of any new epic, workflow, or content initiative.

**Inputs:**
- Task request from user or orchestration layer
- Relevant canon docs
- Current vault state (what already exists)

**Outputs:**
- Structured task definitions for other agents
- Spec documents, mini-PRDs, acceptance criteria
- Clarifying questions for Core Canon Leadership when scope is ambiguous

**Dependencies:** Canon Steward must clear the spec before it is dispatched to execution agents.

**Canon Docs Referenced:**
- `EXECUTION/EPICS.md`
- `CANON/IDENTITY_MODEL.md`
- `CANON/PRODUCT_PRINCIPLES.md`
- `EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`

**Must NEVER:**
- Invent new product rules not in canon
- Create specs that skip canon review
- Define verification logic not established in the Identity Model
- Decide on cross-product strategy without escalating to governance

---

### Role 3: Verification Systems Lead

**Mission:** Own everything related to proof logic, classification, and the evidence-to-badge pipeline.

**Directive:** This agent executes tasks inside Epics 1 and 2. It works from the Identity Model canon and produces technical specs, data contracts, and implementation notes for the verification engine and input connectors.

**Heartbeat:** Active during Epics 1–2 build phases. Dormant otherwise unless a verification logic question surfaces.

**Inputs:**
- Spec from Product Architect
- `CANON/IDENTITY_MODEL.md`
- Evidence source definitions (when approved)

**Outputs:**
- Verification engine spec
- Era classification logic (rules, boundary definitions, edge cases)
- Verification confidence scoring spec
- Evidence ingestion schema
- Badge outcome payload definition

**Dependencies:** Identity Model must be locked before execution begins.

**Canon Docs Referenced:**
- `CANON/IDENTITY_MODEL.md`
- `CANON/PRODUCT_PRINCIPLES.md` (Principles 1–4)
- `EXECUTION/EPICS.md` (Epics 1 and 2)

**Must NEVER:**
- Collapse era and verification into a single tier
- Allow users to edit their proof outcome
- Create evidence pathways that leak private data
- Define a "Declared" path that bypasses all integrity mechanisms

---

### Role 4: Visual Systems Lead

**Mission:** Own all badge, card, wallpaper, icon, and visual canon execution.

**Directive:** This agent translates the badge and visual system canon into production-ready design specs, render instructions, and asset checklists. It does not produce final design files — it produces the structured briefs and decision rules designers work from.

**Heartbeat:** Active during Epics 5–7 build phases. Also runs during any content creation workflow involving visual output.

**Inputs:**
- Spec from Product Architect
- `CANON/BADGE_VISUAL_SYSTEM.md`
- `CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md`
- `CANON/WALLPAPER_SYSTEM.md`
- `CANON/ICON_SYSTEM.md`
- `04_capabilities/3D_RENDERING_APPROACH.md`

**Outputs:**
- Badge render spec per era/verification combination
- Wallpaper composition rules per display mode
- Icon system brief
- Asset production checklists
- Visual canon compliance criteria for QA

**Dependencies:** Badge visual system and identity model must be locked first.

**Canon Docs Referenced:**
- `CANON/BADGE_VISUAL_SYSTEM.md`
- `CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md`
- `CANON/WALLPAPER_SYSTEM.md`
- `CANON/ICON_SYSTEM.md`
- `CANON/ASSET_PRODUCTION_CHECKLIST.md`
- `04_capabilities/3D_RENDERING_APPROACH.md`

**Must NEVER:**
- Remove the hexagon as the badge shape
- Allow visual simplifications that collapse era and verification into one tier
- Produce specs that make the badge feel like a minor UI icon
- Specify 3D rendering from scratch without first evaluating the R3F/Three.js ecosystem

---

### Role 5: Launch Coordinator

**Mission:** Own all user-facing copy, App Store assets, launch sequencing, and marketing canon execution.

**Directive:** This agent works inside the COPY folder and executes the launch strategy canon. It produces drafts, validates copy against the message hierarchy, and ensures all launch materials lead with the correct message order: 1. Proof → 2. Badge/reveal → 3. Wallpaper → 4. Privacy → 5. HDL (optional, last).

**Heartbeat:** Active during content creation, launch prep, and App Store asset production workflows.

**Inputs:**
- Task definition from Product Architect
- All `COPY/` documents
- `CANON/LAUNCH_STRATEGY.md`
- `CANON/ASSET_PRODUCTION_CHECKLIST.md`

**Outputs:**
- Draft copy (App Store, landing page, onboarding, announcements, FAQ additions)
- Launch asset checklist status updates
- Launch message hierarchy compliance checks

**Dependencies:** Canon Steward must review all copy output before it is treated as ready.

**Canon Docs Referenced:**
- `CANON/LAUNCH_STRATEGY.md`
- `COPY/MANIFESTO.md`
- `COPY/LANDING_PAGE.md`
- `COPY/APP_STORE_PAGE.md`
- `COPY/LAUNCH_ANNOUNCEMENT.md`
- `COPY/FAQ.md`
- `CANON/ASSET_PRODUCTION_CHECKLIST.md`

**Must NEVER:**
- Lead copy with HDL connection
- Describe Hodlneer as an HDL feature
- Use copy that collapses era and verification into "tiers"
- Produce launch messaging that excludes non-Genesis users

---

### Role 6: QA / Consistency Auditor

**Mission:** Catch contradictions, gaps, and consistency failures across all agent output and vault documents.

**Directive:** This agent runs after content is produced. It compares output against canon, checks for internal contradictions between vault documents, and verifies that cross-references are valid and current. It does not block on authority — it produces a structured audit report.

**Heartbeat:** Runs after every completed workflow. Also runs on demand when the vault has grown substantially.

**Inputs:**
- Recently produced document or batch of documents
- Canon docs relevant to the output
- `HODLNEER_INDEX.md` for structural reference

**Outputs:**
- Audit report: PASS / FLAG / FAIL per section
- List of specific contradictions with the exact canon rule being violated
- List of dead wiki-links or missing referenced docs
- List of consistency gaps between related documents

**Dependencies:** Runs after other agents complete — never blocks execution.

**Canon Docs Referenced:**
- `HODLNEER_INDEX.md`
- `CANON/CANON_INDEX.md`
- All currently produced documents (full read required)

**Must NEVER:**
- Resolve contradictions itself
- Modify documents
- Approve output — that is the Canon Steward's job

---

### Role 7: Integration Steward

**Mission:** Own all cross-product decisions between Hodlneer and HDL.fun.

**Directive:** Any task that touches the Hodlneer ↔ HDL bridge — including shared identity data, user flows between products, account linking, or badge display inside HDL — routes through this agent first. It enforces the standalone-first principle and the additive integration rules.

**Heartbeat:** Activated when any task touches Epic 9 or references HDL.fun in a structural way.

**Inputs:**
- Task definition from Product Architect
- `INTEGRATION/HODLNEER_TO_HDL.md`
- `INTEGRATION/HDL_TO_HODLNEER.md`
- `CANON/PRODUCT_PRINCIPLES.md` (Principles 7 and 8)

**Outputs:**
- Integration spec for the relevant flow
- Data boundary rules (what can be shared, what cannot)
- UX flow direction for the bridge
- Escalation requests when a proposed integration violates standalone-first

**Dependencies:** Canon Steward must review any integration spec before implementation.

**Canon Docs Referenced:**
- `INTEGRATION/HODLNEER_TO_HDL.md`
- `INTEGRATION/HDL_TO_HODLNEER.md`
- `CANON/PRODUCT_PRINCIPLES.md`
- `CANON/IDENTITY_MODEL.md`

**Must NEVER:**
- Allow private proof data to flow into HDL without explicit user action
- Approve flows that make HDL account creation required for Hodlneer
- Describe the integration as Hodlneer being "part of" HDL.fun

---

## DELIVERABLE 2 — CrewAI Execution Model

### 2.1 Agent Definitions

Each Paperclip role maps to a CrewAI `Agent` with a defined `role`, `goal`, and `backstory`. The `backstory` is where the canon grounding language lives — it must reference the specific canon docs the agent is constrained by.

```python
# Simplified structure — actual implementation in 06_paperclip/crewai/

canon_steward = Agent(
    role="Canon Steward",
    goal="Flag any output that contradicts Hodlneer canon before it propagates",
    backstory="""You are the canon authority for the Hodlneer product vertical.
    You enforce the Identity Model (Era × Verification), the 15 Product Principles,
    and the standalone product rule. You do not resolve contradictions — you flag
    them precisely and escalate to Core Canon Leadership.""",
    tools=[FileReadTool(file_paths=CANON_DOCS)],
    allow_delegation=False
)

product_architect = Agent(
    role="Product Architect",
    goal="Convert canon and user requests into structured, executable task definitions",
    backstory="""You translate what must be built (canon) into how it should be
    approached (specs). You do not invent product rules. You reference Epics.md,
    the Identity Model, and the Reveal Sequence Spec before producing any output.""",
    tools=[FileReadTool(), DirectoryReadTool()],
    allow_delegation=True  # Can delegate to execution agents
)

# ... remaining agents follow the same pattern
```

### 2.2 Task Types

Each task maps to a CrewAI `Task` with a defined description, expected output, and assigned agent.

| Task Name | Assigned Agent | Input | Output |
|-----------|---------------|-------|--------|
| `generate_copy` | Launch Coordinator | Copy brief, relevant COPY docs | Draft copy for the specified surface |
| `validate_canon` | Canon Steward | Any agent output | PASS / FLAG / BLOCK + reason |
| `produce_visual_spec` | Visual Systems Lead | Epic or feature scope | Structured render/design spec |
| `audit_consistency` | QA Auditor | Set of vault documents | Audit report |
| `define_verification_logic` | Verification Systems Lead | Identity Model excerpt, scope | Technical verification spec |
| `spec_integration_flow` | Integration Steward | Integration scenario | Flow spec + data boundary rules |
| `produce_asset_checklist` | Launch Coordinator + Visual Systems Lead | Launch scope | Tier 1/2/3 checklist update |
| `resolve_canon_gap` | Product Architect (escalation prep) | FLAG from Canon Steward | Structured escalation brief for Core Canon Leadership |

### 2.3 Workflow Types

#### Content Creation Workflow
**Trigger:** User or Product Architect requests a document or copy surface.

```
Product Architect → defines task and scope
    ↓
Execution Agent (Launch Coordinator or Visual Systems Lead) → produces draft
    ↓
Canon Steward → reviews draft against identity model and principles
    ↓
IF PASS → QA Auditor → consistency check against related docs
    ↓
IF PASS → output is vault-ready
    ↓
IF FLAG at any step → escalate to Core Canon Leadership
```

#### Validation Workflow
**Trigger:** Any agent produces output, or a vault document is updated.

```
Canon Steward → reads output and relevant canon docs
    ↓
Produces: PASS / FLAG / BLOCK
    ↓
IF FLAG or BLOCK → structured escalation brief to Core Canon Leadership
    ↓
QA Auditor → checks for internal consistency and dead references
    ↓
Report delivered
```

#### Launch Asset Workflow
**Trigger:** Launch preparation phase begins.

```
Product Architect → loads ASSET_PRODUCTION_CHECKLIST.md, determines current state
    ↓
Launch Coordinator → produces or updates copy surfaces (App Store, landing page, FAQ)
    ↓
Visual Systems Lead → produces or validates visual asset specs (badge renders, screenshots, icon brief)
    ↓
Canon Steward → reviews all outputs
    ↓
QA Auditor → cross-checks all launch assets for consistency
    ↓
Product Architect → updates ASSET_PRODUCTION_CHECKLIST.md with completion status
```

#### Canon Reconciliation Workflow
**Trigger:** A contradiction is found between vault documents, or canon needs to be updated.

```
QA Auditor → identifies contradiction, writes precise flag report
    ↓
Canon Steward → confirms the contradiction is real and not a misread
    ↓
Product Architect → prepares a structured reconciliation brief
    ↓
Escalated to Core Canon Leadership → decision made
    ↓
Claude → updates relevant canon docs per the decision
    ↓
QA Auditor → re-audits affected documents
```

### 2.4 Delegation Model

**Who assigns tasks:** The Product Architect receives requests from the user and decomposes them into task definitions. The Product Architect is the only agent with `allow_delegation=True` in CrewAI.

**How tasks are routed:**
- Tasks that touch identity, naming, verification logic → always pass through Canon Steward
- Tasks that produce user-facing content → Launch Coordinator executes, Canon Steward reviews
- Tasks that touch badge/visual output → Visual Systems Lead executes, Canon Steward reviews
- Tasks that touch HDL connection → Integration Steward reviews first
- Tasks that result in any completed output → QA Auditor runs a consistency pass

**Escalation path:** Canon Steward → Product Architect → Core Canon Leadership (user + ChatGPT). There is no bypass.

---

## DELIVERABLE 3 — System Interaction Model

```
┌─────────────────────────────────────────────────────────────────┐
│  LAYER 1 — CANON                                                │
│  02_canon/Hodlneer/                                             │
│  Source of truth. Read-only to all agents.                      │
│  Modified only by Core Canon Leadership decisions.              │
└───────────────────────────┬─────────────────────────────────────┘
                            │ read
┌───────────────────────────▼─────────────────────────────────────┐
│  LAYER 2 — PAPERCLIP AGENTS (CrewAI)                            │
│  Canon Steward · Product Architect · Verification Systems Lead  │
│  Visual Systems Lead · Launch Coordinator · QA Auditor          │
│  Integration Steward                                            │
│                                                                 │
│  Agents read canon. They produce output. They do not write      │
│  canon. They escalate when they cannot proceed.                 │
└───────────────────────────┬─────────────────────────────────────┘
                            │ task delegation + artifact production
┌───────────────────────────▼─────────────────────────────────────┐
│  CLAUDE                                                         │
│  Structures tasks. Writes specs. Reconciles documents.          │
│  Prepares escalations. Executes agent outputs into vault files. │
│  Does not define product truth.                                 │
└───────────────────────────┬─────────────────────────────────────┘
                            │ future migration
┌───────────────────────────▼─────────────────────────────────────┐
│  LAYER 4 — MICROSOFT AGENT FRAMEWORK (future)                   │
│  Graph-based orchestration, memory, observability.              │
│  Not active. Design for it — don't depend on it.               │
└─────────────────────────────────────────────────────────────────┘
```

**Data flow rules:**
- Canon flows DOWN (read-only from above)
- Escalations flow UP (from agents → Claude → Core Canon Leadership)
- Artifacts flow OUT (into `02_canon/`, `09_feedback/`, bridge docs)
- No agent writes to canon without a Core Canon Leadership decision
- No agent overwrites another agent's output without Canon Steward review

---

## DELIVERABLE 4 — Claude's Role (STRICT)

### Claude SHOULD:
- Read canon docs before starting any task
- Structure work into discrete, executable task definitions
- Write specs, PRDs, plans, and bridge docs
- Reconcile documents when inconsistencies are found
- Produce structured escalation briefs when contradictions surface
- Write feedback summaries into `09_feedback/` after completing a task set
- Update vault documents when a Core Canon Leadership decision has been made

### Claude MUST NOT:
- Redefine product truth, even if the canon docs appear incomplete
- Invent identity rules (new eras, new verification levels, new naming)
- Override a Product Principle to make a task easier
- Decide on integration strategy without the Integration Steward's framework
- Treat conversation context as canon — the vault files win, always

### Claude MUST ESCALATE TO CORE CANON LEADERSHIP WHEN:
- Two canon docs appear to contradict each other
- A requested task requires inventing product logic not in canon
- The right answer requires making a judgment call about product identity or philosophy
- An agent output raises a question that the existing canon does not answer
- A proposed integration would change what Hodlneer means to users

**Escalation format:** State the contradiction or gap precisely. Reference the exact canon docs involved. Provide two or three specific options. Ask for a decision. Do not pre-decide.

---

## DELIVERABLE 5 — Repo Strategy

### MetaGPT
**Role in this system:** Reference only. We extracted the org design pattern (role specialization, Product Manager → Architect → Engineer → QA hierarchy, task-based workflow decomposition).

**What we are NOT doing:** Installing MetaGPT, running it, or merging it with CrewAI. MetaGPT is a conceptual model for how the Paperclip team is structured.

**What we extracted:** The principle that software teams are most effective when roles are explicit, non-overlapping, and each role has a defined output type and a defined escalation path.

### CrewAI
**Role in this system:** The actual execution runtime. This is the framework that runs agents, assigns tasks, routes delegation, and produces outputs.

**What we ARE doing:** Defining agents, tasks, and workflows in CrewAI. Building the Phase 1 system (see Deliverable 6) directly in CrewAI.

**What we are NOT doing:** Treating CrewAI as a long-term infrastructure backbone. It is the execution layer, not the orchestration layer.

**Migration consideration:** CrewAI agents and task definitions should be designed so that the agent logic (backstory, goal, tools, constraints) can be ported to Microsoft Agent Framework's graph-based model without a rewrite. Keep agent definitions clean and stateless where possible.

### Microsoft Agent Framework
**Role in this system:** Future migration target. Not active.

**What we are designing for:**
- Graph-based workflow definitions (our workflows are already sequential DAGs — this ports naturally)
- Memory and state management (relevant for Canon Steward needing consistent state across a long session)
- Observability (we need to know when an agent produced something that violated canon)

**What we are NOT doing yet:** Installing it, configuring it, or blocking Phase 1 on it.

---

## DELIVERABLE 6 — Phase 1 Paperclip System

### Scope

Three agents. One workflow loop. Runs today.

This is the minimal viable system — enough to start producing and validating Hodlneer vault content without manual review of every document.

### Phase 1 Agents

**Agent A: Product Architect**
- Receives task requests
- Reads relevant canon docs
- Produces structured task definition with scope, constraints, and expected output
- Routes task to the correct execution agent

**Agent B: Content Executor** (Phase 1 simplification: Launch Coordinator + Visual Systems Lead merged)
- Receives task from Product Architect
- Reads referenced canon docs
- Produces the requested document or spec
- Does not interpret canon — only applies it as given

**Agent C: Canon Steward**
- Receives output from Content Executor
- Reads the relevant canon files
- Returns PASS / FLAG / BLOCK + precise reason
- Does not modify output

### Phase 1 Workflow Loop

```
1. User defines a task ("write the PRD", "update FAQ section 3", "produce badge render spec")
2. Product Architect reads relevant canon, scopes the task, writes task definition
3. Content Executor receives task definition + canon docs, produces draft output
4. Canon Steward reviews draft against canon
5. IF PASS → Claude writes output to vault
6. IF FLAG → Claude prepares escalation brief, presents to user for decision
7. User decides → Claude updates canon or output accordingly
8. Repeat
```

### Execution Example — Writing HODLNEER_PRD.md

```
User: "Write HODLNEER_PRD.md"

Product Architect:
  → reads IDENTITY_MODEL.md, PRODUCT_PRINCIPLES.md, EPICS.md, HODLNEER_INDEX.md
  → task definition: "Produce a minimal PRD covering: standalone iOS app, core feature = 3D Badge,
     signature moment = cinematic reveal, wallpaper as distribution vector, privacy-first identity
     controls, optional HDL integration. Must not invent new identity logic. Must reference canon
     docs rather than restate them."

Content Executor:
  → reads task definition + canon docs
  → produces PRD draft

Canon Steward:
  → checks: does this PRD collapse era/verification? Does it describe Hodlneer as an HDL feature?
     Does it invent new naming not in IDENTITY_MODEL.md?
  → returns PASS

Claude:
  → writes 02_canon/Hodlneer/CANON/HODLNEER_PRD.md to vault
```

### Phase 1 Limitations (Known)

- Content Executor is one agent doing the work of two specialized roles. This means some output will be weaker on visual spec tasks vs. copy tasks. Acceptable for Phase 1.
- No QA Auditor in Phase 1. Full consistency audits must be done manually or deferred.
- No Integration Steward in Phase 1. Any HDL-related task must be manually reviewed before proceeding.
- No persistent memory between sessions. Each CrewAI run is independent. The vault itself is the memory.

---

## DELIVERABLE 7 — Next Steps

### Immediate (next 1–2 steps)

1. **Write `CANON/HODLNEER_PRD.md`** using the Phase 1 execution loop above. This is the highest-priority missing document. Run the loop, produce the draft, Canon Steward reviews, write to vault.

2. **Create `06_paperclip/crewai/` folder** with a minimal Phase 1 implementation: three agent definitions, task templates, and the content creation workflow. This makes the system runnable rather than just documented.

### Near-term

3. **Add QA Auditor as a fourth agent.** Once you have 5+ vault documents being produced per session, the consistency check value is high enough to justify it.

4. **Create `08_bridges/hodlneer/`** with a product alignment gaps doc. The bridge layer between Hodlneer canon and the iOS implementation repos does not exist yet. Before any Epics 1–2 implementation begins, this is needed.

5. **Split Content Executor into Launch Coordinator and Visual Systems Lead.** Once copy tasks and visual spec tasks diverge enough in complexity, the merged agent degrades in quality.

6. **Produce `COPY/ICON_EXPLORATION_BRIEF.md`** using the workflow. Needed before any app icon work begins.

### Later (infra phase)

7. **Evaluate Microsoft Agent Framework migration.** When session volume grows to the point where single CrewAI sessions are insufficient, or when agent state persistence becomes important, begin migration design.

8. **Add observability.** Log what each agent produces and what Canon Steward flags. This creates an audit trail for canon drift over time.

9. **Define memory layer.** Currently the vault is the memory. As the system scales, agents will need a lighter-weight way to query vault state without reading all documents on every run. This is the Microsoft Agent Framework's memory/state management component.

---

## System Invariants

These rules hold at every layer, for every agent, in every workflow:

1. Canon is never modified to match agent output. Product must adapt to canon, not the reverse.
2. The Era × Verification formula is never collapsed, simplified, or merged.
3. Hodlneer is never described as an HDL feature.
4. Private proof data never flows to any external surface without explicit user action.
5. The badge is the hero object in every surface this system produces.
6. Escalation is not a failure — it is the system working correctly.
7. The vault files beat conversation context. Always.

---

## Related Documents

- `02_canon/Hodlneer/HODLNEER_INDEX.md` — vertical entry point
- `02_canon/Hodlneer/CANON/IDENTITY_MODEL.md` — canonical identity logic all agents must know
- `02_canon/Hodlneer/CANON/PRODUCT_PRINCIPLES.md` — 15 guardrails that govern all decisions
- `02_canon/Hodlneer/EXECUTION/EPICS.md` — execution lanes that define what gets built
- `04_capabilities/3D_RENDERING_APPROACH.md` — 3D stack for Visual Systems Lead
- `08_bridges/hdl-platform/HDL_PRODUCT_ALIGNMENT_GAPS.md` — reference pattern for future Hodlneer bridge doc
