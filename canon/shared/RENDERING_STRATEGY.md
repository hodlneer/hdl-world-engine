# HDL World Engine - Rendering Strategy (Canonical)

## Purpose

This document defines the **canonical rendering strategy** for all HDL worlds. It establishes how visual systems should be structured to balance:

* Performance (real-time, scalable)
* Meaning (canonical, interactive, persistent)
* Aesthetic (alive, cinematic, symbolic)

This is a **non-negotiable architectural guideline**. All worlds (BTC, ETH, future chains, and abstract realms) must adhere to this layered approach.

## Related Documents

Parent navigation:
- `../CANON_INDEX.md`

Shared architecture siblings:
- `ENGINE_PIPELINE.md`
- `VISUALIZATION_RULES.md`
- `LOD_STRATEGY.md`
- `PARTICLE_SYSTEMS.md`

World specializations:
- `../btc_world/RENDERING_IMPL.md`

---

## Core Principle

> **Use particles to show that the world is alive. Use geometry to show what the world is.**

---

## The Three-Layer Rendering Model

### 1. Canonical Geometry Layer ("Truth Layer")

**Purpose:**
Defines all objects that carry meaning, identity, and interaction.

**Characteristics:**

* Persistent
* Selectable / clickable
* Metadata-bound
* Rule-governed
* Stable across sessions

**Implementation:**

* Instanced meshes (preferred for scale)
* Structured scene graph objects
* GPU-friendly batching where possible

**Examples:**

* BTC hex node tiles
* Portals
* OD presence anchors (Orchestrating Daemon links)
* Disciples
* Statues / Genesis objects
* Wallet-linked badges
* Landmark structures

**Rule:**
If the user can **interact with it, inspect it, or derive meaning from it**, it must exist in this layer.

---

### 2. Particle Motion Layer ("Life Layer")

**Purpose:**
Represents activity, flow, and invisible processes made visible.

This layer is responsible for making the world feel **alive, dynamic, and responsive**.

**Key Concepts Represented:**

* Network energy
* Activity pressure
* Consensus turbulence
* Invisible data becoming visible

**Characteristics:**

* Non-persistent
* Non-authoritative
* High-volume (10k-1M+ elements)
* Procedural / shader-driven
* Often non-interactive

**Implementation:**

* GPU particle systems (preferred)
* Shader-based motion fields
* Minimal CPU allocation (zero-GC patterns)
* Math-driven transformations (sin, cos, noise)

**Examples (BTC World):**

* Transaction trails flowing between nodes
* Mempool turbulence fields
* Energy halos around active regions
* Flow lines representing block propagation
* Ambient swarm density indicating network health

**Rule:**
If it represents **activity rather than identity**, it belongs here.

---

### 3. LOD Transition Layer ("Perception Layer")

**Purpose:**
Controls how the world transitions between abstraction and precision based on user distance and focus.

**Key Behavior:**

* Far -> Abstract (particles, fields)
* Mid -> Structured (patterns emerge)
* Near -> Precise (full geometry + interaction)

**Implementation:**

* Distance-based LOD switching
* Crossfading between particle systems and geometry
* Progressive detail reveal

**Example (BTC Sphere):**

* Far view: glowing energy sphere
* Mid view: hex distribution becomes visible
* Near view: individual node tiles are selectable
* Focus view: expanded metadata + user linkage

**Rule:**
The user should **never feel a hard switch** - only a smooth emergence of truth.

---

## Rendering Stack Philosophy

### 1. Particles for Energy

Use particles when visualizing:

* Flow
* Motion
* Density
* Pressure
* Emergent patterns

Particles are not objects - they are **signals**.

---

### 2. Instancing for Structure

Use instanced geometry when visualizing:

* Repeating canonical units
* Nodes
* Tiles
* Grids

This enables scale **without losing identity**.

---

### 3. Shaders for Scale

Use shaders when:

* Particle count exceeds CPU viability
* Motion must be continuous and fluid
* Effects require field-based simulation

Shaders handle:

* Massive swarm motion
* Field distortions
* Glow / energy layers

---

### 4. Geometry for Truth

Use explicit geometry when:

* The object has meaning
* The object must be interacted with
* The object must persist

---

## Performance Doctrine (Non-Negotiable)

### Zero Garbage Principle

* No allocations inside per-frame loops
* Reuse vectors, colors, buffers

### Math Over Logic

* Prefer continuous math functions over branching
* Use sin/cos/noise instead of if/else where possible

### GPU First for Scale

* Offload large particle systems to GPU
* Avoid CPU-bound loops for >10k elements

### Stability

* No NaN / Infinity values
* All outputs must remain bounded and predictable

---

## Hybrid System Example (BTC World)

### Geometry Layer

* Hex node grid (instanced)
* Genesis Cube
* Portals

### Particle Layer

* Transaction streams
* Mempool turbulence
* Energy halos

### LOD Behavior

* Distance: particle sphere
* Approach: hex grid emerges
* Interaction: node detail + wallet linkage

---

## What This Strategy Rejects

- Pure particle worlds with no structure
- Fully geometric worlds with no motion
- CPU-heavy per-object simulations at scale
- Visual-first decisions without canonical meaning

---

## What This Strategy Enables

- Massive scale without performance collapse
- Clear separation of meaning vs motion
- Cinematic and immersive environments
- Future compatibility with VR / AR / WebXR

---

## Final Canonical Statement

> The HDL World Engine is not a particle simulator.
>
> It is a **meaningful universe** where:
>
> * Geometry defines truth
> * Particles express life
> * Shaders enable scale
> * And the user reveals reality through proximity

---

## Status

**Canonical - Enforced Across All Worlds**

---

## Terminology Clarification

Throughout this document "OD" refers to the Operator/Orchestrating Daemon - the system-level intelligence that anchors canonical meaning and authorizes interaction in the HDL universe. The Orchestrating Daemon is defined in `hdl_world/OD.md`.

This usage is distinct from world-specific Origins Documents, which also use the "OD" abbreviation. For example, `btc_world/OD.md` records the story of the Bitcoin world.

LOD stands for Level of Detail and is a separate rendering term describing how fidelity changes with distance or focus. It is unrelated to the Orchestrating Daemon and should not be confused with any world's Origins Document.
