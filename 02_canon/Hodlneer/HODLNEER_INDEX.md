# Hodlneer — Vertical Index

Hodlneer is a standalone iOS identity product that verifies a user's crypto origin and turns it into a premium badge experience. It is a distinct product vertical within the HDL ecosystem — not a feature of HDL.fun.

**One-line definition:** Hodlneer is the iOS app for proving your crypto origin and turning it into a badge worth carrying.

**Core identity formula:** Badge = Era × Verification

---

## Folder Structure

```
02_canon/Hodlneer/
├── HODLNEER_INDEX.md         ← this file
├── CANON/
│   ├── CANON_INDEX.md        ← canon-specific index
│   ├── IDENTITY_MODEL.md     ← foundational: era + verification taxonomy
│   ├── BADGE_VISUAL_SYSTEM.md
│   ├── BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md
│   ├── PRODUCT_PRINCIPLES.md
│   ├── WALLPAPER_SYSTEM.md
│   ├── LAUNCH_STRATEGY.md
│   ├── ICON_SYSTEM.md
│   └── ASSET_PRODUCTION_CHECKLIST.md
├── COPY/
│   ├── MANIFESTO.md
│   ├── LANDING_PAGE.md
│   ├── ONBOARDING_COPY_AND_REVEAL_NARRATION.md
│   ├── APP_STORE_PAGE.md
│   ├── SCREENSHOT_STORYBOARD.md
│   ├── LAUNCH_ANNOUNCEMENT.md
│   └── FAQ.md
├── EXPERIENCE/
│   └── REVEAL_SEQUENCE_SPEC.md
├── EXECUTION/
│   └── EPICS.md
└── INTEGRATION/
    ├── HODLNEER_TO_HDL.md
    └── HDL_TO_HODLNEER.md
```

---

## CANON — Source of Truth

| Document | What it defines |
|----------|----------------|
| [[CANON/CANON_INDEX]] | Canon-specific navigation and hierarchy |
| [[CANON/IDENTITY_MODEL]] | Era taxonomy, verification taxonomy, public/private identity rules, badge output format |
| [[CANON/BADGE_VISUAL_SYSTEM]] | Badge silhouette, geometry, layering, materials, era × verification visual logic |
| [[CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM]] | Visual bridge between individual badge (hex cell) and collective Bitcoin sphere |
| [[CANON/PRODUCT_PRINCIPLES]] | 15 operational guardrails for cross-team decisions |
| [[CANON/WALLPAPER_SYSTEM]] | Wallpaper as first-class product: modes, motion rules, privacy, composition |
| [[CANON/LAUNCH_STRATEGY]] | Standalone launch positioning, phasing, message hierarchy, channel strategy |
| [[CANON/ICON_SYSTEM]] | App icon, product mark, supporting glyph system |
| [[CANON/ASSET_PRODUCTION_CHECKLIST]] | Tier 1/2/3 launch asset requirements, launch readiness checklist |

---

## COPY — User-Facing Language

| Document | What it defines |
|----------|----------------|
| [[COPY/MANIFESTO]] | Why Hodlneer exists — the philosophical and cultural core |
| [[COPY/LANDING_PAGE]] | Full landing page copy, messaging hierarchy, section-by-section |
| [[COPY/ONBOARDING_COPY_AND_REVEAL_NARRATION]] | Screen-by-screen onboarding + phase-by-phase reveal narration |
| [[COPY/APP_STORE_PAGE]] | App name, description, feature bullets, screenshot direction, ASO |
| [[COPY/SCREENSHOT_STORYBOARD]] | 6-frame visual conversion sequence for App Store and launch |
| [[COPY/LAUNCH_ANNOUNCEMENT]] | Primary launch copy, short post versions, thread, founder statement, email |
| [[COPY/FAQ]] | 30 canonical Q&A answers for support, marketing, and launch |

---

## EXPERIENCE — Interaction Design

| Document | What it defines |
|----------|----------------|
| [[EXPERIENCE/REVEAL_SEQUENCE_SPEC]] | Frame-by-frame 5-phase reveal spec: timing, motion, copy, dynamic logic, post-reveal branching |

---

## EXECUTION — Implementation Planning

| Document | What it defines |
|----------|----------------|
| [[EXECUTION/EPICS]] | 10 epics across 5 team lanes: identity, experience, visual artifact, product controls, ecosystem |

---

## INTEGRATION — Cross-Product Bridges

| Document | What it defines |
|----------|----------------|
| [[INTEGRATION/HODLNEER_TO_HDL]] | How Hodlneer users are invited into HDL.fun; data boundaries; UX rules |
| [[INTEGRATION/HDL_TO_HODLNEER]] | How HDL.fun users are invited to verify with Hodlneer; upgrade path; prompt timing |

---

## Core Invariants (Never Override)

- **Standalone First:** Hodlneer must deliver complete value before any HDL prompt
- **Era ≠ Verification:** The two axes must never be collapsed into one tier system
- **Badge = Hero, Card = Stage:** The badge is the identity object; the card is the presentation surface
- **Privacy by Default:** Badge result may be public; raw proof stays private unless user consents
- **Hexagon = Identity Cell:** The hex geometry is conceptual, not decorative — it connects badge to the Bitcoin sphere world

---

## Missing Documents (Needs Creation)

- `CANON/HODLNEER_PRD.md` — formal product requirements document (referenced throughout; not yet written). Should define: standalone iOS app, Hodlneer 3D Badge as core feature, cinematic reveal as signature moment, wallpaper as primary distribution vector, privacy-first identity controls, optional HDL integration.

---

## Relationships to Broader Vault

This vertical lives within `02_canon/` following the vault's canon hierarchy. The Hodlneer canon is authoritative for its product domain. Implementation work happens in the product repos. Bridges into implementation are tracked in `08_bridges/`.

For vault-wide context: [[02_canon/CANON_INDEX|Vault Canon Index]] | `CLAUDE.md` | `SYSTEM_OVERVIEW.md`
