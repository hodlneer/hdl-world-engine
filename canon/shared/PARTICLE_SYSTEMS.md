# HDL World Engine - Particle Systems (Canonical)

## Purpose

Particle systems form the Life Layer of the HDL engine. They convey motion, pressure and energy that would otherwise remain invisible. This document defines the canonical particle system types - Flow, Turbulence, Fields, Halos and Swarms - and explains how each should be used to represent network phenomena. All HDL worlds must follow these definitions to maintain consistency across experiences.

## Related Documents

Parent navigation:
- `../CANON_INDEX.md`

Shared architecture siblings:
- `RENDERING_STRATEGY.md`
- `LOD_STRATEGY.md`
- `VISUALIZATION_RULES.md`

World specializations:
- `../btc_world/RENDERING_IMPL.md`

## Overview: What Is a Particle System?

A particle system emits and animates thousands or millions of small sprites or points to create the illusion of a fluid or amorphous entity. In game engines, noise functions can add turbulence to a particle system, causing particles to follow chaotic patterns; low noise frequency yields smooth, slowly changing motion, while high frequency makes particles change direction rapidly. By combining noise with vector fields, you can steer particles along currents and draw intricate patterns. A vector field is simply a grid of vectors in space; each particle samples the vector at its position and receives a force in that direction, making all particles move along the field. Perlin noise can generate smooth vector fields where nearby vectors have similar directions, creating organic flows.

Particle systems in the HDL engine are:

Non-persistent - they do not carry meaning or state across sessions.

GPU-driven - heavy simulation occurs on the GPU for performance.

Math-driven - noise, vector fields and simple functions define motion.

Enhancers - they amplify the Truth Layer without replacing it.

## Canonical Types

The Life Layer uses distinct particle patterns to tell different stories.

### Flow

Definition: Continuous streams of particles that move from one location to another along defined paths. Flows are ideal for visualizing data transfer and transaction propagation. They rely on vector fields; each particle samples the local vector and advances in that direction. Perlin or simplex noise can be used to generate smooth vector fields, ensuring flows meander organically.

Use cases:

Transaction trails between nodes in BTC World.

Block propagation lines showing data moving through a network.

Liquidity streams in a DeFi world.

Guidelines:

Keep flow particles small and fast to convey movement.

Use color gradients to encode direction or value (e.g., older vs newer transactions).

Use vector field data derived from real metrics (e.g., hash-rate distribution) to make flows meaningful.

### Turbulence

Definition: Chaotic swirling motion produced by noise functions. Turbulence gives energy fields a sense of unpredictability and pressure. In Blender and other graphics tools a Turbulence force field creates a random 3D noise effect similar to jets of water or geysers. Unity's noise module allows adjusting frequency so that low values produce soft, smooth turbulence and high values make particles change direction more rapidly.

Use cases:

Mempool turbulence visualizing fluctuating transaction backlogs.

Consensus turbulence showing network instability during forks.

Energy pressure fields around congested zones.

Guidelines:

Turbulence should modulate flows rather than replace them - overlay noise on top of vector fields to create eddies and vortices.

Vary noise frequency based on the intensity of the underlying event. High congestion -> high frequency noise; calm periods -> low frequency noise.

Use multi-octave noise sparingly; additional octaves enrich patterns but increase GPU cost.

### Fields (Vector & Scalar)

Definition: Spatial datasets that assign a value (scalar) or a direction (vector) to every point. In a vector field, particles receive a force from the vector at their location and follow it, creating currents and pathways. Scalar fields can influence particle size, opacity or emission rate based on values such as density or pressure.

Use cases:

Routing flows along network topology or geographic maps.

Density fields showing concentration of activity (e.g., heat maps).

Force fields around portals or nodes indicating attraction/repulsion.

Guidelines:

Construct vector fields from real data (e.g., network latency) or procedural patterns (e.g., curl noise) to inform motion.

Normalize vectors to prevent unrealistic acceleration.

Combine scalar fields with other types to modulate size or color based on local values.

### Halos & Auras

Definition: Clouds or rings of particles that surround objects, representing energy or influence. Halos are rendered as glowing dots or small clouds of light and are visible but do not cast light physically - they suggest power without being literal light sources. Use them to indicate active nodes, portals, or sacred artifacts.

Use cases:

Energy halos around high-throughput nodes or validators.

Portals shimmering to show they are ready for activation.

Blessed objects radiating a soft aura in narrative worlds.

Guidelines:

Keep halos subtle; they should enhance, not overpower geometry.

Animate halo intensity based on real metrics (e.g., node load).

Use additive blending and radial gradients to achieve a luminous effect.

### Swarms & Density Clouds

Definition: High-density collections of particles that buzz or swarm in place, representing ambient activity or data concentration. Swarms give the impression of life in regions where many micro events occur.

Use cases:

Ambient swarm density indicating network health in BTC World.

Node clusters with heavy micro-transactions or smart contract calls.

Biological analogs in abstract worlds (e.g., nanobots around a cell).

Guidelines:

Use randomness and small oscillations to avoid static appearance.

Tie swarm density to network metrics (e.g., active peer count).

Vary particle size or brightness within a swarm to add depth.

## Implementation Considerations

GPU first: Offload simulation to the GPU. Each particle type should have a dedicated shader or compute routine. Avoid CPU loops for more than 10k particles per system.

Noise parameters: Adjust strength, frequency and octaves to control turbulence. Higher frequency leads to faster directional changes.

Vector field resolution: Use coarse grids for large-scale flows and fine grids only when the user is near. Interpolate smoothly between grid samples to prevent jitter.

Resource reuse: Preallocate buffers and reuse particle instances to adhere to the Zero Garbage Principle.

Colour & encoding: Use color, brightness and motion to encode quantitative information (e.g., transaction size, age, fee).

## Prototyping & Tools

Rapid experimentation is essential to design compelling Life Layer effects. The interactive particle site at `particles.casberry.in` is a Life Layer Prototyping Tool. It is ideal for motion ideation, energy visualization testing and fast experimentation. It should not be treated as a replacement for the HDL rendering engine, nor dictate architecture. Insights from prototypes should be transferred into shader-based implementations in the engine.

## Rules & Best Practices

Complement, don't confuse: Particle systems should never carry canonical state. If an object has meaning, represent it with geometry (Truth Layer). Use particles only to express activity, flow or aura.

Balance complexity: Overly intricate turbulence or flow patterns can obscure meaning. Start simple and layer complexity only when it adds narrative value.

Tie to data: Where possible, drive particle behavior from real data (e.g., block times, mempool size, gas prices) to anchor visuals in truth. Procedural patterns should still follow plausible physical rules.

Ensure continuity: When combined with LOD transitions, fade particle systems gracefully so they appear and disappear without popping.

## Status

Canonical - enforced across all worlds

## Terminology Summary

| Term | Meaning | Notes |
| --- | --- | --- |
| Flow | Particle streams following vector fields, used to visualize movement or transfer | Built on vector fields and noise |
| Turbulence | Chaotic motion added via noise; low frequency for smooth movement, high for rapid changes | Use to convey pressure or instability |
| Field | Scalar or vector data defined over space; controls particle direction or attributes | Vector fields steer flows; scalar fields modulate size or color |
| Halo/Aura | Luminous cloud of particles around objects; suggests energy or influence | Visible but not a light source; subtle |
| Swarm/Density | Concentrated cluster of particles representing ambient activity | High density, small oscillations |
| Noise | Procedural function that produces random-looking values; used for turbulence | Perlin noise yields smooth transitions |
