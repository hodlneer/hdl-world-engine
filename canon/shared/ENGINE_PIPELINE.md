# HDL World Engine — Engine Pipeline (Canonical)

## Purpose

This document defines the **universal engine pipeline** for all HDL worlds.

It describes how the HDL engine moves from:

- external or internal data
- through normalization and interpretation
- into world state
- into GPU-friendly buffers
- into shaders and final rendered output

This is the canonical architecture that all world-specific implementations inherit.

It is intentionally **world-agnostic**.

BTC, ETH, XRP, Solana, HDL World, and future worlds must all plug into this same engine structure, even when their data sources and visual semantics differ.

## Related Documents

Parent navigation:
- `../CANON_INDEX.md`

Shared architecture siblings:
- `WALLET_MODEL.md`
- `VISUALIZATION_RULES.md`
- `RENDERING_STRATEGY.md`
- `LOD_STRATEGY.md`
- `PARTICLE_SYSTEMS.md`

World specializations:
- `../btc_world/ENGINE_PIPELINE.md`

---

## Core Principle

> The HDL engine must render meaning through a deterministic pipeline.

No world should bypass the pipeline.

No render effect should exist without one of the following origins:

- canonical static definition
- user interaction state
- world-specific derived data
- system-generated simulation mode

Every visible behavior must be explainable.

---

## Pipeline Scope

This document defines the shared engine flow:

**Ingestion → normalization → derivation → smoothing → world state → LOD resolution → GPU upload → shader/material binding → frame render**

This is not a BTC document.

This is the architectural backbone of the HDL World Engine itself.

---

## High-Level Pipeline

```text
World Data Sources / Canon Inputs / User Inputs
    ↓
Ingestion Layer
    ↓
Normalization Layer
    ↓
Transform / Derivation Layer
    ↓
Temporal Stabilization Layer
    ↓
World State Store
    ↓
LOD / Visibility Resolver
    ↓
GPU Upload Layer
    ↓
Shader / Material Input Layer
    ↓
Frame Render
```

---

## Stage 1 — Ingestion Layer

## Purpose

Receive raw inputs from any source that can influence the world.

## Possible Input Sources

### A. Live External Data
Examples:

- blockchain node streams
- WebSocket feeds
- RPC endpoints
- indexed APIs
- market / network telemetry

### B. Canonical Static Data
Examples:

- world geometry definitions
- immutable entity metadata
- landmark locations
- portal definitions
- symbolic rules

### C. User State Inputs
Examples:

- connected wallet state
- selected object
- camera movement
- interaction focus
- profile metadata

### D. Simulation Inputs
Examples:

- fallback simulation mode
- demo environments
- educational scripted sequences
- local development stubs

---

## Ingestion Rules

- Every incoming payload must be timestamped.
- Every payload must be source-tagged.
- No raw source may write directly to rendering systems.
- Duplicate events must be deduplicated upstream.
- Out-of-order events must be handled safely.
- Ingestion must be resilient to missing or delayed data.

---

## Example Shared Event Shape

```ts
type EngineEvent = {
  id: string
  source: "ws" | "rpc" | "poll" | "canon" | "user" | "sim"
  world: string
  kind: string
  receivedAt: number
  payload: unknown
}
```

---

## Stage 2 — Normalization Layer

## Purpose

Convert raw, inconsistent inputs into stable engine-readable structures.

Different worlds may use different external sources, but the engine should consume normalized records.

## Responsibilities

- unify units
- unify time representations
- resolve null / optional fields explicitly
- validate required shape
- drop invalid records
- produce predictable internal objects

---

## Normalization Rules

- Time values should resolve to a single internal format.
- Units should be standardized before derivation.
- Optional data should never remain ambiguous.
- World-specific normalization logic should remain isolated from the core renderer.
- Normalization should be deterministic and testable.

---

## Stage 3 — Transform / Derivation Layer

## Purpose

Translate normalized input into **render-driving meaning**.

