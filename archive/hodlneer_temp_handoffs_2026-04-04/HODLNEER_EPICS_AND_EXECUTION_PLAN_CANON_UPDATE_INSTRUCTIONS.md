# HODLNEER_EPICS_AND_EXECUTION_PLAN_CANON_UPDATE_INSTRUCTIONS.md

## Purpose
This document defines the **execution workstreams, epics, team boundaries, and implementation sequencing** for the standalone **Hodlneer** product vertical.

It is intended for:
- product management
- engineering leadership
- Claude task orchestration
- design planning
- isolated execution teams
- future staff onboarding

This document converts the approved product vision, onboarding language, and reveal experience into **parallelizable execution lanes** without collapsing Hodlneer back into HDL.fun.

---

## Placement Instructions for Claude

Place this file in the Obsidian vault at:

`/Hodlneer/EXECUTION/EPICS.md`

If this document is temporarily staged at the root of the HDL universe folder, Claude should move it into the path above once the Hodlneer folder structure is created.

This file belongs in the `EXECUTION` directory because it defines:
- implementation lanes
- epic ownership
- sequencing
- dependency mapping
- isolated team boundaries
- canon-safe delivery expectations

---

## Canon Update Rules

Claude should treat this file as the canonical source for Hodlneer execution planning.

When this file is placed, Claude should review and align:
- `/Hodlneer/CANON/HODLNEER_PRD.md`
- `/Hodlneer/CANON/IDENTITY_MODEL.md`
- `/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`
- `/Hodlneer/COPY/ONBOARDING_COPY_AND_REVEAL_NARRATION.md`
- `/Hodlneer/INTEGRATION/HODLNEER_TO_HDL.md`
- `/Hodlneer/INTEGRATION/HDL_TO_HODLNEER.md`

If older docs or prior task lists describe Hodlneer work as:
- a subset of HDL.fun onboarding
- just another badge feature inside HDL
- a social feed feature
- a generic wallet add-on

Those docs should be revised. The latest canon is:
- **Hodlneer is its own product vertical**
- **HDL.fun is a separate but complementary product**
- **The two products should integrate well, but must be planned independently**

---

## Execution Philosophy

The Hodlneer product should be built using **segmented but canon-aligned teams**.

Each team should be able to move independently with:
- a clear lane
- limited cross-team blockers
- well-defined interfaces

But all teams must stay aligned to:
- one identity model
- one premium reveal philosophy
- one product separation strategy

This is not an excuse for disconnected output. It is a way to create speed without chaos.

---

## Team Lanes

The product should be divided into the following execution lanes:

### Lane A — Identity & Verification
Responsible for:
- origin verification logic
- era classification
- verification classification
- privacy-safe proof handling
- badge payload generation

### Lane B — Experience & Motion
Responsible for:
- onboarding flow
- reveal sequence
- motion behavior
- animation states
- wallpaper composition flows

### Lane C — Badge System & Visual Artifact
Responsible for:
- badge visual system
- card styles
- dynamic badge rendering
- era/verification presentation rules
- export assets and display modes

### Lane D — Product Surfaces & Sharing
Responsible for:
- onboarding screens
- badge detail screens
- share flows
- wallpaper flows
- settings surfaces

### Lane E — Ecosystem Integration
Responsible for:
- HDL linking
- SSO or account bridge strategy
- mutual prompts between Hodlneer and HDL
- public display integration surfaces

Each lane can be assigned to separate staff or isolated teams, but all lanes must consume the same canon.

---

## Epic Map

---

# EPIC 1 — Identity Model & Verification Engine

## Goal
Build the system that determines:
- when the user entered crypto
- how strongly that entry is verified
- what public badge outcome they receive

## Why It Exists
This is the foundation of legitimacy. Without this, Hodlneer is just visual theater.

## Scope
- Era classification rules
- Verification level classification rules
- Evidence source hierarchy
- Proof confidence logic
- Badge outcome payload generation

## Required Outputs
- canonical identity model implementation
- deterministic badge classification payload
- support for future evidence source expansion

