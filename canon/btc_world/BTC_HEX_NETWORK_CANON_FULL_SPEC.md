# BTC WORLD — HEX NETWORK CANON (FULL SPEC)

## Purpose

This document defines the complete technical and canonical specification for the BTC Hex Network.

It bridges:

- Bitcoin protocol data
- Visual representation
- Interaction systems
- Rendering architecture

This is the source of truth for all implementations.

---

# 1. SYSTEM MODEL

## 1.1 Concept

The BTC Hex Network is a spherical, non-contact hex grid where:

- Each hex = wallet interface (observer abstraction)
- Network = adoption + activity visualization
- Blockchain = separate layer (not the dome)

---

## 1.2 Separation of Concerns

| Layer | Responsibility |
|------|------|
| Blockchain | Truth (blocks, transactions) |
| Nodes | Validation |
| Hex Network | Visualization of participation |
| HDL World | User interaction layer |

---

# 2. DATA MAPPING (CRITICAL)

## 2.1 Wallet Representation Model

Since Bitcoin is UTXO-based:

### Canon Decision:
A "Hex" represents a clustered wallet identity, not a single address.

---

## 2.2 Clustering Strategy

Hexes are derived from:

- Address clustering heuristics
- Wallet-level aggregation
- Exchange grouping (optional abstraction layer)

---

## 2.3 Data Inputs

Each hex receives:

type HexData = {
  id: string
  activityScore: number
  txCount: number
  lastActive: timestamp
  valueFlow: number
  clusterSize: number
}

---

## 2.4 Activity Score Formula (example)

activityScore =
  (txCount * weightA) +
  (recentActivity * weightB) +
  (valueFlow * weightC)

---

# 3. GEOMETRY SYSTEM

## 3.1 Base Grid

- Hex grid generated using axial coordinates (q, r)
- Converted to 3D spherical projection

---

## 3.2 Spherical Projection

x = radius * cos(theta) * sin(phi)
y = radius * sin(theta) * sin(phi)
z = radius * cos(phi)

---

## 3.3 Dome Constraint

- Only render upper 85% of sphere
- Remove lower hemisphere
- Add ground plane reference

---

## 3.4 Hex Spacing

- No collisions
- Fixed gap between hexes
- Floating positioning

---

# 4. RENDERING SYSTEM

## 4.1 Three.js Requirements

- InstancedMesh REQUIRED
- GPU-driven transforms
- Frustum culling
- LOD (Level of Detail)

---

## 4.2 Hex Mesh

Each hex:

- Geometry: 6-sided flat prism
- Optional depth extrusion
- Shader-based material

---

## 4.3 Shader Behavior

Controls:

- Pulse animation
- Color gradients
- Interaction highlight
- Activity glow

---

# 5. INTERACTION MODEL

## 5.1 Hover

- Highlight hex
- Show minimal tooltip

---

## 5.2 Click

Triggers:

onHexSelect(hexId)

---

## 5.3 Expand

Hex transitions into:

- 3D panel
- Detailed wallet cluster view

---

## 5.4 Drill Down

User can:

- View transaction flows
- Track movement
- Navigate connections

---

# 6. TRANSACTION VISUALIZATION

## 6.1 Representation

Transactions = moving energy signals

---

## 6.2 Flow System

- Bezier curves between hexes
- Particle-based motion
- Directional animation

---

## 6.3 States

| State | Visual |
|------|------|
| Pending | soft pulse |
| Confirmed | solid path |
| Completed | fade trail |

---

# 7. TEMPORAL ENGINE

## 7.1 Real-Time Mode

- Live data streaming
- Continuous updates

---

## 7.2 Replay Mode (Optional)

- Historical playback
- Time scrubbing

Constraint:
Replay = observational only

---

# 8. SCALING STRATEGY

## 8.1 Initial Load

- 30,000 hex baseline

---

## 8.2 Expansion Strategy

- Chunk-based loading
- Region prioritization
- Activity-based rendering

---

## 8.3 Millions of Nodes

Handled via:

- Aggregation layers
- Dynamic clustering
- LOD degradation

---

# 9. PERFORMANCE RULES

Must maintain:

- 60 FPS target
- GPU instancing
- Minimal CPU overhead

---

# 10. DECENTRALIZATION ENFORCEMENT

## 10.1 Visual Constraints

- No central node
- No dominant hex
- No hierarchy

---

## 10.2 Distribution Algorithm

- Even spatial spread
- Activity variation allowed
- No clustering implying control

---

# 11. CROSS-LAYER CONSISTENCY

## 11.1 DOM Version

- 2D projection
- Simplified interaction

---

## 11.2 3D Version

- Full dome
- Interactive

---

## 11.3 VR Version

- Immersive interior
- Spatial navigation

---

## 11.4 Canon Rule

All layers must represent the same underlying data.

---

# 12. FORBIDDEN IMPLEMENTATIONS

The system must NEVER:

- Treat hexes as accounts
- Display balances as stored objects
- Introduce central hubs
- Fake transaction success
- Simplify mining into deterministic outcomes

---

# FINAL NOTE

The BTC Hex Network is a translation layer.

It does not replace Bitcoin.  
It reveals it.

It turns:

- Invisible systems → visible structure  
- Abstract data → spatial experience  
- Network activity → living motion  

Without ever breaking the truth.
