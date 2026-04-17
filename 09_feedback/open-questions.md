# Open Questions Log

This document tracks unresolved product, canon, and design questions across the HDL / Hodlneer ecosystem. Each question should include its source, the decision it blocks, and who needs to resolve it.

Questions are removed or marked resolved when Core Canon Leadership makes a decision. Resolved decisions belong in the relevant canon doc — not here.

---

## Hodlneer Badge — Tier System

**Source:** Intake 2026-04-17 | **Blocks:** `TIER_SYSTEM.md` finalization, Epic 1 implementation

| # | Question | Blocks | Owner |
|---|----------|--------|-------|
| T-1 | What are the final canonical tier names? Candidates: Genesis, Pioneer, Veteran, Legacy, Sovereign, Apex, Origin. Names must honor pioneers without feeling elitist or gamified. | `TIER_SYSTEM.md`, badge copy, visual system | Core Canon Leadership |
| T-2 | What are the precise validation thresholds per tier at launch? (e.g. wallet age in years, minimum evidence signals, confidence score cutoffs) | Epic 1 verification engine, Epics 1–2 | Core Canon Leadership + Verification Systems Lead |
| T-3 | How will whales and institutions verify privately? Standard proof flows may expose financial scale. Alternative: admin video call, third-party attestation, redacted evidence review. | Platinum flagging path, privacy model | Core Canon Leadership |
| T-4 | Can users hide their badge on their profile? If yes, under what conditions? Does hiding the badge hide the tier or just the artifact? | Visibility rules, `BADGE_VISUAL_SYSTEM.md` | Core Canon Leadership |
| T-5 | Should badges appear automatically in feed or comments, or only on profile? | Visibility rules, share system | Product / Core Canon Leadership |
| T-6 | Are there per-tier visibility differences? (e.g. Platinum is always visible, Bronze can be hidden?) | Visibility rules | Core Canon Leadership |
| T-7 | What minimal launch privileges, if any, should badge holders receive beyond visibility? (early access, exclusive content, etc.) | Epic 9 integration, future behavior spec | Core Canon Leadership |
| T-8 | What are the evolution rules for tier upgrades? Specifically: how is "new evidence" defined vs. re-submission of old evidence? | Badge evolution flow, Epic 1 | Verification Systems Lead |

---

## Hodlneer Badge — Naming and Identity

**Source:** Intake 2026-04-17 | **Blocks:** Copy finalization, onboarding copy

| # | Question | Blocks | Owner |
|---|----------|--------|-------|
| N-1 | How does the dual-tier system (canonical meaning tier + visual material tier) surface to users? Do users see both names, or only the material? | Onboarding copy, badge detail screen, `APP_STORE_PAGE.md` | Core Canon Leadership |
| N-2 | Is the canonical tier name ever user-facing, or is it internal truth only? | Badge display, copy canon | Core Canon Leadership |

---

## Hodlneer Badge — Share System

**Source:** Intake 2026-04-17 | **Blocks:** Share UX spec, Epic 7

| # | Question | Blocks | Owner |
|---|----------|--------|-------|
| S-1 | What is the final share UX design? Specifically: what does the shareable asset look like, what copy surrounds it, and what share targets are prioritized at launch? | Epic 7, `SCREENSHOT_STORYBOARD.md` | Launch Coordinator + Core Canon Leadership |

---

## Hodlneer — Identity Model Alignment

**Source:** Migration report 2026-04-04

| # | Question | Blocks | Owner |
|---|----------|--------|-------|
| ~~I-1~~ | ~~How does the material tier system relate to the era × verification formula?~~ | **RESOLVED 2026-04-17** — See `01_governance/decisions/I-1_TIER_MODEL_RECONCILIATION.md`. These are parallel, non-competing systems. Era × Verification = primary public identity. Material Tier = badge visual weight. Both appear on the badge simultaneously. The specific tier mapping for Bronze/Silver/Gold given an Era × Verification combination is a T-2 decision (still open). Platinum is independent of the Era × Verification track entirely. | — |
| I-2 | "Declared" verification has no integrity mechanism. A user can self-declare any era with no validation. What prevents abuse? | Trust model, Verification Systems Lead design | Core Canon Leadership + Verification Systems Lead |

---

## How to Use This Log

- **To add a question:** Add a row under the relevant section. Include source, what it blocks, and the responsible owner.
- **To resolve a question:** Remove the row. Write the decision into the relevant canon doc. Note the decision date in that doc.
- **Do not resolve questions here.** This is a tracking log, not a decision doc.
