# Epics and Execution Plan

## Purpose
This document defines the execution workstreams, epics, team boundaries, and implementation sequencing for the standalone Hodlneer product vertical. It is intended for: product management, engineering leadership, orchestration, design planning, isolated execution teams, and future staff onboarding.

This document converts the approved product vision, onboarding language, and reveal experience into parallelizable execution lanes without collapsing Hodlneer back into HDL.fun.

See also: [[HODLNEER_INDEX]] | [[IDENTITY_MODEL]] | [[REVEAL_SEQUENCE_SPEC]] | [[PRODUCT_PRINCIPLES]]

---

## Execution Philosophy

The Hodlneer product should be built using **segmented but canon-aligned teams**. Each team should be able to move independently with a clear lane and limited cross-team blockers — but all teams must stay aligned to one identity model, one premium reveal philosophy, and one product separation strategy.

---

## Team Lanes

### Lane A — Identity & Verification
Origin verification logic, era classification, verification classification, privacy-safe proof handling, badge payload generation.

### Lane B — Experience & Motion
Onboarding flow, reveal sequence, motion behavior, animation states, wallpaper composition flows.

### Lane C — Badge System & Visual Artifact
Badge visual system, card styles, dynamic badge rendering, era/verification presentation rules, export assets and display modes.

### Lane D — Product Surfaces & Sharing
Onboarding screens, badge detail screens, share flows, wallpaper flows, settings surfaces.

### Lane E — Ecosystem Integration
HDL linking, SSO or account bridge strategy, mutual prompts between Hodlneer and HDL, public display integration surfaces.

---

# EPIC 1 — Identity Model & Verification Engine

**Goal:** Build the system that determines when the user entered crypto, how strongly that entry is verified, and what public badge outcome they receive.

**Why It Exists:** This is the foundation of legitimacy. Without this, Hodlneer is just visual theater.

**Scope:** Era classification rules, verification level classification rules, evidence source hierarchy, proof confidence logic, badge outcome payload generation.

**Required Outputs:** Canonical identity model implementation, deterministic badge classification payload, support for future evidence source expansion.

**Example Stories:** Define era taxonomy in code, define verification taxonomy in code, build rules engine for evidence interpretation, create badge outcome resolver, build privacy-safe source evidence storage rules.

**Dependencies:** Identity model canon must be locked. Product team must approve final taxonomy naming.

**Must Never Become:** Manual ad hoc logic, inconsistent user classification, a user-editable trust system.

---

# EPIC 2 — Verification Input Connectors

**Goal:** Allow users to submit or connect evidence that can support Hodlneer classification.

**Why It Exists:** The system must accept different levels of proof without breaking the trust model.

**Scope:** Wallet connection, exchange connection or proof input, manual declaration path, evidence ingestion normalization, failure/fallback states.

**Required Outputs:** User-facing input flows, structured evidence ingestion, normalized evidence records, confidence pathway compatibility.

**Example Stories:** Connect wallet input flow, connect exchange/account proof flow, manual declaration flow, evidence parsing and validation service, unsupported evidence fallback handling.

**Dependencies:** Epic 1 classification model, product-approved supported evidence list.

**Must Never Become:** A loose "tell us your story" submission box, a confusing technical upload wizard, a privacy-hostile evidence trap.

---

# EPIC 3 — Onboarding Experience

**Goal:** Create the first-time user journey that introduces Hodlneer as an identity system, not a generic app.

**Why It Exists:** First impression defines whether the badge feels premium or forgettable.

**Scope:** Intro screens, privacy framing, proof framing, verification entry selection, transition into reveal sequence.

**Required Outputs:** Production onboarding flow, screen states, copy implementation, analytics touchpoints.

**Example Stories:** Build intro screen sequence, implement privacy assurance screen, build verification method selection screen, build transition state into reveal, add onboarding analytics events.

**Dependencies:** Onboarding copy canon ([[ONBOARDING_COPY_AND_REVEAL_NARRATION]]), supported evidence types from Epic 2.

**Must Never Become:** A crypto tutorial, a wallet app setup clone, an HDL.fun signup flow in disguise.

---

# EPIC 4 — Signature Reveal System

**Goal:** Build the cinematic reveal sequence that transforms verified identity into a premium emotional moment.

**Why It Exists:** This is the product's signature artifact moment and share trigger.

