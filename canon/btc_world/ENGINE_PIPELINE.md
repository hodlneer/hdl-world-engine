# BTC World — Engine Pipeline (v2, Derived from Shared Canon)

## Purpose

This document defines how the **BTC World implements the shared HDL engine pipeline**.

It does NOT redefine the engine.

Instead, it specifies how Bitcoin data flows through the canonical pipeline defined in:

→ `shared/ENGINE_PIPELINE.md`

---

## Relationship to Shared Engine

> BTC World inherits the HDL Engine Pipeline.

This file provides:

- BTC-specific data sources
- BTC-specific normalization
- BTC-specific derived signals
- BTC-specific event semantics
- BTC-specific shader behaviors

All universal pipeline stages (ingestion → normalization → transform → etc.)
are defined in:

→ `shared/ENGINE_PIPELINE.md`

---

## BTC-Specific Pipeline Overview

```text
Bitcoin Data Sources
    ↓
BTC Ingestion Layer
    ↓
BTC Normalization
    ↓
BTC Derivation (Meaning Layer)
    ↓
BTC World State
    ↓
LOD Resolver (shared)
    ↓
GPU Upload (shared)
    ↓
BTC Shader Semantics
    ↓
Render Output
```

---

## Stage 1 — BTC Data Ingestion

## Sources

### Primary (Authoritative)

- Bitcoin Core RPC
- Mempool (local node)

### Secondary (Fallback)

- Public mempool APIs
- Fee estimation APIs
- Node distribution APIs

### Realtime

- WebSocket mempool feeds
- Block event streams

---

## BTC Ingestion Rules

- Prefer local node over external APIs
- Timestamp all events on arrival
- Deduplicate transactions by txid
- Handle mempool churn safely
- Never push raw data directly to render

---

## Stage 2 — BTC Normalization

## Purpose

Convert Bitcoin-native formats into engine-readable structures.

---

## Normalized Types

```ts
type BtcTx = {
  txid: string
  feeRate: number
  sizeBytes: number
  valueSat: number
  firstSeen: number
}

type BtcBlock = {
  hash: string
  height: number
  txCount: number
  sizeBytes: number
  time: number
}

type BtcNetwork = {
  mempoolCount: number
  mempoolBytes: number
  medianFeeRate: number
}
```

---

## Rules

- Standardize fee units
- Normalize time to epoch ms
- Drop malformed transactions
- Avoid partial records

---

## Stage 3 — BTC Derivation Layer

## Purpose

Translate Bitcoin data into visual meaning.

---

## Derived Signals

### Transaction Priority

```ts
priority = feeRate / medianFeeRate
```

Used for:
- flow speed
- brightness
- path priority

---

### Network Pressure

```ts
pressure = mempoolBytes / avgBlockCapacity
```

Used for:
- turbulence density
- turbulence frequency

---

### Block Tension

```ts
tension = timeSinceLastBlock / targetBlockTime
```

Used for:
- pre-block buildup
- confirmation burst

---

### Activity Density

```ts
density = mempoolCount / nodeCount
```

Used for:
- halo strength
- swarm density

---

## Stage 4 — BTC Smoothing Rules

- Smooth mempool fluctuations
- Do NOT smooth block events
- Apply exponential smoothing to pressure
- Clamp derived values

---

## Stage 5 — BTC World State

## Domains

### Geometry

- node tiles (hex grid)
- Genesis Cube
- user markers

### Particles

- transaction flows
- turbulence fields
- halos
- ambient field

### Events

- block confirmations
- mempool spikes

---

## Example State

```ts
type BtcWorldState = {
  pressure: number
  flowCount: number
  turbulence: number
  latestBlock?: string
}
```

---

## Stage 6 — LOD Behavior (BTC Overrides)

BTC uses shared LOD system but defines:

### Far
- energy sphere only

### Mid
- hex grid emerges
- clustered flows

### Near
- node-level flows
- halos

### Focus
- metadata overlays
- reduced noise

---

## Stage 7 — GPU Mapping (BTC)

### Flow Buffers

- origin
- target
- velocity (priority-driven)
- life

### Turbulence Buffers

- pressure
- noise frequency
- density

### Global Uniforms

- networkPressure
- blockTension
- ambientDensity

---

## Stage 8 — BTC Shader Semantics

### Flow Shader

- speed = priority
- brightness = fee strength
- fade = age

---

### Turbulence Shader

- density = mempool size
- motion = noise frequency

---

### Confirmation Shader

Triggered by:
- new block event

Effect:
- collapse → flash → ripple

---

## Stage 9 — Event Mapping

### Transaction

→ Flow particle created

---

### Mempool Spike

→ Turbulence increases

---

### Block Mined

→ Burst + pressure reset

---

## Performance Rules

- GPU particles only
- No per-tx CPU objects
- Clamp max active flows
- Reuse buffers

---

## What This File Does NOT Do

- Redefine pipeline stages
- Define generic engine behavior
- Replace shared pipeline

---

## Final Statement

> BTC World is an implementation of the HDL engine.
>
> The pipeline is shared.
> The data is Bitcoin.
> The behavior is derived.
>
> The world becomes real
> when Bitcoin moves.
