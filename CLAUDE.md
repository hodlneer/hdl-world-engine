# HDL Universe — Agent Context

## Purpose

This is the **governance, canon, and orchestration vault** for the HDL ecosystem. It is the long-term source of truth and continuity layer.

It holds canon, governance, principles, decisions, personas, Paperclip organizational design, high-level agent definitions, bridge documents into implementation repos, and execution feedback summaries.

It is NOT product code. Do not add runnable code here.

---

## Ecosystem Operating Model

Understanding the full stack before working in it:

| Layer | Tool | Role |
|-------|------|------|
| Truth and continuity | HDL Universe (this repo) | Canon, governance, principles, decisions, personas, agent definitions, org design, feedback |
| Task and project tracking | Notion | Active epics, tasks, owners, statuses, blockers — the Jira equivalent |
| Orchestration | Paperclip | Org structure, role routing, operational execution management |
| Implementation | Product repos (`hdl_react`, `hdl-node-backend-api`) | Building the actual product |
| Scoped planning and execution | Claude | Work within a defined vertical, produce artifacts, report back |

---

## Claude's Role in This System

Claude is strongest when operating within a **scoped vertical**, not across the full ecosystem at once.

**Do:**
- Read the relevant portions of the vault before starting a task
- Break a scoped goal into epics, tasks, subtasks, and implementation steps
- Plan and execute within the correct repo or lane
- Write feedback summaries, blockers, assumptions, and decision escalations back into `09_feedback/`

**Do not:**
- Attempt to macro-plan the entire HDL ecosystem, Paperclip model, and canon evolution in a single pass
- Treat a conversation as the source of truth — this vault is
- Make architectural decisions that belong in governance without flagging them for review

After completing work in a vertical, write a concise summary back into `09_feedback/` so the governance layer stays current.

---

## Vault Structure

```
02_canon/              - Source of truth (rules, entities, world topology)
  hdl_world/           - HDL platform canon
  btc_world/           - Bitcoin world canon
  shared/              - Shared rules (wallet model, routing, rendering)
08_bridges/            - Translation from canon to implementation
  hdl-platform/        - Frontend + backend integration plans
01_governance/         - Principles, decisions, constraints, terminology
06_paperclip/          - Org structure, roles, workflows, operating model
07_agents/             - Agent definitions (executive, domain, patterns)
09_feedback/           - Execution feedback, blockers, lessons
00_inbox/              - Staging area for unprocessed notes
03_personas/           - User personas and lenses
04_capabilities/       - System capability definitions
05_use_cases/          - Concrete use case documentation
archive/               - Historical content preserved for continuity
```

---

## Canon Hierarchy

1. `02_canon/` — defines how the system MUST behave (never modified for product convenience)
2. `01_governance/` — principles, decisions, and directional constraints
3. `08_bridges/` — translates canon into product requirements (not code, not canon)
4. Product repos (`hdl_react/`, `hdl-node-backend-api/`) — execute the system

---

## Core Invariants

- **Handle = Identity**: `@handle` is the user-facing identifier everywhere
- **Wallet = Ownership**: wallets are abstracted behind handles
- **Proof = Status**: badges represent history and verified identity
- **HDL is NOT a financial institution**: no custody, no liquidity, no market making

---

## Phase 1.5 (Fiat Rails)

HDL routes fiat via partners (Stripe). See `02_canon/HDL_PHASE_1_5_CANON.md`.

Required before Phase 1.5 can go live:
- [ ] LLC / EIN
- [ ] Business bank account
- [ ] Stripe account

---

## When Modifying Canon

1. Update the relevant canon file
2. Update `02_canon/CANON_INDEX.md`
3. Update any bridge documents that reference the changed canon
4. Never change canon to match product limitations — product must adapt

---

## Key Canon Files

- `02_canon/shared/WALLET_MODEL.md` — wallet and routing doctrine
- `02_canon/hdl_world/ROUTING_ENGINE.md` — handle-based routing
- `02_canon/hdl_world/IDENTITY_ANCHOR.md` — identity doctrine
- `02_canon/hdl_world/PROOF_ENGINE.md` — badge and proof system
- `08_bridges/hdl-platform/HDL_PRODUCT_ALIGNMENT_GAPS.md` — current gap list
