# HDL Canon — Index (Revised)

This document serves as the map of the HDL universe. It explains how the canon repository is structured, how
authority flows between documents, and where to look when you need to
understand or extend the HDL World Engine. Anyone building,
interpreting or extending the system should begin here.

The canon has matured significantly since its inception. In addition to
doctrine and rules, it now contains a growing set of systems — such as
the Proof Engine, Identity Anchor, Routing Engine and Brand System —
that form the core of the HDL product. This index reflects those
additions and clarifies how the pieces fit together.

## Canon Authority Layers

Canonical truth in HDL flows through five layers of doctrinal
authority. Higher layers override lower layers. Implementation
documents, diagrams and brand materials must respect this hierarchy.

- Canon Invariants – `/canon/shared/CANON_INVARIANTS.md`
  The constitutional truths of the HDL universe (e.g. “HDL is the
  central world”, “HDL is permanently safe”). These rarely change
  without redefining HDL itself.
- Universal Rules – `/canon/shared/UNIVERSAL_RULES.md` and related
  documents
  Cross-world rules for portals, terminology, agents, rendering,
  wallet behaviour and visualisation. Every world must conform to
  these rules.
- World Doctrine – `_WORLD_OVERVIEW.md` files
  Each world has its own overview defining its identity, spatial and
  temporal models, atmosphere and mood. Examples: `/canon/hdl_world/_WORLD_OVERVIEW.md`,
  `/canon/btc_world/_WORLD_OVERVIEW.md`.
- World Rules – `RULES.md` files
  Operational rules specific to each world (movement, interaction,
  safety, consequences). These must follow both the world overview
  and the universal rules.
- Canonical Objects & Entities
  World-specific canonical objects, origins records, system
  intelligence documents and symbolic entities. Examples: `OD.md`,
  `ENTITIES.md`, `DISCIPLES.md`, `BTC_HEX_NETWORK_CANON.md`, etc.
  These files are subordinate to all layers above.

In addition to the doctrinal stack, the repository contains shared
architecture specifications, world implementation specs, and
meta-governance/navigation documents. These supporting documents do
not outrank doctrine but are part of the canon and must remain
consistent with it.

## Meta Documents

These files help govern and navigate the canon repository, but they do
not carry doctrinal authority themselves:

- `CANON_INDEX.md` – the document you are reading. It maps the
  entire canon.
- `CANON_AUTHORITY.md` – explains how authority and change flow
  through the canon. It defines who can propose updates and how
  doctrine evolves.

## Shared Architecture

These documents define engine-level, rendering-level and
cross-world implementation architecture shared by all worlds. They do
not replace doctrine but provide canonical building blocks used by
world-specific implementations.

| File | Purpose |
| --- | --- |
| `/canon/shared/ENGINE_PIPELINE.md` | Defines the universal pipeline by which data, identity and signalling move from chain inputs through geometry, particles, LOD and rendered output. World-specific engine docs (e.g. `btc_world/ENGINE_PIPELINE.md`) must inherit from this pipeline rather than redefine it. |
| `/canon/shared/WALLET_MODEL.md` | Specifies the cross-chain wallet model used throughout HDL. It describes identity handles, wallet linking, asset compatibility and routing prerequisites. |
| `/canon/shared/VISUALIZATION_RULES.md` | Defines how blockchain participation and canonical objects are visualised. This includes particle types, motion and halo usage, and how distance and focus affect representation. |
| `/canon/shared/RENDERING_STRATEGY.md` | Lays out the layered rendering model balancing geometry, particles and LOD across all worlds. |
| `/canon/shared/LOD_STRATEGY.md` | Describes how canonical objects transition from abstract energy to precise geometry as distance and focus change. |
| `/canon/shared/PARTICLE_SYSTEMS.md` | Defines the Life Layer particle types and their behaviours (motion, turbulence, fields, halos, swarms). |
| `/canon/shared/BRAND_SYSTEM.md` | Preserves emerging brand ethos, emotional tone and philosophical framing. This document explores what HDL means and how it feels; it does not override doctrine or architecture. |

