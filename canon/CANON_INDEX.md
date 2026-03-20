# HDL Canon --- Index

This document is the **map of the HDL universe**.

It explains how the canon repository is structured and how authority
flows between documents.

Anyone building, extending, or interpreting the HDL World Engine should
begin here.

------------------------------------------------------------------------

# Canon Structure

The HDL canon is organized in **five layers of doctrinal authority**.

Higher layers override lower layers.

1.  CANON_INVARIANTS.md
2.  UNIVERSAL_RULES.md
3.  WORLD_OVERVIEW.md
4.  RULES.md
5.  ENTITY FILES

This hierarchy governs **truth and doctrine**.

In addition to the doctrinal stack, the repository also contains:

• shared architecture documents\
• world-specific implementation specifications\
• meta-governance and navigation documents

These supporting documents do not outrank doctrine, but they are part of
the canonical system and must remain consistent with it.

------------------------------------------------------------------------

# Meta Documents

The following documents help govern and navigate the canon repository,
but are not part of the doctrinal authority stack:

• CANON_INDEX.md\
• CANON_AUTHORITY.md

------------------------------------------------------------------------

# Shared Architecture

These documents define engine-level, rendering-level, and cross-world
implementation architecture shared by all worlds.

Files:

/canon/shared/ENGINE_PIPELINE.md\
/canon/shared/WALLET_MODEL.md\
/canon/shared/VISUALIZATION_RULES.md\
/canon/shared/RENDERING_STRATEGY.md\
/canon/shared/LOD_STRATEGY.md\
/canon/shared/PARTICLE_SYSTEMS.md

Purpose:

Defines how HDL systems move from data and identity into geometry,
particles, LOD, interaction, and rendered output.

These files are canonical architecture, but they remain subordinate to
the doctrinal hierarchy above.

------------------------------------------------------------------------

# Layer 1 --- Canon Invariants

File:

/canon/shared/CANON_INVARIANTS.md

Purpose:

Defines the **constitutional truths of the HDL universe**.

These rules never change without redefining HDL itself.

Examples include:

• HDL is the central world\
• HDL is permanently safe\
• Worlds remain separate\
• Portals are the only travel mechanism

All other documents must comply with these invariants.

------------------------------------------------------------------------

# Layer 2 --- Universal Rules

Files:

/canon/shared/UNIVERSAL_RULES.md\
/canon/shared/PORTALS.md\
/canon/shared/GLOSSARY.md\
/canon/shared/AGENTS.md\
/canon/shared/WALLET_MODEL.md\
/canon/shared/VISUALIZATION_RULES.md\
/canon/shared/RENDERING_STRATEGY.md\
/canon/shared/LOD_STRATEGY.md\
/canon/shared/PARTICLE_SYSTEMS.md\
/canon/shared/BRAND_SYSTEM.md

Purpose:

Defines rules that apply **across all worlds**.

Examples:

• how worlds connect\
• portal travel rules\
• terminology used across the universe

These rules govern the behavior of the entire system.

Additional shared canon:

shared/
    AGENTS.md
    WALLET_MODEL.md
    VISUALIZATION_RULES.md
    RENDERING_STRATEGY.md
    LOD_STRATEGY.md
    PARTICLE_SYSTEMS.md
    BRAND_SYSTEM.md

Description:

Defines the role, permissions, and constraints of AI agents operating within the HDL ecosystem.

Agents participate in the visitor layer but are not canonical authorities or symbolic entities.

WALLET_MODEL.md defines the identity, routing, and blockchain wallet layer model used across the HDL ecosystem.

VISUALIZATION_RULES.md defines cross-world rules for how blockchain participation is rendered in HDL environments.

RENDERING_STRATEGY.md defines the canonical layered rendering model balancing geometry, particles, and LOD across all HDL worlds.

LOD_STRATEGY.md defines how canonical objects transition from abstract energy to precise geometry as distance and focus change.

PARTICLE_SYSTEMS.md defines the Life Layer particle types and how motion, turbulence, fields, halos, and swarms should be used canonically.

BRAND_SYSTEM.md preserves the emerging HDL brand ethos, emotional tone, and movement-level framing without overriding doctrinal canon.

------------------------------------------------------------------------

# Layer 3 --- World Doctrine

Each world defines its own **world overview**.

Examples:

/canon/hdl_world/\_WORLD_OVERVIEW.md\
/canon/btc_world/\_WORLD_OVERVIEW.md

Purpose:

Explains:

• the identity of the world\
• spatial model\
• time model\
• atmosphere and mood

This document defines how the world should feel and exist.

