# Hodlneer Identity Model

## Purpose
This is the source of truth for the Hodlneer identity classification system. It defines:
- era naming and boundaries
- verification naming and strength levels
- badge output logic
- public vs private identity rules
- how identity is expressed across Hodlneer, HDL.fun, and future 3D/VR surfaces

See also: [[HODLNEER_INDEX]] | [[HODLNEER_CANON_INDEX]] | [[BADGE_VISUAL_SYSTEM]] | [[PRODUCT_PRINCIPLES]]

---

## Core Model Principle

The Hodlneer identity model is built on **two separate axes**:

1. **Era** — when the user entered crypto
2. **Verification** — how strongly that entry can be proven

These two axes must remain separate.

**Why:** Historical placement and credibility are not the same thing. A user can be early but poorly proven; a user can be later but strongly proven. Collapsing both into one "tier" system makes the product feel unfair, shallow, or gameable.

---

## Canonical Identity Formula

> **Badge Identity = Era × Verification**

A user's public Hodlneer identity is always the combination of one era classification and one verification classification.

Examples:
- Genesis • Verified
- Breakout • Confirmed
- Breakout • Declared
- Expansion • Verified

---

## Era System

### Purpose of Era
Era represents the user's historical placement in crypto — the wave or chapter they belong to and the cultural context of when they entered. Era is not the same as credibility. Era answers: *When did you arrive?*

### Canonical Era Names

#### 1. Genesis
**Definition:** Pre–December 2017

**Meaning:** Entered before Bitcoin's first major mainstream $20,000 breakout moment in December 2017. This represents the pre-mainstream era — before crypto became a major mainstream retail phenomenon.

**Community meaning:** The foundational early-believer era.

#### 2. Breakout
**Definition:** December 2017 through December 2020

**Meaning:** Entered during the first major mainstream breakout and the years immediately following. This captures the wave of people who entered as Bitcoin and crypto moved into broad public awareness but before the later massive normalization waves of 2021 and beyond.

**Community meaning:** The early mass-awareness era — still early in the big picture, but not pre-mainstream.

#### 3. Expansion
**Definition:** January 2021 and beyond

**Meaning:** Entered during the broader public normalization and expansion era — reflecting crypto becoming more broadly recognized through NFTs, broader retail awareness, institutional narratives, and larger social adoption waves.

**Community meaning:** The growth and normalization era.

### Era Design Interpretation
Era should be treated as historical context, chapter identity, and world atmosphere. It should influence badge atmosphere, reveal mood, visual language family, and contextual positioning. Era must not be treated as moral worth, superiority score, or final trust score.

---

## Verification System

### Purpose of Verification
Verification represents the strength of proof behind the user's claimed entry point — the trustworthiness of the identity result and the quality of evidence the system can stand behind. Verification answers: *How much can we trust it?*

### Canonical Verification Names

#### 1. Verified
**Definition:** Strongest proof level

**Meaning:** The user's entry can be strongly established through high-confidence evidence, ideally tied to direct account or on-chain history. Examples: connected wallet with historical activity, on-chain transaction history tied to the user, connected exchange/account history with strong historical signals.

**Community meaning:** The highest-confidence proof state.

#### 2. Confirmed
**Definition:** Moderate proof level

**Meaning:** The user's entry is supported by meaningful but less direct evidence than the Verified level. Examples: onboarding emails, account age indicators, platform membership history, less direct but still credible timeline evidence.

**Community meaning:** A respectable, supported proof state, but not the strongest possible one.

#### 3. Declared
**Definition:** Lowest proof level

**Meaning:** The user has declared their entry period, but the system does not have strong external evidence to verify it. Examples: user self-declaration, weak social proof, unverified stated history.

**Community meaning:** A valid participation state, but not a strong credibility state.

### Verification Design Interpretation
Verification should influence badge precision, confidence of visual treatment, structural crispness, secondary labeling, and public trust signaling. Verification should not be fully hideable — that would destroy the point of the system.

---

## Public Identity Rules

