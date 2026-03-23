# HDL System Overview

## Purpose

This document explains the purpose of the parent repository and the role of its major directories.

`hdl-world-engine` is not the product repository. It is the architecture and doctrine repository that defines:

- canonical truth
- translation from canon into product requirements
- planning context for future system evolution

HDL is a multi-layered system composed of:

- Canon (truth layer)
- Bridge (translation layer)
- Planning (roadmap and design layer)
- Product (execution layer, in child repos)

## Repository Structure

At the top level, this repository is organized around:

- `canon/`
- `bridges/`
- `planning/` when planning artifacts are needed
- root guidance documents such as `SYSTEM_OVERVIEW.md`

### `canon/`

The `canon/` directory defines truth.

It contains the rules, entities, world structure, identity model, and invariant system behavior that HDL must follow. Product limitations do not redefine canon.

Examples of what lives here:

- identity doctrine
- routing doctrine
- proof doctrine
- world topology
- rendering and portal rules
- universal system invariants

Key principle:

> Canon defines how the system must behave.

### `bridges/`

The `bridges/` directory translates canonical truth into implementation strategy.

It is where doctrine is mapped into:

- frontend integration plans
- backend integration plans
- implementation gap analysis
- current product API snapshots

Bridge documents are not code and they are not canon. They exist to help product teams and engineers understand how existing repositories need to evolve to align with the truth layer.

Key principle:

> Bridge converts truth into implementation direction.

### `planning/`

The `planning/` directory is reserved for roadmap, sequencing, and system planning artifacts that sit between bridge guidance and active implementation.

This can include:

- phased rollout plans
- dependency maps
- milestone breakdowns
- service extraction plans
- long-range architecture sequencing

Key principle:

> Planning defines how change happens over time.

### Child Repositories

The actual product code belongs in child repositories, not here.

Current product-facing execution repos include:

- `hdl` or `hdl_react` for the frontend experience
- `hdl-node-backend-api` for the backend platform

Those repositories execute the product. This repository defines truth and alignment.

Key principle:

> Product executes the system, but does not define the doctrine.

## System Layers

### 1. Canon Layer

Source of truth for:

- Handle-first identity
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

### 3. Planning Layer

Sequencing layer for:

- implementation order
- migration strategy
- service evolution
- long-range architecture execution

### 4. Product Layer

Execution layer for:

- frontend UX
- backend APIs
- wallet interfaces
- social/feed systems
- future world rendering

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

## Architectural Direction

Current direction:

- canon is defined separately from product
- product systems are only partially aligned
- bridge documents explain the delta

Target direction:

- handle-first identity everywhere
- wallet abstraction behind routing
- proof-driven reputation and status
- world-aware interfaces over time

## Rules

- Canon is never modified to satisfy product convenience.
- Product must adapt to canon.
- Bridge documents define alignment strategy, not doctrine.
- Planning documents define sequence, not truth.
- Raw code does not belong in bridge or canon documents.

## Final Principle

HDL is not just a social product.

It is:

> a handle-based identity system  
> a wallet abstraction layer  
> a proof-driven reputation system  
> a world-based interface

Everything in the product layer must ultimately align to that.
