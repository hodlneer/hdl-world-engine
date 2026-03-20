# HDL World — Identity Anchor (Canonical)

## Purpose

The Identity Anchor defines how a user (via their HDL handle) is positioned within the HDL World Engine.

It bridges:

- Handle (identity)
- Wallet(s) (ownership)
- Proof Engine (credibility)
- World (visual representation)

The Identity Anchor is how a user becomes **visible inside the blockchain universe**.

## Related Documents

Parent world docs:
- `_WORLD_OVERVIEW.md`
- `RULES.md`
- `ENTITIES.md`

Shared dependencies:
- `../shared/WALLET_MODEL.md`
- `../shared/ENGINE_PIPELINE.md`

Sibling implementation docs:
- `ROUTING_ENGINE.md`
- `WORLD_TOPOLOGY.md`
- `PROOF_ENGINE.md`

---

## Core Concept

> Users are not mapped to coins.  
> Users are mapped to **presence within the network field**.

---

## Definition

An Identity Anchor represents a user’s:

- Location within a world (BTC, ETH, etc.)
- Activity footprint
- Genesis (time of belief)
- Network relationships

---

## Anchor Model

```ts
type IdentityAnchor = {
  handle: string,
  world: string,
  position: [number, number, number],
  clusterId: string,
  intensity: number,
  genesisYear: number,
  connections: string[]
}
```

---

## Inputs

### 1. Handle
- Primary identity (HDL handle)

### 2. Wallets
- Linked multi-chain wallets

### 3. Proof Engine Output
- Genesis Year
- Validation Tier

### 4. Activity Signals
- Transaction frequency
- Value movement
- Interaction density

---

## Positioning Logic

### World Assignment
- Determined by dominant chain usage
- Example:
  - BTC heavy → BTC World
  - ETH heavy → ETH World

---

### Cluster Assignment

Users are placed into **activity clusters**:

- High activity → dense regions
- Low activity → sparse regions

Clusters represent:

- Network hotspots
- Behavioral similarity
- Flow density

---

### Spatial Position

Position is derived from:

- cluster centroid
- slight randomized offset
- smoothing for stability

---

## Intensity (Visual Weight)

Represents:

- activity level
- engagement
- presence

Not wealth.

---

## Genesis Layer

Each anchor carries:

- genesisYear
- validation tier

Displayed as:

ON-CHAIN SINCE {year}

---

## Connections

Anchors may visually connect to:

- frequent counterparties
- shared cluster members
- social graph (future)

---

## Visual Representation

Each Identity Anchor renders as:

- Core Node (user presence)
- Halo (activity)
- Badge (genesis)
- Connection Lines (relationships)

---

## Behavior

### Idle State
- Soft glow
- Stable position

### Active State
- Increased halo intensity
- subtle motion

### Focused State
- Enlarged
- metadata visible
- surrounding dimmed

---

## LOD Behavior

### Far
- Anchor not individually visible
- contributes to field

### Mid
- Anchor becomes point light

### Near
- Full node + halo

### Focus
- Full metadata + interaction

---

## Cross-World Identity

Users may exist in multiple worlds:

- BTC
- ETH
- SOL

Each world maintains:

- its own anchor
- shared identity reference

---

## Movement

Anchors may shift over time based on:

- changing activity
- new chain usage
- evolving behavior

Movement must be:

- smooth
- meaningful
- non-chaotic

---

## Privacy

Users may:

- hide exact position
- obfuscate connections
- reduce visibility

---

## Rules

- Anchors must never misrepresent data
- No arbitrary placement
- Movement must reflect real change
- Genesis cannot be altered without proof

---

## Final Statement

> The Identity Anchor is the manifestation of a user within the HDL universe.

It answers:

Where are you?  
When did you arrive?  
How do you move?

---

## Status

**Canonical — Identity Mapping Layer**