### Always Public
If the badge is shown, these must be public:
1. Era classification
2. Verification classification
3. Badge visual state derived from both
4. Any public-facing badge label or shorthand tied to the above

**Why:** The public badge must carry credibility and context. If a user can hide era or verification while still presenting the same prestige artifact, trust collapses.

### Optionally Public (User-Controlled)
1. Exact year
2. Exact month/date if ever supported
3. Wallet address details
4. Exchange source details
5. Balances
6. Raw evidence artifacts
7. Supporting timeline evidence
8. External linked accounts

**Why:** The product promise is credibility without forced exposure — proof without unnecessary doxxing.

### Default Privacy Position
Show badge result. Hide raw source details. This is the right balance.

---

## Important Integrity Rule

> Users can hide their raw data.
> They cannot hide or rewrite the badge credibility state.

This is one of the most important principles in the product.

---

## Badge Output Structure

### Primary Badge Output
`[Era] • [Verification]`

Examples:
- Genesis • Verified
- Breakout • Confirmed
- Expansion • Declared

This format is clean, readable, fair, extensible, and easy to represent visually and in copy.

### Optional Supporting Outputs
The system may later support additional metadata or flavor labels (sub-era distinctions, earned overlays, milestone markers, HDL-specific context layers), but these must never replace the core identity formula.

### Future Sub-Era Guidance
Not required for MVP, but should remain open. If sub-eras are introduced, they must remain subordinate to the main Era label and must not overcomplicate the primary product experience. Example direction: Genesis I / Genesis II, or internal chapter names under Genesis.

---

## Trust Model Summary

- **Era gives:** historical placement, cultural weight, context
- **Verification gives:** confidence, proof strength, trust level
- **Together they create:** a fairer identity system, a more honest product, a more resilient public badge language

---

## Product Interpretation Examples

**Example A — Early but weakly proven**
- Era: Genesis | Verification: Declared
- Interpretation: historically early, not strongly proven

**Example B — Slightly later but strongly proven**
- Era: Breakout | Verification: Verified
- Interpretation: not pre-mainstream, but highly credible and strongly evidenced

**Example C — Newer but real**
- Era: Expansion | Verification: Verified
- Interpretation: later era, but highly legitimate and well-established within that era

These examples show why the model is fairer than "early = automatically best."

---

## Integration Implications for HDL.fun

When Hodlneer identity is displayed inside HDL.fun:
- HDL should inherit the Hodlneer public identity result
- HDL should not reinterpret or downgrade the core identity formula
- HDL may add richer context, utility, or social display power
- HDL must not expose raw data that the user chose to keep private

---

## World / 3D / VR Implications

In world-based or Three.js surfaces:
- Era should influence environmental or atmospheric context
- Verification should influence certainty/quality/strength cues
- The hex-based badge should remain the compact public form of this identity

The world should reflect the logic. It should not invent a second identity system.

---

## Final Canonical Statement

> Era tells the world when you arrived.
>
> Verification tells the world how much your entry can be trusted.
>
> Hodlneer identity is the combination of both.

---

## Related Documents

- [[BADGE_VISUAL_SYSTEM]] — visual rules that map to era and verification as independent variables
- [[BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM]] — macro/micro visual relationship
- [[PRODUCT_PRINCIPLES]] — operational guardrails derived from this model
- [[REVEAL_SEQUENCE_SPEC]] — ensure `[Era] • [Verification]` format is used in dynamic reveal outputs
- [[ONBOARDING_COPY_AND_REVEAL_NARRATION]] — copy that reflects this identity structure
- [[LANDING_PAGE]] — public-facing simplified explanation of this model
- [[HODLNEER_TO_HDL]] — bridge rules that respect public/private identity boundaries
- [[HDL_TO_HODLNEER]] — reverse bridge aligned to this identity logic
- [[EPICS]] — implementation lanes that execute this model
- [[TIER_SYSTEM]] — material tier system that coexists with this formula on the badge
- `01_governance/decisions/I-1_TIER_MODEL_RECONCILIATION.md` — decision confirming Era × Verification and Material Tier are parallel, non-competing systems
