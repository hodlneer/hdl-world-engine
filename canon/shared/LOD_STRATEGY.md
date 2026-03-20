# HDL World Engine - LOD (Level of Detail) Strategy (Canonical)

## Purpose

In the HDL universe, Level of Detail (LOD) is not just a performance trick - it is a storytelling mechanism. This strategy defines how objects and phenomena transition from abstract energy to concrete form as users move closer or focus their attention. By controlling LOD we balance performance, meaning, and immersion across all worlds. Proper LOD ensures that the world remains responsive at scale and that truth is revealed gracefully rather than abruptly.

## Related Documents

Parent navigation:
- `../CANON_INDEX.md`

Shared architecture siblings:
- `RENDERING_STRATEGY.md`
- `PARTICLE_SYSTEMS.md`
- `VISUALIZATION_RULES.md`

World specializations:
- `../btc_world/RENDERING_IMPL.md`

## Principle: Distance Drives Revelation

LOD ties rendering fidelity to both camera distance and user intent. Objects far away should communicate only broad energy and structure, while objects nearby must reveal precise geometry and interactivity. As the user zooms in, details emerge progressively - particles condense into shapes, patterns become grids, and ultimately discrete nodes become selectable. The user should never feel a hard swap between levels; instead they should experience a smooth emergence of truth.

## LOD Stages

The HDL engine uses four canonical LOD stages. Each world may customize threshold distances, but the qualitative behavior must remain consistent.

| Stage | Primary Visuals | Intended Meaning |
| --- | --- | --- |
| Far - Abstraction | Energy fields, swarms, halos | Communicate network energy and global activity; no discrete objects |
| Mid - Structure | Emergent patterns (e.g., hex grids, flow lines) | Reveal underlying topology; hint at the canonical geometry that underpins the world |
| Near - Precision | Full instanced geometry with selectable nodes | Convey identity, allow selection and inspection, attach metadata |
| Focus - Depth | Expanded details, UI overlays, metadata panels | Provide deep context, wallet/agent linkage and interactive tools |

Guidelines:

Abstraction (far): Use procedural particle systems and shader fields to visualize abstract qualities like energy, pressure and turbulence. No individual objects should be selectable at this stage. This view is predominantly about feel.

Structure (mid): Begin to instantiate coarse geometry. Patterns such as hex tiles, grid outlines or orbiting bands emerge from the energy field. The geometry hints at the canonical layer but remains simplified for performance. Transitions between particles and geometry must be cross-faded, not abruptly swapped.

Precision (near): Switch fully to instanced geometry. Nodes, tiles and landmarks are selectable and their metadata can be inspected. Particle effects augment but do not obscure the geometry. This stage is where the meaning of objects becomes paramount; respect the Truth Layer rules from `RENDERING_STRATEGY.md`.

Focus (depth): When a user selects an object or zooms very closely, additional UI overlays, panels and animations appear. Wallet addresses, transaction histories or lore can be revealed here. This stage emphasizes clarity and should minimize decorative effects to avoid overwhelming the user.

## Implementation Guidelines

### 1. Distance-Based Switching

Define world-specific threshold distances (or screen-space size ratios) for the Abstraction -> Structure -> Precision transitions. The thresholds should be chosen empirically to balance performance and narrative fidelity. Use exponential falloff for very large worlds so that distant objects remain abstracted.

Evaluate the object's screen size rather than absolute distance when computing LOD to remain consistent across different device resolutions.

### 2. Cross-Fading and Blending

Smooth blending is essential. Rather than instantly swapping models at a threshold, use cross-fading between LOD levels. In traditional 3D engines, cross-fading reduces the number of triangles at distance and blends meshes over a defined transition width or time. In HDL:

When transitioning from particles to geometry (or between geometric LODs), fade out one representation while fading in the next. Use shader opacity, dithering or custom blending functions to achieve this. Avoid scaling objects in place as this can distort meaning.