**Scope:** Phase-based reveal playback, dynamic badge rendering during reveal, timing and motion states, audio/haptic hooks, reduced motion alternative.

**Required Outputs:** Deterministic reveal playback system, dynamic reveal state renderer, reduced motion fallback, stable handoff into next actions.

**Example Stories:** Precompute reveal payload before animation, implement Phase 1 through Phase 5 reveal states, build dynamic era/verification text injection, add reduced motion reveal mode, add haptic/audio trigger timing hooks.

**Dependencies:** [[REVEAL_SEQUENCE_SPEC]] canon, badge payload from Epic 1, visual system from Epic 5.

**Must Never Become:** A loading spinner plus badge, a cheap game loot-box animation, a generic success confirmation page.

---

# EPIC 5 — Badge Visual System

**Goal:** Create the visual identity artifact that users actually receive, display, and associate with Hodlneer.

**Why It Exists:** If the badge feels ordinary, the whole concept loses emotional gravity.

**Scope:** Badge/card design system, era-specific visual logic, verification-specific visual logic, idle animation behavior, share-ready composition states.

**Required Outputs:** Badge design framework, dynamic render spec, display modes for reveal, detail, wallpaper, and sharing.

**Example Stories:** Define card frame system, define era styling rules, define verification styling rules, build 3D badge render model, create idle motion state rules.

**Dependencies:** Identity model labels, reveal experience design direction.

**Must Never Become:** A flat generic badge icon, text-heavy stat card clutter, an HDL-themed card that loses Hodlneer identity.

---

# EPIC 6 — Wallpaper System

**Goal:** Turn the badge into a display-worthy iOS wallpaper artifact.

**Why It Exists:** Wallpaper is one of the strongest real-world and digital distribution vectors for the product.

**Scope:** Lock screen composition, home screen composition, wallpaper export or apply flow, motion-safe wallpaper states, display optimization for iOS surfaces.

**Required Outputs:** Lock screen presentation mode, home screen presentation mode, wallpaper preview flow, safe export/apply guidance.

**Example Stories:** Create lock screen badge composition, create home screen animated composition, build wallpaper preview state, implement set/export flow, add reduced motion wallpaper mode.

**Dependencies:** Badge visual system ([[BADGE_VISUAL_SYSTEM]]), platform-specific iOS capabilities planning.

**Must Never Become:** An afterthought export screen, a static screenshot pretending to be a premium wallpaper product, overloaded with tiny unreadable details.

---

# EPIC 7 — Share & Social Export System

**Goal:** Let users share the reveal and the badge in a way that feels premium and understandable on external platforms.

**Why It Exists:** The product should spread through pride, not just links.

**Scope:** Reveal share asset generation, static image share output, short-form motion export, metadata-safe badge presentation, external platform presentation rules.

**Required Outputs:** Screenshot-friendly final state, share-ready media outputs, platform-agnostic export logic.

**Example Stories:** Generate share card image, generate short reveal clip export, build share CTA flow, build caption/default message suggestions, preserve privacy rules in exported assets.

**Dependencies:** Reveal final state, badge visual system, privacy model.

**Must Never Become:** Low-resolution share junk, confusing exports that leak hidden data, HDL-only sharing assumptions.

---

# EPIC 8 — Badge Detail & Privacy Settings

**Goal:** Allow users to inspect their Hodlneer identity and control what supporting data is or is not public.

**Why It Exists:** The product promise depends on privacy-respecting control.

**Scope:** Badge detail view, privacy settings view, public/private signal mapping, hidden data controls, explanation of what is always shown vs optionally shown.

**Required Outputs:** Settings surface, detail view, visibility control logic, user education states.

**Example Stories:** Build badge detail screen, build privacy settings panel, define always-public vs optional-public rules in UI, add preview of public badge state, add explanation tooltips or help states.

**Dependencies:** [[IDENTITY_MODEL]] canon, badge visual system, share rules from Epic 7.

**Must Never Become:** Confusing privacy jargon, settings that override credibility rules, uncontrolled exposure of sensitive wallet data.

---

# EPIC 9 — HDL Integration Bridge

**Goal:** Create a respectful but strategic bridge between Hodlneer and HDL.fun.

**Why It Exists:** The products should strengthen each other without becoming mutually dependent.