## Example Stories
- Define era taxonomy in code
- Define verification taxonomy in code
- Build rules engine for evidence interpretation
- Create badge outcome resolver
- Build privacy-safe source evidence storage rules

## Dependencies
- Identity model canon must be locked
- Product team must approve final taxonomy naming

## Must Never Become
- manual ad hoc logic
- inconsistent user classification
- a user-editable trust system

---

# EPIC 2 — Verification Input Connectors

## Goal
Allow users to submit or connect evidence that can support Hodlneer classification.

## Why It Exists
The system must accept different levels of proof without breaking the trust model.

## Scope
- Wallet connection
- Exchange connection or proof input
- Manual declaration path
- Evidence ingestion normalization
- Failure/fallback states

## Required Outputs
- user-facing input flows
- structured evidence ingestion
- normalized evidence records
- confidence pathway compatibility

## Example Stories
- Connect wallet input flow
- Connect exchange/account proof flow
- Manual declaration flow
- Evidence parsing and validation service
- Unsupported evidence fallback handling

## Dependencies
- Epic 1 classification model
- product-approved supported evidence list

## Must Never Become
- a loose “tell us your story” submission box
- a confusing technical upload wizard
- a privacy-hostile evidence trap

---

# EPIC 3 — Onboarding Experience

## Goal
Create the first-time user journey that introduces Hodlneer as an identity system, not a generic app.

## Why It Exists
First impression defines whether the badge feels premium or forgettable.

## Scope
- intro screens
- privacy framing
- proof framing
- verification entry selection
- transition into reveal sequence

## Required Outputs
- production onboarding flow
- screen states
- copy implementation
- analytics touchpoints

## Example Stories
- Build intro screen sequence
- Implement privacy assurance screen
- Build verification method selection screen
- Build transition state into reveal
- Add onboarding analytics events

## Dependencies
- onboarding copy canon
- supported evidence types from Epic 2

## Must Never Become
- a crypto tutorial
- a wallet app setup clone
- an HDL.fun signup flow in disguise

---

# EPIC 4 — Signature Reveal System

## Goal
Build the cinematic reveal sequence that transforms verified identity into a premium emotional moment.

## Why It Exists
This is the product’s signature artifact moment and share trigger.

## Scope
- phase-based reveal playback
- dynamic badge rendering during reveal
- timing and motion states
- audio/haptic hooks
- reduced motion alternative

## Required Outputs
- deterministic reveal playback system
- dynamic reveal state renderer
- reduced motion fallback
- stable handoff into next actions

## Example Stories
- Precompute reveal payload before animation
- Implement Phase 1 through Phase 5 reveal states
- Build dynamic era/verification text injection
- Add reduced motion reveal mode
- Add haptic/audio trigger timing hooks

## Dependencies
- reveal sequence canon
- badge payload from Epic 1
- visual system from Epic 5

## Must Never Become
- a loading spinner plus badge
- a cheap game loot-box animation
- a generic success confirmation page

---

# EPIC 5 — Badge Visual System

## Goal
Create the visual identity artifact that users actually receive, display, and associate with Hodlneer.

## Why It Exists
If the badge feels ordinary, the whole concept loses emotional gravity.

## Scope
- badge/card design system
- era-specific visual logic
- verification-specific visual logic
- idle animation behavior
- share-ready composition states

## Required Outputs
- badge design framework
- dynamic render spec
- display modes for reveal, detail, wallpaper, and sharing

## Example Stories
- Define card frame system
- Define era styling rules
- Define verification styling rules
- Build 3D badge render model
- Create idle motion state rules

## Dependencies
- identity model labels
- reveal experience design direction

## Must Never Become
- a flat generic badge icon
- text-heavy stat card clutter
- an HDL-themed card that loses Hodlneer identity

---

# EPIC 6 — Wallpaper System

## Goal
Turn the badge into a display-worthy iOS wallpaper artifact.

## Why It Exists
Wallpaper is one of the strongest real-world and digital distribution vectors for the product.

