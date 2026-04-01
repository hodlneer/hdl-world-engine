# HDL System Overview

## Purpose

This document explains the purpose of this repository and the role of its major directories.

`hdl-universe` is the **governance, canon, and orchestration vault** for the HDL ecosystem. It is the long-term source of truth and continuity layer that preserves canon, captures decisions, defines organizational structure, and keeps strategy aligned with execution over time.

This repo is not the product codebase. It is the knowledge layer that everything else derives from.

HDL is a multi-layered ecosystem composed of:

- **Governance and Canon** — truth, doctrine, principles, and invariants (this repo)
- **Orchestration** — organizational structure, routing, and execution management (Paperclip)
- **Task tracking** — active work, epics, status, and progress (Notion)
- **Product execution** — implementation (child repos)

---

## Ecosystem Operating Model

### HDL Universe / Obsidian — Truth and Continuity

This repository is the long-term knowledge layer.

It holds:
- canon and doctrine
- governance and principles
- decisions and rationale
- personas and user lenses
- Paperclip organizational design
- high-level agent definitions
- bridge documents into implementation repos
- execution feedback summaries

It is intended to be opened as an Obsidian vault for local-first, version-controlled knowledge work.

### Paperclip — Orchestration and Execution Routing

Paperclip is the organizational execution layer.

It is where company structure, roles, task routing, and operational follow-through become active. This repo defines what Paperclip must operate within — the principles, org structure, and agent boundaries. Paperclip carries that into motion.

### Notion — Active Task and Project Tracking

Notion is the project management layer, similar to Jira.

Active epics, tasks, owners, statuses, and blockers live in Notion. This repo maintains high-level visibility into Notion so the governance layer stays aware of real implementation progress over time.

### Product Repos — Implementation

Product code belongs in child repositories.

Current execution repos:
- `hdl_react` — frontend experience
- `hdl-node-backend-api` — backend platform

Those repositories execute the system. This repository defines the truth they must align to.

---

## Repository Structure

The vault is organized across the following top-level directories:

### `01_governance/`

Principles, constraints, decisions, vision, and terminology that keep the system aligned over time.

What lives here:
- directional vision
- operating principles
- explicit decisions and rationale
- system constraints
- shared terminology definitions

Key principle:

> Governance defines what must remain true as the system evolves.

### `02_canon/`

The source of truth for how HDL must behave.

It contains the rules, entities, world structure, identity model, and invariant system behavior that HDL must follow. Product limitations do not redefine canon.

What lives here:
- identity doctrine
- routing doctrine
- proof doctrine
- world topology
- rendering and portal rules
- universal system invariants

Key principle:

> Canon defines how the system must behave.

### `06_paperclip/`

High-level organizational design for the Paperclip execution layer.

What lives here:
- org structure definitions
- role and responsibility definitions
- workflow patterns
- operating model

Key principle:

> Paperclip structure is defined here before it becomes operational.

### `07_agents/`

High-level definitions for AI and human agents operating within the ecosystem.

What lives here:
- executive agent definitions
- domain agent scopes
- agent interaction patterns

Key principle:

> Agent boundaries are defined in governance, not improvised at runtime.

### `08_bridges/`

Translation from canonical truth into implementation strategy.

It is where doctrine is mapped into:
- frontend integration plans
- backend integration plans
- implementation gap analysis
- current product API snapshots

Bridge documents are not code and they are not canon. They exist to help product teams and engineers understand how existing repositories need to evolve to align with the truth layer.

Key principle:

> Bridge converts truth into implementation direction.

### `09_feedback/`

Structured feedback flowing back from downstream execution into the governance layer.

What lives here:
- implementation results and outcomes
- blockers and escalations
- lessons and retrospective summaries

Key principle:

> Execution must report back so governance stays current.

### Supporting directories

- `00_inbox/` — staging area for new ideas and unprocessed notes
- `03_personas/` — user lenses and persona definitions
- `04_capabilities/` — system capability definitions
- `05_use_cases/` — concrete use case documentation
- `archive/` — historical content preserved for continuity

### Child Repositories

The actual product code belongs in child repositories, not here.

Current product-facing execution repos include:
- `hdl_react` for the frontend experience
- `hdl-node-backend-api` for the backend platform

Those repositories execute the product. This repository defines truth and alignment.

Key principle:

> Product executes the system, but does not define the doctrine.

---

## System Layers

### 1. Governance and Canon Layer

Source of truth for:
- HDL vision and principles
- handle-first identity
- wallet and routing doctrine
- proof and badge systems
- world structure
- interaction rules

### 2. Bridge Layer

Translation layer for:
- frontend integration
- backend integration
- product gap analysis
- existing system audits

### 3. Orchestration Layer (Paperclip)

Execution routing layer for:
- organizational structure
- role assignment
- task routing
- operational follow-through

### 4. Product Layer

Execution layer for:
- frontend UX
- backend APIs
- wallet interfaces
- social and feed systems
- future world rendering

---

## Core Architecture Principles

### Handle = Identity

- The handle is the primary user-facing identifier.
- Handles replace usernames and numeric IDs in user-facing contexts.
- Identity must be handle-native across frontend and backend systems.

### Wallet = Ownership

- Wallets are the ownership and routing layer.
- Wallets should be abstracted from the primary UX.
- Multi-chain support should exist behind a simple handle-first interface.

### Proof = Status

- Proof is the credibility layer.
- Badges represent history, participation, and verified identity.
- Hodlneer belongs here as a badge/status identity, not as the platform brand.

### Feed = Interaction

- The feed is the central interaction surface.
- It should surface handles, proof, and actions clearly.
- It is the social entry point into the HDL system.

---

## Rules

- Canon is never modified to satisfy product convenience.
- Product must adapt to canon.
- Bridge documents define alignment strategy, not doctrine.
- Feedback artifacts must flow back into `09_feedback/` so the vault stays current.
- Raw code does not belong in bridge or canon documents.

---

## Final Principle

HDL is not just a social product.

It is:

> a handle-based identity system
> a wallet abstraction layer
> a proof-driven reputation system
> a world-based interface

Everything in the product layer must ultimately align to that.
