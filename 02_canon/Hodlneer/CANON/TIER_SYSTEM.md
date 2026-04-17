# Hodlneer Badge Tier System

**Status:** Draft v1 — 2026-04-17
**Owner:** Core Canon Leadership

This document defines the canonical tier structure for the HODLNEER Badge. It is the authoritative reference for tier meaning, visual material mapping, validation criteria, evolution rules, and revocation rules.

See also: [[HODLNEER_INDEX]] | [[IDENTITY_MODEL]] | [[BADGE_VISUAL_SYSTEM]] | [[PRODUCT_PRINCIPLES]]

---

## Core Model

The tier system uses two independent layers. They must never be collapsed into one.

| Layer | Name | Purpose |
|-------|------|---------|
| Layer 1 | Canonical Meaning | What the tier represents — the internal truth about the user's history, credibility, and standing |
| Layer 2 | Visual Material | How the badge looks — the user-facing expression of that standing |

**Why two layers:** Canonical meaning is stable and principled. Visual material is expressive and designed. Keeping them separate means the visual system can evolve without changing product truth, and product truth can be updated without requiring a visual redesign.

---

## Visual Material Tiers

These are the four launch materials, ordered from entry to highest recognition.

| Material | Position | Design Character |
|----------|----------|-----------------|
| Bronze | 1 — Entry | Warm, grounded, accessible. Proof of participation. |
| Silver | 2 — Established | Refined, credible. Stronger signal. |
| Gold | 3 — Distinguished | Premium, recognizable weight. Clear standing. |
| Platinum | 4 — Recognition | Pristine, white, intentionally restrained. The rarest. |

**Design rules for all tiers:**
- Higher tiers are more refined, not louder
- No tier should dominate the badge shape or overwhelm the hex geometry
- Tiers are legible without text labels
- The badge remains the hero — material is the signal layer, not the identity layer

---

## Canonical Meaning Tiers

**Status: Names are open questions. The structure below is confirmed. Final names are pending decision.**

Each visual material maps to a canonical meaning tier. Canonical names should reflect:
- Historical depth or credibility in the crypto ecosystem
- A sense of earned standing, not purchased status
- Language that honors the ethos of HODLing and genuine participation

### Candidate name directions (not finalized)

| Material | Candidate Names | Character |
|----------|----------------|-----------|
| Bronze | Pioneer / Early / Participant | Entered, opted in, verified at base level |
| Silver | Veteran / Confirmed / Builder | Demonstrated sustained participation or stronger proof |
| Gold | Genesis / Legacy / Distinguished | Early entry or deep credibility, strongly evidenced |
| Platinum | Origin / Sovereign / Recognized | Reserved for individuals with verifiable, publicly recognized ecosystem impact |

**Decision required:** Final canonical names must be locked by Core Canon Leadership before implementation begins. See `09_feedback/open-questions.md`.

---

## Validation Criteria

**Status: Precise rules are open questions. The framework below is confirmed.**

### Validation Framework per Tier

| Material | Validation Direction |
|----------|---------------------|
| Bronze | Onboarding completion + declared entry year + at least one submitted proof signal (wallet, exchange, self-declaration) |
| Silver | Stronger proof signal required — e.g. verified exchange account history, wallet age confirmation, or equivalent evidence with meaningful confidence |
| Gold | High-confidence evidence — on-chain wallet history, early dated account records, or multi-signal corroboration showing early or sustained participation |
| Platinum | Identity verified + publicly recognized contribution to the crypto ecosystem. Not self-declared. Admin-assigned only. |

**Unresolved:** Specific thresholds (e.g. wallet age in years, minimum evidence count, confidence score cutoffs) are open questions to be defined before Epics 1–2 implementation begins.

---

## Origin / Platinum Tier (Recognition Assignment)

The Platinum tier operates differently from Bronze, Silver, and Gold. It is not earned through onboarding. It is recognized and granted.

### Assignment rules

Platinum is assigned when:
- Identity is verified
- Contribution to crypto is publicly recognized
- Impact aligns with canonical criteria (protocol builders, major advocates, ecosystem shapers, long-term influential figures)

