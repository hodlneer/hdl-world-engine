# BTC World — Data Binding Specification

## Purpose

This document defines how **real Bitcoin network data** is translated into:

- Geometry state
- Particle behavior
- LOD transitions
- Visual intensity

This is the bridge between:

**Blockchain reality → HDL visual experience**

Without this layer, BTC World is decorative.

With this layer, BTC World becomes **truthful, alive, and educational**.

---

## Core Principle

> Every visual change in BTC World must be traceable to a real or derived data signal.

No arbitrary animation.  
No fake motion.  
Everything maps back to **Bitcoin network state**.

---

## Data Sources

### Primary Sources (Recommended)

- Full Node (Bitcoin Core RPC)
- Public APIs (fallback only)
- Indexers (optional optimization)

---

## Key Data Streams

| Data Type            | Description |
|---------------------|------------|
| Mempool Data        | Unconfirmed transactions |
| Block Data          | Confirmed blocks |
| Node Data           | Active node distribution |
| Fee Rates           | Transaction prioritization |
| Network Stats       | Hash rate, difficulty |
| Address Activity    | Transaction frequency |

---

## Update Frequencies

| Data Type        | Frequency |
|-----------------|----------|
| Mempool         | 1–3 sec |
| Blocks          | Event-based |
| Node Data       | 30–60 sec |
| Fee Rates       | 5–10 sec |
| Network Stats   | 10–30 sec |

---

## Geometry Binding (Truth Layer)

### Hex Node Tiles

**Source:**
- Node data (aggregated)

**Mapping:**

| Data | Visual |
|------|--------|
| Node online | Tile visible |
| Node offline | Tile dimmed |
| Node activity | Pulse intensity |

---

### User Wallet Binding

**Source:**
- Wallet API (user-connected)

**Mapping:**

| Data | Visual |
|------|--------|
| Balance > 0 | Badge enabled |
| ≥ 1 BTC | Flag unlock |
| Early wallet | Vintage marker |

---

## Particle Binding (Life Layer)

### 1. Transaction Flow Mapping

**Source:**
- Mempool transactions

**Mapping Logic:**

| Data | Visual |
|------|--------|
| Transaction | Particle stream |
| Fee rate | Speed + brightness |
| Size (bytes) | Trail thickness |
| Age | Fade-out duration |

---

### 2. Mempool Turbulence Mapping

**Source:**
- Total mempool size

| Data | Visual |
|------|--------|
| High mempool | Dense turbulence |
| Low mempool | Calm field |
| Sudden drop | Turbulence collapse |

---

### 3. Block Formation Mapping

**Source:**
- Block creation events

| Data | Visual |
|------|--------|
| New block | Field collapse |
| Block size | Collapse intensity |
| Time since last block | Field tension buildup |

---

### 4. Energy Halos (Node Activity)

**Source:**
- Transaction throughput per node

| Data | Visual |
|------|--------|
| High activity | Strong halo |
| Idle node | Minimal glow |

---

### 5. Global Network Field

**Source:**
- Hash rate
- Transaction volume

| Data | Visual |
|------|--------|
| High hash rate | Strong directional flow |
| Low activity | Weak ambient motion |

---

## Derived Metrics

### Network Pressure Index (NPI)

NPI = mempool_size / avg_block_capacity

---

### Transaction Priority Score

TPS = fee_rate / network_median_fee

---

### Activity Density

AD = tx_count / node_count

---

## Smoothing & Stability

- Moving averages (5–10 sec window)
- Exponential smoothing
- Threshold damping

Rule:
> No visual should flicker due to raw data spikes.

---

## LOD Data Scaling

### Far View
- Aggregated metrics only

### Mid View
- Clustered flows

### Near View
- Individual transactions visible

### Focus View
- Full metadata

---

## Performance Strategy

### Data Ingestion
- WebSocket preferred
- Polling fallback

### Processing
- Transform data once
- Store in GPU-friendly buffers

### Rendering
- Shader-driven updates
- Avoid CPU loops

---

## Fallback Mode

If live data fails:
- Use simulated data
- Mark as simulation mode
- Maintain continuity

---

## Security & Privacy

- Never expose raw wallet data
- Aggregate node location data
- Avoid deanonymization

---

## Final Canonical Statement

> BTC World is not animated.  
> It is **driven**.

Every particle, every pulse, every collapse must be rooted in:

- Real data  
- Derived meaning  
- Observable truth  

When the Bitcoin network changes,  
the world must change with it.