This is where raw records become signals that the world can use.

## Typical Derived Outputs

- intensity
- velocity
- pressure
- stability
- importance
- congestion
- trust/confidence
- emphasis
- event classification
- region activity

---

## Derivation Rules

- Raw values should not flow directly into shaders unless intentionally scalar.
- All derived values must be clamped into safe visual ranges.
- Derivation must remain explainable and inspectable.
- World-specific derivation should be separate from engine-generic orchestration.
- Derived values should be smoothing-ready.

---

## Stage 4 — Temporal Stabilization Layer

## Purpose

Prevent visual instability caused by noisy or bursty input data.

The engine must feel responsive without becoming jittery.

## Allowed Techniques

- moving averages
- exponential smoothing
- hysteresis
- threshold gating
- capped rate-of-change
- event burst windows

## Rules

- Stabilization must never erase meaning.
- Critical discrete events may bypass smoothing for the core trigger.
- Slow world state should smooth more heavily than urgent events.
- The user should perceive: **stable, truthful, alive**.

---

## Stage 5 — World State Store

## Purpose

Maintain the current authoritative visual state for a world.

This is the state the renderer reads from.

It is not raw source data.

It is not external API data.

It is the engine’s current interpretation of world truth.

---

## World State Domains

### A. Geometry State
Examples:

- visible canonical entities
- node / landmark activation
- portal availability
- badge or marker states
- instancing data

### B. Particle State
Examples:

- flow activity
- turbulence strength
- ambient density
- aura/halo intensity
- field coefficients

### C. Event State
Examples:

- latest triggered event
- active transitions
- recent confirmations
- shockwaves
- alerts / narrative cues

### D. Interaction State
Examples:

- hovered object
- selected object
- focus target
- active overlays
- inspect mode

### E. LOD State
Examples:

- far / mid / near / focus stage
- target visibility masks
- particle budget targets
- detail unlock flags

---

## World State Rules

- The renderer reads from world state only.
- External systems must never render directly from raw input.
- State mutation should be centralized.
- Updates should be batched when possible.
- World state should be serializable for debugging and replay.

---

## Stage 6 — LOD / Visibility Resolver

## Purpose

Resolve what should be shown at the current camera distance, screen-space scale, and interaction focus.

This stage protects performance and preserves meaning.

## Responsibilities

- choose detail level
- determine visibility masks
- allocate particle budgets
- enable or suppress overlays
- switch between aggregate and specific representations

## General LOD Model

### Far
- aggregate phenomena only
- broad energy / field representation
- no fine interactivity

### Mid
- structure emerges
- clustered motion
- simplified identities

### Near
- object-level fidelity
- localized activity
- selective labels / metadata

### Focus
- inspected object dominates
- exact metadata allowed
- surrounding noise reduced

---

## LOD Rules

- Transitions must be smooth, never abrupt.
- LOD decisions should consider both distance and user intent.
- Particle systems must scale with LOD.
- Metadata must not appear before the object is meaningfully readable.

---

## Stage 7 — GPU Upload Layer

## Purpose

Translate world state into compact renderable memory structures.

This stage prepares data for geometry instancing, particles, fields, and global uniforms.

## Common Buffer Classes

### Geometry Buffers
Examples:

- transform matrices
- instance color
- pulse / emphasis values
- active / hidden flags

### Particle Buffers
Examples:

- origins
- targets
- velocities
- life values
- densities
- coefficients
- intensities

### Global Uniform Buffers
Examples:

- time
- world pressure
- ambient density
- active LOD stage
- camera-dependent flags

---

## GPU Upload Rules

- Prefer contiguous typed arrays.
- Reuse buffers whenever possible.
- Avoid full reallocation every frame.
- Mark dirty ranges where feasible.
- Particle counts must always remain bounded.
- Upload cost must be measurable and debuggable.

---

## Stage 8 — Shader / Material Input Layer

## Purpose

Turn GPU-side state into visible behavior.

This is where meaning becomes:

