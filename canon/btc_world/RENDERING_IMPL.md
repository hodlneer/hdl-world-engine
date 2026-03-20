# BTC World - Rendering Implementation

## Purpose

This document defines how the **canonical rendering system** is applied specifically to the **BTC World**.

It translates:

- Rendering Strategy (global)
- Particle Systems (shared)

into a **Bitcoin-native visual language**.

BTC World is not decorative.

It is a **living visualization of the Bitcoin network**.

---

## Core Interpretation

> BTC is not a place.
>
> It is a **network under constant pressure**.
>
> The world must feel:
>
> - Alive
> - Congested at times
> - Fluid but constrained
> - Deterministic, not chaotic

---

## Layer Mapping (BTC-Specific)

### 1. Canonical Geometry Layer (Truth)

Represents **what actually exists in Bitcoin**.

#### Components

- Hex Node Grid (wallets / addresses)
- Genesis Cube (Satoshi anchor)
- Portals (cross-world bridges)
- OD Anchors (AI presence points)
- Wallet Identity Nodes (user-bound)

#### Rules

- Fully instanced
- Clickable / inspectable
- Metadata-bound (wallet, tx history, etc.)
- Stable across sessions

#### Visual Behavior

- Static base structure
- Subtle pulse allowed (low frequency)
- Never chaotic

---

### 2. Particle Motion Layer (Life)

Represents **Bitcoin activity in motion**.

This is where BTC becomes visible.

---

## Particle System Mapping

### A. Transaction Flow (FLOW SYSTEM)

**Represents:**
Movement of BTC between addresses

**Behavior:**

- Directed paths between nodes
- Curved trajectories (not straight lines)
- Speed tied to:
  - Fee priority
  - Network congestion

**Visual Traits:**

- Thin luminous trails
- Color shift:
  - Low fee -> dim / slow
  - High fee -> bright / fast

**Implementation:**

- GPU instanced lines or point trails
- Precomputed path curves
- Shader-based motion

---

### B. Mempool Turbulence (TURBULENCE SYSTEM)

**Represents:**
Unconfirmed transaction pressure

**Behavior:**

- Chaotic swirl above node regions
- Density increases with congestion
- Rotational + noisy movement

**Visual Traits:**

- Fog-like particle clouds
- Pulsing density
- Occasional "bursts" when blocks clear

**Implementation:**

- Curl noise fields
- Density field driven by mempool size
- GPU particles (no CPU loops)

---

### C. Mining / Block Formation (FIELD SYSTEM)

**Represents:**
Consensus and block creation

**Behavior:**

- Field contraction toward block center
- Sudden collapse -> block confirmation event

**Visual Traits:**

- Gravitational pull effect
- Bright flash at confirmation
- Ripple outward after block is mined

**Implementation:**

- Vector field simulation
- Time-based contraction curves
- Event-driven shader burst

---

### D. Energy Halos (EMITTER SYSTEM)

**Represents:**
Node activity / importance

**Behavior:**

- Continuous emission around active nodes
- Radius tied to:
  - Transaction frequency
  - Balance weight (optional)

**Visual Traits:**

- Soft glowing halos
- Breathing/pulsing effect
- Subtle particle emission outward

---

### E. Ambient Network Field (FIELD SYSTEM)

**Represents:**
Overall network health

**Behavior:**

- Global slow-moving field
- Density reflects:
  - Total activity
  - Hash rate (optional mapping)

**Visual Traits:**

- Faint drifting particles across entire world
- Slight directional bias (global flow)

---

## LOD Behavior (BTC World)

### Far Distance

- Appears as a **glowing energy sphere**
- No visible nodes
- Only:
  - Ambient field
  - Light flow hints

---

### Mid Distance

- Hex grid begins to emerge
- Transaction flows become visible
- Mempool turbulence becomes readable

---

### Near Distance

- Individual nodes visible
- Particle systems become localized
- Halos and flows clearly tied to nodes

---

### Focus (Interaction)

- Geometry dominates
- Particles become supportive context
- Metadata overlays activate

---

## Behavioral Coupling (Critical)

Particles must be driven by **real or simulated BTC data**.

### Data Inputs

- Transaction volume
- Mempool size
- Block time
- Fee rates

---

### Mapping Rules

| Data Signal | Visual Output |
| --- | --- |
| High mempool | Dense turbulence |
| Fast blocks | Frequent field collapses |
| High fees | Faster/brighter flows |
| Low activity | Sparse particle presence |

---

## Performance Constraints

### MUST

- GPU-driven particles
- Instanced geometry for nodes
- Zero allocations per frame
- Bounded particle counts

### MUST NOT

- Per-particle CPU updates
- Object-per-transaction models
- Unbounded emitters

---

## Visual Philosophy (BTC-Specific)

BTC is:

- Deterministic -> avoid randomness without meaning
- Pressure-driven -> emphasize tension fields
- Scarce -> avoid visual clutter

---

## What to Avoid

- Arcade-like particle spam
- Symmetrical "perfect" motion (BTC is uneven)
- Pure chaos (must always feel rule-driven)

---

## What to Emphasize

- Flow under constraint
- Pressure buildup and release
- Network-wide coherence

---

## Example Frame Breakdown

**Scene Moment: High Congestion**

- Dense turbulence clouds above regions
- Slow-moving transaction trails
- Bright bursts when block clears
- Halos intensify around active nodes

---

**Scene Moment: Low Activity**

- Sparse flow lines
- Minimal turbulence
- Calm ambient field
- Nodes softly glowing

---

## Final Canonical Statement

> BTC World is not a visualization of transactions.
>
> It is a **living pressure system** where:
>
> - Flow reveals value movement
> - Turbulence reveals congestion
> - Fields reveal consensus
> - Geometry reveals truth
>
> And together, they make Bitcoin **visible as a living organism**.
