# HDL Product Alignment Gaps

## Purpose

This document tracks the discrepancies between the HDL canon (as defined in the `hdl-world-engine` repo) and the current product implementation (frontend and backend). It acts as a living checklist of missing features, misalignments and priorities.

## Critical Gaps

### 1. Handle as Primary Identity

Status: `Not fully enforced`

Issues:

- Some areas of the product still rely on usernames or internal IDs instead of handles.
- Routing and lookup logic is not consistently handle-based across modules.

Required:

- Make handle the universal identifier across all APIs and UI components.
- Remove dependencies on internal numeric IDs in user-facing contexts.

### 2. Routing Engine

Status: `Not implemented`

Missing:

- Ability to send assets using `@handle` instead of wallet addresses.
- Chain resolution logic to select the correct wallet binding by default.

Impact:

- Core HDL value proposition (handle-based sending) is absent.

### 3. Proof / Badge System (Hodlneer)

Status: `Missing`

Missing:

- Definitions and issuance rules for badge types (claimed, social, on-chain, OG).
- Proof validation logic and persistence.
- User interface to display badges in profiles and feeds.

Impact:

- No identity differentiation.
- No social credibility layer or incentive for early adoption.

### 4. Wallet Abstraction

Status: `Partial`

Issues:

- The product still exposes wallet concepts directly to users in some flows.
- Wallet selection and management are not fully hidden behind the handle abstraction.

Required:

- Adopt handle-first user flows where the wallet is an invisible implementation detail.
- Consolidate multi-chain wallet management behind the routing engine.

### 5. Feed Identity Layer

Status: `Partial`

Issues:

- Posts and comments display the author's name but lack badge context.
- Identity signals (proof badges) are not surfaced in the feed.

Required:

- Display proof badges or status indicators next to handles in the feed.
- Emphasize handle prominence over other identifiers.

### 6. World Integration (3D / VR)

Status: `Not started`

Missing:

- Entry points from the product into the 3D world engine.
- Visual systems for identity and environment (e.g. handle badges floating above avatars).
- Three.js/VR integration in the frontend.

Impact:

- The product lacks the immersive, world-based differentiator envisioned by the canon.

## Secondary Gaps

### Messaging System

- Messaging is handle-based but not yet wallet-aware.
- There is no capability to transfer assets within chat.

### Profile System

- Profiles lack emphasis on proof badges and identity depth.
- There is no clear story about the user's history or contributions.

## Aligned Areas

- A basic social feed exists and functions.
- Authentication flows are operational.
- Preliminary wallet integration groundwork is in place.

## Priority Order

- Proof System (Hodlneer) - unlocks identity differentiation and gamification.
- Handle Enforcement - ensures a consistent identity model across the product.
- Routing Engine - delivers the core handle-based sending feature.
- Wallet Abstraction - removes cognitive load by hiding chains and addresses.
- Feed Identity Upgrade - surfaces handles and badges in all social interactions.
- World Layer - integrates VR/3D identity contexts once the foundations are solid.

## Final Truth

If HDL does not:

- make identity visible (via handles and badges),
- make wallets invisible (abstracted behind handles), and
- make proof meaningful (badges as status and story),

then the product will feel like just another social app. The gaps above must be resolved to realize the vision.