## Layer 1 – Canon Invariants

File: `/canon/shared/CANON_INVARIANTS.md`

Defines the constitutional truths of the HDL universe. Examples
include: “HDL is the central world”, “HDL is permanently safe”,
“worlds remain separate”, and “portals are the only travel mechanism”.
All other documents must comply with these invariants.

## Layer 2 – Universal Rules

Files:

- `/canon/shared/UNIVERSAL_RULES.md`
- `/canon/shared/PORTALS.md`
- `/canon/shared/GLOSSARY.md`
- `/canon/shared/AGENTS.md`
- `/canon/shared/WALLET_MODEL.md`
- `/canon/shared/VISUALIZATION_RULES.md`
- `/canon/shared/RENDERING_STRATEGY.md`
- `/canon/shared/LOD_STRATEGY.md`
- `/canon/shared/PARTICLE_SYSTEMS.md`
- `/canon/shared/BRAND_SYSTEM.md`

Purpose:

Defines rules that apply across all worlds. These govern how worlds
connect, how portals operate, what terminology means, how agents are
bounded, how identity and wallets behave, and how objects render.
Every world and system must follow these universal rules.

## Layer 3 – World Doctrine

Each world defines its own world overview (`_WORLD_OVERVIEW.md`).
This document explains the identity, spatial model, time model,
atmosphere and mood of the world. It provides the narrative and
philosophical context for that world. Examples:

- `/canon/hdl_world/_WORLD_OVERVIEW.md` (HDL World – the safe central environment)
- `/canon/btc_world/_WORLD_OVERVIEW.md` (Bitcoin World – the Bitcoin ecosystem)

## Layer 4 – World Rules

Files: `/canon/hdl_world/RULES.md`, `/canon/btc_world/RULES.md` (and
future worlds).

Defines the operational rules for each world: movement constraints,
interaction mechanics, safety systems and consequences. These rules
must follow both the world overview and the universal rules.

## Layer 5 – World-Specific Canon Objects

Worlds define canonical objects, origins documents and entity lists.
Examples include:

- `/canon/hdl_world/OD.md` – the Orchestrating Daemon (universal
  intelligence layer). Defines how OD guides and interprets rather
  than decides.
- `/canon/hdl_world/DISCIPLES.md` – the Twelve Disciples representing
  disciplines like cryptography, DeFi and on-chain art.
- `/canon/btc_world/OD.md` – the Bitcoin origins document.
- `/canon/btc_world/SATOSHI.md` – defines Satoshi in canon.
- `/canon/btc_world/BTC_HEX_NETWORK_CANON.md` – describes the hex-sphere
  representation of the Bitcoin network.
- `/canon/btc_world/ENTITIES.md` – enumerates BTC World entities
  (blocks, nodes, miners, etc.).

These files must obey the world rules, world overview, universal rules
and canon invariants.

## World Implementation Specifications

Implementation specs specialise the shared architecture for a specific
world. They do not replace doctrine; instead they explain how a
world’s rules, canonical objects, rendering, data bindings and engine
semantics are expressed in concrete terms.

### HDL World Implementation Specs

| File | Purpose |
| --- | --- |
| `/canon/hdl_world/IDENTITY_ANCHOR.md` | Defines how a user’s HDL handle is anchored in the world. It bridges the handle, linked wallets, Proof Engine output and spatial representation, determining where and how a user appears in the universe. |
| `/canon/hdl_world/ROUTING_ENGINE.md` | Specifies how HDL resolves a handle into the correct wallet, chain and execution path. It makes “send BTC to @grandma” work without requiring the sender to understand chain nuances. It prioritises safety, determinism and asset correctness before cost optimisation. |
| `/canon/hdl_world/WORLD_TOPOLOGY.md` | Describes the topological structure of HDL World, including portals, horizons, spaces and flows. |
| `/canon/hdl_world/PROOF_ENGINE.md` | Defines the system that determines and validates a user’s Genesis (On-Chain Since) and conviction. It establishes badge tiers (claimed, social, on-chain) and processes data from on-chain and off-chain sources. |
| `/canon/hdl_world/PROOF_ENGINE_LORE.md` | Provides narrative context and philosophy for the Proof Engine. It explains why conviction matters and how it shapes identity. |