## Scope
- lock screen composition
- home screen composition
- wallpaper export or apply flow
- motion-safe wallpaper states
- display optimization for iOS surfaces

## Required Outputs
- lock screen presentation mode
- home screen presentation mode
- wallpaper preview flow
- safe export/apply guidance

## Example Stories
- Create lock screen badge composition
- Create home screen animated composition
- Build wallpaper preview state
- Implement set/export flow
- Add reduced motion wallpaper mode

## Dependencies
- badge visual system
- platform-specific iOS capabilities planning

## Must Never Become
- an afterthought export screen
- a static screenshot pretending to be a premium wallpaper product
- overloaded with tiny unreadable details

---

# EPIC 7 — Share & Social Export System

## Goal
Let users share the reveal and the badge in a way that feels premium and understandable on external platforms.

## Why It Exists
The product should spread through pride, not just links.

## Scope
- reveal share asset generation
- static image share output
- short-form motion export
- metadata-safe badge presentation
- external platform presentation rules

## Required Outputs
- screenshot-friendly final state
- share-ready media outputs
- platform-agnostic export logic

## Example Stories
- Generate share card image
- Generate short reveal clip export
- Build share CTA flow
- Build caption/default message suggestions
- Preserve privacy rules in exported assets

## Dependencies
- reveal final state
- badge visual system
- privacy model

## Must Never Become
- low-resolution share junk
- confusing exports that leak hidden data
- HDL-only sharing assumptions

---

# EPIC 8 — Badge Detail & Privacy Settings

## Goal
Allow users to inspect their Hodlneer identity and control what supporting data is or is not public.

## Why It Exists
The product promise depends on privacy-respecting control.

## Scope
- badge detail view
- privacy settings view
- public/private signal mapping
- hidden data controls
- explanation of what is always shown vs optionally shown

## Required Outputs
- settings surface
- detail view
- visibility control logic
- user education states

## Example Stories
- Build badge detail screen
- Build privacy settings panel
- Define always-public vs optional-public rules in UI
- Add preview of public badge state
- Add explanation tooltips or help states

## Dependencies
- identity model canon
- badge visual system
- share rules from Epic 7

## Must Never Become
- confusing privacy jargon
- settings that override credibility rules
- uncontrolled exposure of sensitive wallet data

---

# EPIC 9 — HDL Integration Bridge

## Goal
Create a respectful but strategic bridge between Hodlneer and HDL.fun.

## Why It Exists
The products should strengthen each other without becoming mutually dependent.

## Scope
- optional HDL connect prompt
- account linking strategy
- SSO direction or future shared auth concept
- badge display inside HDL
- Hodlneer upsell path from HDL

## Required Outputs
- user journey from Hodlneer to HDL
- user journey from HDL to Hodlneer
- explicit data-sharing boundaries

## Example Stories
- Build post-reveal HDL prompt
- Design account-linking state
- Document badge display API/contract for HDL
- Define what HDL gains from linked Hodlneer identity
- Define what remains private

## Dependencies
- integration canon
- badge payload contract

## Must Never Become
- forced HDL account creation
- a dependency that blocks Hodlneer core experience
- unclear data sharing between products

---

# EPIC 10 — Analytics, Reliability, and Launch Readiness

## Goal
Ensure the product can be measured, trusted, and launched in a disciplined way.

## Why It Exists
A premium experience that cannot be measured or trusted is a vanity piece.

## Scope
- onboarding analytics
- reveal completion analytics
- verification funnel analytics
- crash/performance instrumentation
- launch checklist support

## Required Outputs
- event taxonomy
- funnel visibility
- reliability instrumentation
- launch readiness checklist

## Example Stories
- Define onboarding event tracking
- Track verification completion outcomes
- Track reveal completion and branching
- Add performance monitoring hooks
- Build launch QA checklist

## Dependencies
- flow definitions from other epics

## Must Never Become
- analytics clutter without clear purpose
- performance-blind animation release
- launch-by-vibes

---

## Dependency Overview

