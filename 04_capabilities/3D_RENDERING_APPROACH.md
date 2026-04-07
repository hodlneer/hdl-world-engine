# 3D Rendering and World-Building Approach

## Purpose

This document captures the strategic and technical approach to 3D world-building across the HDL ecosystem. It exists so that agents and contributors working on 3D features — the Hodlneer reveal sequence, the badge system, the Bitcoin sphere visualization, and future HDL worlds — understand the implementation philosophy before beginning work.

**The core principle: do not build from scratch what already exists as a mature, production-grade tool.**

---

## Rendering Stack

The HDL ecosystem uses a layered 3D stack. Understanding which layer a task lives in determines which tools to use.

| Layer | Purpose | Primary Tools |
|-------|---------|---------------|
| Asset generation | Creating 3D geometry, textures, meshes | SAM3D (Meta), Blender, GLB/GLTF exports |
| Scene rendering | Displaying and animating 3D content on screen | Three.js, React Three Fiber (R3F) |
| Interaction and physics | Camera, controls, colliders, springs | @react-three/drei, @react-three/rapier |
| Shader/material layer | Custom visual effects, badges, particle systems | GLSL via Three.js ShaderMaterial, R3F |
| Platform delivery | AR/VR targets, web, mobile WebGL | WebXR, iOS SceneKit/RealityKit for native |

---

## Key Tools

### Three.js + React Three Fiber (R3F)

The primary rendering layer for HDL web experiences. Three.js is the underlying 3D engine; React Three Fiber is the React declarative wrapper that makes Three.js composable with the existing React product stack.

Use R3F for:
- The Bitcoin sphere / hex network visualization
- The Hodlneer badge 3D render and reveal sequence
- Any Three.js scene that needs to integrate with the React component tree

R3F is production-ready, well-documented, and has a large ecosystem. Do not write raw Three.js scene management code when R3F provides the same abstraction with less boilerplate.

Relevant libraries from the R3F ecosystem:
- `@react-three/drei` — camera controls, loaders, environment maps, billboards, instances
- `@react-three/rapier` — physics engine (for future interactive worlds)
- `@react-three/postprocessing` — bloom, depth of field, glow effects (relevant for badge glow / reveal)

### SAM3D (Meta)

SAM3D is Meta's AI model for generating high-quality 3D assets from single 2D photographs. It is the asset generation layer upstream of Three.js.

- Input: single RGB image (no LiDAR, no depth sensor required)
- Output: textured `.GLB` / `.OBJ` mesh, or Gaussian splat file
- License: Apache 2.0 — commercial use permitted
- API pricing: ~$0.02/model, ~$0.06/composed scene
- Inference time: 4–24 seconds per scene
- Integrates directly with Three.js / R3F via standard GLB loading

Use SAM3D when:
- A 3D asset needs to be created from reference photography
- Manual modeling would be a bottleneck
- Asset fidelity needs to be production-grade without a 3D artist

Do not use SAM3D when:
- The asset is fully geometric and can be procedurally generated (hex shapes, badge geometry)
- The asset already exists as a properly formatted GLB

The Hodlneer badge geometry (hexagonal, procedural) does not need SAM3D — it can be generated programmatically in Three.js/R3F using standard geometry primitives and custom shaders.

### Gaussian Splatting

SAM3D can output Gaussian splat format in addition to polygon meshes. Gaussian splatting is a neural representation that can produce photorealistic scene captures efficiently. If the HDL world ever needs hyper-realistic ambient environments (not just geometric worlds), Gaussian splats are worth evaluating — R3F has splat rendering support via `@react-three/drei`.

---

## Hodlneer 3D Badge — Implementation Approach

The Hodlneer badge is fully geometric (hexagonal facets, metallic materials, procedural layering). It does not require SAM3D. The implementation approach is:

1. **Geometry** — procedurally generated hex shape in R3F using `ExtrudeGeometry` or `Shape`
2. **Materials** — `MeshPhysicalMaterial` for metal/reflective finish, IBL environment maps for lighting
3. **Reveal animation** — managed via `@react-spring/three` or Framer Motion 3D; frame-by-frame timing spec lives in `EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`
4. **Particle systems** — Three.js `Points` or `InstancedMesh` for energy/particle effects during reveal phases
5. **Export for wallpaper** — rendered canvas captured as PNG/JPEG for iOS wallpaper generation

See `CANON/BADGE_VISUAL_SYSTEM.md` for the visual canon (geometry, layers, materials, era rules) that the Three.js implementation must conform to.

---

## Bitcoin Sphere Visualization — Implementation Approach

The Bitcoin hex sphere (from `CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md`) is procedurally generated network geometry. The approach is:

1. **Sphere construction** — hex cells mapped to icosphere or geodesic sphere using Three.js `IcosahedronGeometry` with face subdivisions; each hex cell is an `InstancedMesh` for performance
2. **Data binding** — real Bitcoin network data (transactions, blocks, mempool) drives cell motion, glow intensity, and color via shader uniforms (see `02_canon/btc_world/DATA_BINDING.md`)
3. **Particle systems** — inter-cell energy flows rendered as `Points` with custom vertex shaders
4. **LOD** — near cells show full detail hex geometry; far cells degrade to billboard sprites per `02_canon/shared/LOD_STRATEGY.md`

Do not attempt to model the Bitcoin sphere as individual discrete objects in a scene graph — the performance ceiling is too low. Use `InstancedMesh` from the start.

---

## Agent Instructions

When working on any task involving 3D visuals, rendering, or world-building in the HDL ecosystem:

1. **Read the canon spec first** — the visual canon defines what must be built. The rendering approach defines how to build it efficiently.
2. **Do not invent a rendering architecture** — the R3F + Three.js stack is the decided approach. Work within it.
3. **Leverage the ecosystem** — `@react-three/drei`, postprocessing, spring animation, and instanced rendering cover the vast majority of needs. Check the drei docs before writing custom solutions.
4. **Asset generation via SAM3D** — if a task requires a 3D asset from photography or reference imagery, evaluate SAM3D before budgeting for 3D artist time.
5. **Performance first on hex geometry** — always use `InstancedMesh` for repeated hex cells; never create one `Mesh` per cell.
6. **Canon does not change to match rendering constraints** — if the badge visual system says a material must be metallic and reflective, the implementation must achieve that. If a constraint is truly impossible within WebGL, it must be escalated to governance — not silently dropped.

---

## Related Documents

- `02_canon/Hodlneer/CANON/BADGE_VISUAL_SYSTEM.md` — visual canon for the badge
- `02_canon/Hodlneer/CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md` — visual bridge between badge and Bitcoin sphere
- `02_canon/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md` — frame-by-frame reveal spec
- `02_canon/btc_world/BTC_HEX_NETWORK_SPEC.md` — hex sphere specification
- `02_canon/shared/LOD_STRATEGY.md` — LOD rules for all worlds
- `02_canon/shared/PARTICLE_SYSTEMS.md` — particle behavior canon
- `02_canon/shared/RENDERING_STRATEGY.md` — layered rendering model
