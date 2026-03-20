
# VISUALIZATION_RULES.md
## HDL / HODLNEER Network Visualization Rules

This document defines the rules governing how blockchain networks are visualized in HDL 3D environments.

## Related Documents

Parent navigation:
- `../CANON_INDEX.md`

Shared architecture siblings:
- `ENGINE_PIPELINE.md`
- `RENDERING_STRATEGY.md`
- `LOD_STRATEGY.md`
- `PARTICLE_SYSTEMS.md`

World specializations:
- `../btc_world/RENDERING_IMPL.md`
- `../btc_world/BTC_HEX_NETWORK_CANON.md`

---

# 1. Network Node Visualization Rule

Blockchain worlds are visualized using **network nodes**, not asset units.

Nodes represent **wallet participation in the network**, not coin supply.

Example:

Bitcoin world → nodes represent wallets participating in the Bitcoin network.

Nodes may be rendered as:

- hexagons
- spheres
- geometric cells
- lattice points

depending on the design of the world.

---

# 2. Bitcoin Sphere Rule

The Bitcoin Sphere is a symbolic visualization of the Bitcoin network.

Structure:

- sphere composed of hexagonal nodes
- each hex represents a wallet node

Hexes do NOT represent:

- individual Bitcoin
- satoshis
- supply units

They represent **wallet participants**.

---

# 3. Node Visual States

Nodes may visually represent participation using intensity or animation.

Example states:

dim → inactive wallet  
glow → active wallet  
bright → strong participation  
radiant → historically significant node

Exact values remain abstract to preserve visual clarity.

---

# 4. Structural vs Activation Layers

Two conceptual layers exist in network worlds.

Structural Layer

This layer defines the geometry of the network structure.

Nodes exist even if no HDL users are connected.

Activation Layer

When a user connects a wallet:

- the node activates
- the node illuminates
- the user profile links to that node

---

# 5. Scalability Rule

Network visualizations must remain computationally feasible.

Therefore asset supply must **never** determine geometry.

Incorrect approach:

21,000,000 BTC → 21,000,000 nodes

Correct approach:

wallet nodes → scalable network visualization

---

# 6. Narrative Visualization

Network worlds should tell the story of adoption.

Possible visual signals:

- early adopters near the core
- new users forming outer layers
- inactive nodes fading
- active nodes glowing

This allows users to explore blockchain adoption visually.

---

# 7. Canonical Principle

The core rule across all HDL worlds:

Hex = Network Node  
User = Node Activator  
Asset = Value flowing through the node