### Foundational First
1. Epic 1 — Identity Model & Verification Engine
2. Epic 2 — Verification Input Connectors
3. Epic 3 — Onboarding Experience

### Signature Core Build
4. Epic 5 — Badge Visual System
5. Epic 4 — Signature Reveal System

### Distribution and Control
6. Epic 6 — Wallpaper System
7. Epic 7 — Share & Social Export System
8. Epic 8 — Badge Detail & Privacy Settings

### Ecosystem Layer
9. Epic 9 — HDL Integration Bridge

### Operational Layer
10. Epic 10 — Analytics, Reliability, and Launch Readiness

Note: Epic 4 and Epic 5 will likely iterate together, but their ownership should remain logically distinct.

---

## Suggested Team Assignment Model

### Team Alpha — Identity
Owns:
- Epic 1
- Epic 2

### Team Beta — Experience
Owns:
- Epic 3
- Epic 4

### Team Gamma — Visual Artifact
Owns:
- Epic 5
- Epic 6
- Epic 7

### Team Delta — Product Controls
Owns:
- Epic 8
- Epic 10

### Team Epsilon — Ecosystem
Owns:
- Epic 9

These are execution lanes, not rigid org charts.

---

## Milestone Structure

### Milestone 1 — Canon Lock
Done when:
- PRD is approved
- identity model is approved
- onboarding copy is approved
- reveal sequence spec is approved

### Milestone 2 — Proofable Prototype
Done when:
- users can submit evidence
- badge outcome can be resolved
- reveal payload can be generated

### Milestone 3 — Signature Experience Prototype
Done when:
- onboarding flow works
- reveal sequence works
- badge visual system is recognizable
- reduced motion version exists

### Milestone 4 — Display & Distribution Prototype
Done when:
- wallpaper mode works
- share export works
- badge detail/settings work

### Milestone 5 — Ecosystem Readiness
Done when:
- HDL integration path is documented or functioning
- analytics are in place
- launch checklist is defined

---

## What Good Looks Like

The Hodlneer product effort is healthy when:
- isolated teams can move in parallel
- nobody is redefining identity logic ad hoc
- nobody is collapsing Hodlneer into HDL
- the reveal remains premium
- wallpaper and share flows are treated as first-class, not extras
- privacy rules remain intact across all surfaces

---

## What Must Never Happen

The execution plan must never degrade into:
- a generic backlog dump
- HDL-first thinking that demotes Hodlneer
- motion design disconnected from product logic
- verification logic disconnected from UX
- team silos that produce conflicting realities
- old conversations continuing to define current canon

---

## Notes for Claude

When integrating this file:
- Preserve the independent Hodlneer product framing
- Do not merge these epics into HDL.fun roadmap documents without a very explicit integration section
- Use this document to refactor older or duplicate task lists
- If older backlog items conflict with this new structure, archive or rewrite them
- All future implementation prompts for staff should reference this document plus the PRD and reveal spec

---

## Required Related Docs to Update

After placing this file, Claude should review and update:

### `/Hodlneer/COPY/LANDING_PAGE.md`
Ensure the landing page aligns with the execution intent of:
- premium reveal
- wallpaper distribution
- privacy-first identity
- optional HDL bridge

### `/Hodlneer/COPY/MANIFESTO.md`
Ensure the manifesto reflects:
- identity as proof
- the cultural meaning of the badge
- pride without forced exposure

### `/Hodlneer/INTEGRATION/HODLNEER_TO_HDL.md`
Ensure it clearly describes the post-reveal bridge into HDL

### `/Hodlneer/INTEGRATION/HDL_TO_HODLNEER.md`
Ensure it clearly describes the HDL-to-Hodlneer upgrade path

---

## Next Recommended Documents

After this file is placed and canon is reconciled, the next best documents to produce are:

1. `/Hodlneer/COPY/LANDING_PAGE.md`
2. `/Hodlneer/COPY/MANIFESTO.md`

These two docs will define how the product is presented to the world and how the team speaks about why it exists.