### Bitcoin World Implementation Specs

| File | Purpose |
| --- | --- |
| `/canon/btc_world/ENGINE_PIPELINE.md` | Specialises the universal engine pipeline for BTC World. It adapts shared stages to Bitcoin data, defines world-specific rendering targets (DOM, 3D, VR) and explains how hexes and particle flows represent transactions. This file must reference `../shared/ENGINE_PIPELINE.md` as its parent pipeline. |
| `/canon/btc_world/DATA_BINDING.md` | Describes how Bitcoin network data (blocks, transactions, mempool) binds to visual metrics like position, colour and motion. |
| `/canon/btc_world/RENDERING_IMPL.md` | Explains how BTC World implements rendering using instancing, camera behaviour and performance strategies across 2D, 3D and VR targets. |
| `/canon/btc_world/BTC_HEX_NETWORK_CANON_FULL_SPEC.md` | Provides a full technical specification of the hex-sphere representation of the Bitcoin network, including coordinate systems, clustering, adjacency and rendering details. |

## Current Worlds

The HDL universe currently defines two worlds. Each world resides in its own
folder under `/canon/` and contains doctrine, rules, entity lists and
implementation specs.

### HDL World

Location: `/canon/hdl_world/`
Purpose: The safe central environment of the universe. It contains
the helmet interior, OD, the Twelve Disciples, wallet identity
mapping and navigation portals. HDL is the hub connecting all
ecosystems.
Core doctrine: `_WORLD_OVERVIEW.md`, `RULES.md`, `ENTITIES.md`, `OD.md`, `DISCIPLES.md`.
Supporting implementation docs: `IDENTITY_ANCHOR.md`,
`ROUTING_ENGINE.md`, `WORLD_TOPOLOGY.md`, `PROOF_ENGINE.md`,
`PROOF_ENGINE_LORE.md`.

### Bitcoin World

Location: `/canon/btc_world/`
Purpose: Represents the Bitcoin ecosystem. Key entities include
Satoshi Nakamoto, Genesis block structures, mining constructs, the BTC
hex network and the Bitcoin origins document.
Core doctrine: `_WORLD_OVERVIEW.md`, `RULES.md`, `ENTITIES.md`,
`OD.md`, `BTC_HEX_NETWORK_CANON.md`, `SATOSHI.md`.
Supporting implementation docs: `ENGINE_PIPELINE.md`,
`DATA_BINDING.md`, `RENDERING_IMPL.md`, `BTC_HEX_NETWORK_CANON_FULL_SPEC.md`.

## Future Worlds

Additional worlds will be introduced over time (e.g. Ethereum World,
XRP World, Solana World). Each new world must include at minimum:

- `_WORLD_OVERVIEW.md`
- `RULES.md`
- `ENTITIES.md`
- any world-specific objects (e.g. origins document, key entities)
- implementation specs that specialise the shared architecture for that
  world

All worlds must connect through HDL and respect the universal rules and
canon invariants.

## Canon Update Process

Canon evolves through a deliberate, transparent process:

- Discovery occurs through discussion, exploration and usage.
- Proposed doctrine is drafted and reviewed.
- Canon documents are updated via pull requests and community
  consensus.
- The repository becomes the official source of truth. If
  conversation and repository disagree, the repository wins.

## Final Principle

The HDL World Engine is not merely a codebase. It is the constitution of
a universe. Technology may change, rendering engines may evolve, and
new worlds may appear. Canon remains the anchor that keeps the system
coherent, safe and meaningful. Maintain it with care.