------------------------------------------------------------------------

# Layer 4 --- World Rules

Files:

/canon/hdl_world/RULES.md\
/canon/btc_world/RULES.md

Purpose:

Defines the **operational rules of each world**.

Examples include:

• movement constraints\
• interaction rules\
• safety mechanics\
• consequences within that world

These rules must follow both the world overview and the universal rules.

------------------------------------------------------------------------

# Layer 5 --- World-Specific Canon Objects

Examples:

/canon/hdl_world/OD.md\
/canon/btc_world/OD.md\
/canon/hdl_world/DISCIPLES.md\
/canon/btc_world/BTC_HEX_NETWORK_CANON.md\
/canon/btc_world/SATOSHI.md\
/canon/btc_world/ENTITIES.md

Purpose:

Defines the **world-specific canonical objects, origins records, system
intelligence documents, and symbolic entities** that exist within a world.

These files must obey:

• world rules\
• world overview\
• universal rules\
• canon invariants

------------------------------------------------------------------------

# World Implementation Specs

These files specialize the shared architecture for a specific world.

They do not replace doctrine.

They explain how a world's rules, canonical objects, rendering, data
bindings, and engine semantics are actually expressed in implementation
terms.

### HDL World Implementation Specs

/canon/hdl_world/IDENTITY_ANCHOR.md\
/canon/hdl_world/ROUTING_ENGINE.md\
/canon/hdl_world/WORLD_TOPOLOGY.md\
/canon/hdl_world/PROOF_ENGINE.md\
/canon/hdl_world/PROOF_ENGINE_LORE.md

Purpose:

Defines how HDL identity, routing, topology, and proof systems work
inside the central world.

### BTC World Implementation Specs

/canon/btc_world/ENGINE_PIPELINE.md\
/canon/btc_world/DATA_BINDING.md\
/canon/btc_world/RENDERING_IMPL.md\
/canon/btc_world/BTC_HEX_NETWORK_CANON_FULL_SPEC.md

Purpose:

Defines how Bitcoin-specific data, rendering, and participation models
inherit from shared architecture and become concrete in BTC World.

------------------------------------------------------------------------

# Current Worlds

The HDL universe currently defines the following worlds.

### HDL World

Location:

/canon/hdl_world/

Purpose:

The central environment of the universe.

Contains:

• the helmet interior\
• OD\
• the Twelve Disciples\
• wallet identity\
• navigation portals

HDL is the safe hub connecting all ecosystems.

Core doctrine:

• /canon/hdl_world/_WORLD_OVERVIEW.md\
• /canon/hdl_world/RULES.md\
• /canon/hdl_world/ENTITIES.md\
• /canon/hdl_world/OD.md\
• /canon/hdl_world/DISCIPLES.md

Supporting implementation docs:

• /canon/hdl_world/IDENTITY_ANCHOR.md\
• /canon/hdl_world/ROUTING_ENGINE.md\
• /canon/hdl_world/WORLD_TOPOLOGY.md\
• /canon/hdl_world/PROOF_ENGINE.md\
• /canon/hdl_world/PROOF_ENGINE_LORE.md

------------------------------------------------------------------------

### Bitcoin World

Location:

/canon/btc_world/

Purpose:

Represents the Bitcoin ecosystem.

Key entities include:

• Satoshi Nakamoto\
• Genesis block structures\
• mining constructs\
• BTC hex network canon\
• BTC origins document

Supporting implementation docs include:

• /canon/btc_world/ENGINE_PIPELINE.md\
• /canon/btc_world/DATA_BINDING.md\
• /canon/btc_world/RENDERING_IMPL.md\
• /canon/btc_world/BTC_HEX_NETWORK_CANON_FULL_SPEC.md

This world visualizes the Bitcoin network and its historical identity.

------------------------------------------------------------------------

# Future Worlds

Additional worlds will be introduced over time.

Examples may include:

• Ethereum World\
• XRP World\
• Solana World

Each world must include:

• WORLD_OVERVIEW.md\
• RULES.md\
• ENTITIES.md

All worlds must connect through HDL.

------------------------------------------------------------------------

# Canon Update Process

Canon evolves through a deliberate process.

1.  Discovery occurs through discussion and exploration
2.  Proposed doctrine is drafted
3.  Canon documents are updated
4.  The repository becomes the official source of truth

If conversation and repository disagree:

The repository wins.

------------------------------------------------------------------------

# Final Principle

The HDL World Engine is not a codebase.

It is the **constitution of a universe**.

Technology may change.

Rendering engines may evolve.

New worlds may appear.

Canon remains the anchor.
