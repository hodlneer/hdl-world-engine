# BTC World Origins Document (OD)

## Purpose

The BTC World Origins Document records the conceptual and technical foundation of the Bitcoin World within the HDL engine. It explains why we chose to represent Bitcoin's network the way we did, outlines the narrative that ties the world to the broader HDL story, and provides a reference for designers and developers when extending or revising the BTC world.

## Background

Bitcoin was the first blockchain to demonstrate a truly decentralized monetary network. Its capped supply of 21 million coins, permissionless peer-to-peer design, and emergent global consensus inspired countless other protocols. When we set out to model Bitcoin inside the HDL engine, we initially attempted to map each of the 21 million coins to a hexagonal tile on a sphere. While elegant on paper, the idea proved impractical: dividing a sphere into 21 million unique, addressable hexagons required a level of geometric subdivision that would have strained both rendering and gameplay.
A second challenge was that coins are fungible units; linking a tile to a specific satoshi created messy edge-cases whenever coins were split or merged.

## Choosing the Right Abstraction

After much experimentation, we chose to anchor the BTC world's geometry to network nodes rather than individual coins. The Bitcoin network is maintained by roughly 10-15 thousand nodes at any given time. Each node verifies transactions, propagates blocks, and collectively enforces the consensus rules. Mapping one hexagonal tile to each node produces a sphere with a few tens of thousands of hexes-dense enough to suggest a continuous surface, yet small enough to manage computationally. This decision conveys two important principles:

Decentralization over Ownership: Bitcoin's strength lies in its distributed architecture. Representing nodes rather than coins keeps the focus on consensus and collaboration, not accumulation.

Accessibility: The total number of tiles remains comprehensible. Players can imagine that each tile has a guardian node behind it, anchoring the world to real-world infrastructure.

## Design of the Sphere

The BTC world is depicted as a sphere constructed from tessellated hexagons. A small pentagonal seam is unavoidable when tiling a sphere with hexes; we incorporate twelve pentagons to allow a consistent hex lattice across the majority of the surface. Each hex tile corresponds to a node and can display metadata such as the node's uptime, geographical distribution (aggregated for privacy), and perhaps the miner identity when relevant. Tiles may be color-coded to show whether a node is currently online, participating in mining, or running archival hardware. For immersive interaction, players can click on a tile to view educational material about how Bitcoin works and how to run a node yourself.

## Linking Users to Tiles

While tiles represent nodes, users still want to see their personal relationship to Bitcoin reflected in the world. To accommodate this, the engine records the amount of BTC that an account holds (or has ever held) and assigns badges or decorative elements accordingly. For example:

Owning at least one full BTC might allow the player to place a small flag on a tile of their choice (without claiming ownership of the node).

Early adopters (e.g., wallets seeded before 2013) could receive a vintage badge.

Running a full node and linking it to your HDL profile could grant stewardship of the corresponding tile, enabling you to customize its appearance or add educational content.

## Narrative Context

Within the broader HDL universe, the BTC world occupies a special place. It is the oldest of the on-chain worlds and serves as a historical foundation for everything that followed. A central narrative thread invites visitors to travel back to the pseudonymous creation of Bitcoin, explore the cypherpunk roots of the movement, and witness how a handful of enthusiasts launched a financial revolution. This story is interwoven with the personal heritage themes of HDL: diaspora communities funding node hardware in their home countries; local artists designing tile patterns; and children discovering that a simple Raspberry Pi can participate in a global network.

## Future Extensions

The BTC world will evolve alongside Bitcoin itself. As the network scales through technologies like the Lightning Network, sidechains, and vault-style custody solutions, additional layers could be added around or within the sphere. Likewise, if the node count changes dramatically or if new classes of participants (e.g., watch-only nodes or mobile miners) become significant, the tiling scheme may be revisited. The important thing is that the BTC world remains anchored in its core principles: decentralization, transparency, and permissionless participation.

This Origins Document should be read together with btc_world/RULES.md and btc_world/ENTITIES.md, which define the specific behaviors, entities, and legalities within the BTC world. For detailed discussion on the geometric representation of the network, see BTC_HEX_NETWORK_CANON_FULL_SPEC.md.