- movement
- glow
- distortion
- density
- emphasis
- pulse
- reveal

## Shader Input Categories

### Geometry Shaders
Use for:

- canonical objects
- pulse / activity accents
- state-linked color shifts
- instance-level variation

### Particle Shaders
Use for:

- flow
- turbulence
- swarms
- field response
- halos

### Event Shaders
Use for:

- bursts
- ripples
- collapses
- confirmation flashes
- portal activations

### Overlay / Focus Shaders
Use for:

- inspected object emphasis
- dimming surrounding context
- selection signals
- HUD-linked transitions

---

## Shader Rules

- Shaders may stylize but not contradict data.
- Visual intensity must remain traceable to meaning.
- All shader outputs must be bounded and NaN-safe.
- Complexity should scale down gracefully in low-performance modes.
- Effects should enhance truth, not obscure it.

---

## Stage 9 — Frame Render Orchestration

## Purpose

Ensure the world updates in the correct order each frame or tick.

## Recommended Order

```text
1. Receive new events / inputs
2. Normalize
3. Derive
4. Stabilize
5. Update world state
6. Resolve LOD / visibility
7. Populate GPU buffers
8. Bind shader/material inputs
9. Render geometry
10. Render particles
11. Render overlays / focus UI
```

---

## Render Order Rules

- Geometry generally renders before supportive particles.
- Additive particles may render after geometry.
- Focus / UI overlays render last.
- Transparency ordering must be handled explicitly.
- Debug layers must be optionally insertable without changing the pipeline architecture.

---

## Performance Modes

## High Fidelity
Use:

- rich particles
- dense local effects
- high detail geometry
- broader overlay capacity

## Balanced
Use:

- reduced particle counts
- clustered representation
- moderate field complexity

## Low Power
Use:

- aggregated fields
- minimal particles
- focus-first detail only
- reduced overlay complexity

---

## Fallback & Resilience

## If Live Data Is Delayed
- continue with decaying last-known state
- mark data staleness internally
- reduce effect intensity gradually

## If Live Data Is Unavailable
- switch to simulation mode where appropriate
- preserve continuity
- never silently present simulation as live truth

## If Inputs Conflict
- prefer authoritative source order defined by the world implementation
- log conflicts
- resolve deterministically

---

## Observability / Debugging

## Required Debug Views

- raw input stream
- normalized record inspector
- derived signal inspector
- world state inspector
- LOD mask viewer
- buffer inspector
- shader uniform viewer

## Required Metrics

- ingestion latency
- normalization time
- derivation time
- smoothing time
- GPU upload size
- particle counts
- dropped events
- stale state age
- frame cost by layer

---

## Relationship to World-Specific Pipeline Files

A world-specific `ENGINE_PIPELINE.md` may exist, but only as a **specialization** of this shared canonical pipeline.

That means:

- `shared/ENGINE_PIPELINE.md` defines the architecture
- `btc_world/ENGINE_PIPELINE.md` defines BTC-specific application
- future worlds may do the same

World-specific engine documents must not replace or contradict this file.

They may only specify:

- source-specific ingestion
- world-specific normalization
- world-specific derived signals
- world-specific event semantics
- world-specific shader behaviors

---

## Guidance for Revising Existing World-Specific Files

If a world-specific pipeline file was written before this shared file existed, revise it so that it:

1. explicitly states it inherits from `shared/ENGINE_PIPELINE.md`
2. removes generic engine doctrine that now belongs here
3. focuses on world-specific bindings and behaviors
4. avoids redefining universal pipeline stages unless specialization is necessary

This keeps the engine clean and prevents architectural drift.

---

## Final Canonical Statement

> The HDL World Engine is not a pile of effects.
>
> It is a disciplined pipeline that converts:
>
> input → meaning → state → buffers → shaders → world
>
> The architecture must remain shared.
> The worlds may differ.
> The engine must not.

---

## Status

**Canonical — Shared Engine Doctrine**