**Scope:** Optional HDL connect prompt, account linking strategy, SSO direction or future shared auth concept, badge display inside HDL, Hodlneer upsell path from HDL.

**Required Outputs:** User journey from Hodlneer to HDL, user journey from HDL to Hodlneer, explicit data-sharing boundaries.

**Example Stories:** Build post-reveal HDL prompt, design account-linking state, document badge display API/contract for HDL, define what HDL gains from linked Hodlneer identity, define what remains private.

**Dependencies:** [[HODLNEER_TO_HDL]] and [[HDL_TO_HODLNEER]] canon, badge payload contract.

**Must Never Become:** Forced HDL account creation, a dependency that blocks Hodlneer core experience, unclear data sharing between products.

---

# EPIC 10 — Analytics, Reliability, and Launch Readiness

**Goal:** Ensure the product can be measured, trusted, and launched in a disciplined way.

**Why It Exists:** A premium experience that cannot be measured or trusted is a vanity piece.

**Scope:** Onboarding analytics, reveal completion analytics, verification funnel analytics, crash/performance instrumentation, launch checklist support.

**Required Outputs:** Event taxonomy, funnel visibility, reliability instrumentation, launch readiness checklist.

**Example Stories:** Define onboarding event tracking, track verification completion outcomes, track reveal completion and branching, add performance monitoring hooks, build launch QA checklist.

**Dependencies:** Flow definitions from other epics.

**Must Never Become:** Analytics clutter without clear purpose, performance-blind animation release, launch-by-vibes.

---

## Dependency Overview

### Foundational First
1. Epic 1 — Identity Model & Verification Engine
2. Epic 2 — Verification Input Connectors
3. Epic 3 — Onboarding Experience

### Signature Core Build
4. Epic 5 — Badge Visual System
5. Epic 4 — Signature Reveal System *(Epics 4 and 5 iterate together, but ownership stays distinct)*

### Distribution and Control
6. Epic 6 — Wallpaper System
7. Epic 7 — Share & Social Export System
8. Epic 8 — Badge Detail & Privacy Settings

### Ecosystem Layer
9. Epic 9 — HDL Integration Bridge

### Operational Layer
10. Epic 10 — Analytics, Reliability, and Launch Readiness

---

## Suggested Team Assignment Model

**Team Alpha — Identity:** Epics 1, 2

**Team Beta — Experience:** Epics 3, 4

**Team Gamma — Visual Artifact:** Epics 5, 6, 7

**Team Delta — Product Controls:** Epics 8, 10

**Team Epsilon — Ecosystem:** Epic 9

These are execution lanes, not rigid org charts.

---

## Milestone Structure

**Milestone 1 — Canon Lock:** PRD approved, identity model approved, onboarding copy approved, reveal sequence spec approved.

**Milestone 2 — Proofable Prototype:** Users can submit evidence, badge outcome can be resolved, reveal payload can be generated.

**Milestone 3 — Signature Experience Prototype:** Onboarding flow works, reveal sequence works, badge visual system is recognizable, reduced motion version exists.

**Milestone 4 — Display & Distribution Prototype:** Wallpaper mode works, share export works, badge detail/settings work.

**Milestone 5 — Ecosystem Readiness:** HDL integration path is documented or functioning, analytics are in place, launch checklist is defined.

---

## Final Canonical Statement

> The Hodlneer product effort is healthy when isolated teams can move in parallel, nobody is redefining identity logic ad hoc, nobody is collapsing Hodlneer into HDL, and the reveal, wallpaper, and share flows are treated as first-class.

---

## Related Documents

- [[IDENTITY_MODEL]] — canon for Epic 1 implementation
- [[REVEAL_SEQUENCE_SPEC]] — spec for Epic 4
- [[BADGE_VISUAL_SYSTEM]] — spec for Epic 5
- [[WALLPAPER_SYSTEM]] — spec for Epic 6
- [[ONBOARDING_COPY_AND_REVEAL_NARRATION]] — copy for Epics 3 and 4
- [[HODLNEER_TO_HDL]] — integration direction for Epic 9
- [[HDL_TO_HODLNEER]] — reverse integration direction for Epic 9
- [[PRODUCT_PRINCIPLES]] — guardrails all teams must reference
- [[ASSET_PRODUCTION_CHECKLIST]] — launch readiness tracking