Provide a configurable transition width for each stage. A larger width yields a longer blend and hides the switch better; a smaller width keeps transitions concise. Worlds may choose a single transition time for all LODs to minimize the number of concurrent blends.

Use GPU shaders to compute blend factors based on camera distance to minimize CPU overhead.

### 3. Progressive Detail Reveal

LOD is about progressive revelation, not degradation. As users approach:

Add, don't remove, information: start with abstract energy, then add structure and names, then add interactive panels.

Avoid popping in entire hierarchies of objects simultaneously. Instead, progressively instantiate geometry as the camera moves through nested distance thresholds.

Ensure that each stage prepares the user for what comes next; for example, in the BTC world the energy sphere suggests a hex grid inside, so the emergence of hex tiles feels natural.

### 4. Level Definitions and Files

Each canonical object should define its own LOD models or shaders. For example, a node tile might have a high-poly version for the Precision stage, a simplified icon for the Structure stage, and a particle swarm for the Abstraction stage. Keep the simplified versions consistent with the object's color and general shape so recognition is maintained.

Store LOD definitions in a `LOD` subdirectory next to the primary asset. Use naming conventions like `node_hex_LOD0.glb`, `node_hex_LOD1.glb`, etc. The engine will pick the correct file based on distance.

### 5. Interaction Considerations

Interactivity starts only at the Precision stage. Users should not be able to click or hover on objects when they are represented by particles or simplified glyphs. This prevents confusion and preserves performance.

When transitioning to Focus, suspend particle effects around the selected object to reduce clutter and emphasize the information panel.

### 6. Performance & Stability

LOD is a performance optimization: by reducing triangle counts at distance you can render large worlds smoothly. Ensure that distant versions of objects dramatically reduce polygon counts and texture resolution. Use billboards or imposters where appropriate.

Adopt the Zero Garbage Principle from the rendering strategy: allocate LOD resources up front and reuse them. Avoid spawning new particle systems on every camera move.

## Examples

### BTC World Example

Far: A glowing sphere representing total network energy. Colors and pulsations indicate hash-rate and mempool pressure.

Mid: A hex pattern gradually appears on the sphere, hinting at the hex grid of nodes. Flow lines begin to trace transaction flows.

Near: Individual hex tiles instantiate; users can select nodes to see state and wallet linkage. Particle streams overlay the geometry to visualize active transactions.

Focus: Selecting a node opens a panel with block headers, wallet history and narrative details. Surrounding particles dim to draw attention.

### General Chain Example

Far: A torus field visualizes total stake or energy; swirling turbulence indicates consensus activity.

Mid: Concentric rings denote shards or subnetworks; simple icons indicate validators.

Near: Full 3D validator models appear; stake balances and delegation relationships are inspectable.

Focus: Drilling down on a validator surfaces on-chain metadata, performance metrics and governance proposals.

## Tools & Prototyping

Use specialized tools to prototype motion and transitions. For example, the interactive particle site at `particles.casberry.in` is categorized as a Life Layer Prototyping Tool. It should be used for motion ideation, energy visualization testing and fast experimentation, but not as an engine replacement or architecture driver. Integrate lessons learned from prototype explorations into the LOD strategy before production.

## Rules & Rejections

LOD must never compromise truth. Worlds that over-build geometry at a distance waste resources and blur meaning. Worlds that over-use particles when detail is needed feel insubstantial. Avoid jarring transitions, unrealistic scaling, and abrupt pop-in effects. The goal is to guide users through discovery, not to hide information behind gimmicks.

## Status

Canonical - enforced across all worlds

## Terminology Clarification

LOD stands for Level of Detail. It refers to the technique of displaying different representations of an object depending on distance and importance. In this document, LOD describes how the HDL engine manages rendering fidelity and revelation across scales.

OD (Orchestrating Daemon) is the system-level intelligence defined in `hdl_world/OD.md`. It is separate from LOD. A world's Origins Document may also be abbreviated "OD", but that is unrelated to this strategy. See `canon/shared/GLOSSARY.md` for definitions.