### Admin process at launch

1. Admin seeds initial whitelist from curated sources (e.g. CoinDesk Most Influential, known protocol contributors)
2. Whitelist entries are reviewed and identity-verified before badge assignment
3. New entries are added through manual admin curation on a rolling basis

### User flagging path

Users who believe they qualify may flag themselves for consideration:
- During onboarding (opt-in step)
- Via a post-onboarding review request
- By submitting supporting evidence and references

**The flagging path is not an application.** Submitting for review does not initiate a standard process — it enters a manual queue reviewed at admin discretion. Qualification is not guaranteed and may require documentation, references, or direct verification (including human review for whales or institutions).

### Anti-gaming rule

The Platinum tier must represent pioneers, not celebrities. Fame without genuine ecosystem contribution does not qualify. Wealth without verifiable historical participation does not qualify.

> The top tier honors people who shaped this space. Not people who are simply known.

---

## Badge Evolution (Tier Upgrades)

A badge can be upgraded when a user provides stronger proof than what was originally submitted.

### Upgrade path

1. User submits new or additional evidence (e.g. evidence of older wallet holdings, historical account records previously not connected)
2. System re-evaluates badge outcome against updated evidence
3. If new evidence supports a higher tier, badge is upgraded
4. The new badge state replaces the previous state — it is not a separate badge

### Rules

- Upgrades are user-initiated
- Upgrades require actual new evidence — not re-submission of existing signals
- No tier can be self-upgraded without system validation
- Platinum upgrades require admin review regardless of submitted evidence

---

## Revocation

A badge may be revoked when:
- The badge was issued based on false, fabricated, or misrepresented evidence
- The account or identity behind the badge is found to be compromised or fraudulent
- A previously valid proof source is invalidated (e.g. exchange account history found to be manipulated)

### Revocation rules

- Revocation is an admin action — not automated
- Users must be notified before revocation is finalized (except in fraud/compromise cases where speed matters)
- Revoked badges are removed from display
- The user may re-enter onboarding if they can provide legitimate proof

### What revocation is NOT for

- Revocation is not a punishment for unpopular opinions
- Revocation is not triggered by behavior outside the proof system
- Revocation is not used to manage tier disputes

---

## Badge Permanence

Outside of revocation, a badge is permanent.

A badge is not:
- Time-limited
- Subscription-dependent
- Subject to inactivity expiry
- Tied to HDL account status

The badge represents historical truth. Historical truth does not expire.

---

## Tier Visibility

- All tier information (material + canonical meaning) is visible when the badge is displayed
- Tier must not be hidden while the badge remains public (same principle as era/verification in the Identity Model)
- Users who want full privacy should not display their badge publicly

---

## Badge Expression Format

The Hodlneer badge carries both this system and the Era × Verification identity formula simultaneously:

```
[Material Tier]
[Era] • [Verification]
```

Example:
```
Gold
Genesis • Verified
```

The material tier is the visual weight layer. Era × Verification is the identity layer. These are additive and non-redundant — each answers a different question. See `01_governance/decisions/I-1_TIER_MODEL_RECONCILIATION.md` for the full reconciliation decision.

---

## Open Questions

See `09_feedback/open-questions.md` for the active list. Key unresolved items:

- Final canonical tier names
- Precise validation thresholds per tier
- Privacy-preserving verification path for whales and institutions
- Per-tier visibility rule differences (if any)

---

## Related Documents

- [[IDENTITY_MODEL]] — the era × verification model that this tier system complements
- [[BADGE_VISUAL_SYSTEM]] — material and visual rules for each tier
- [[PRODUCT_PRINCIPLES]] — guardrails governing tier decisions (especially Principles 1, 2, 11)
- [[HODLNEER_INDEX]] — vertical entry point
- `01_governance/vision/HODLNEER_BADGE_PRD.md` — product definition this doc operationalizes
- `09_feedback/open-questions.md` — unresolved questions log
- `01_governance/decisions/I-1_TIER_MODEL_RECONCILIATION.md` — decision doc confirming these are parallel, non-competing systems
