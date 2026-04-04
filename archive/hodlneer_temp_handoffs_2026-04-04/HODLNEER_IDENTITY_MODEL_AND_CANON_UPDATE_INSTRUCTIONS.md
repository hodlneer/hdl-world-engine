# HODLNEER_IDENTITY_MODEL_AND_CANON_UPDATE_INSTRUCTIONS.md

## Purpose
This document defines the **canonical identity model** for the standalone **Hodlneer** product vertical.

It is the source of truth for:
- era naming
- era boundaries
- verification naming
- verification strength levels
- badge output logic
- public vs private identity rules
- how identity is expressed across Hodlneer, HDL.fun, and future 3D/VR surfaces

This document exists so the product does not collapse into vague badge tiers or inconsistent naming.

---

## Placement Instructions for Claude

Place this file in the Obsidian vault at:

`/Hodlneer/CANON/IDENTITY_MODEL.md`

If this file is temporarily staged in the root of the HDL universe folder, Claude should move it into the path above once the folder structure is ready.

This file belongs in the `CANON` directory because it defines a foundational cross-product truth that must influence:
- product copy
- verification logic
- badge rendering
- reveal outputs
- settings/privacy behavior
- HDL integration rules
- future world/native display systems

---

## Canon Update Rules

Claude should treat this file as the canonical source for Hodlneer identity classification.

When this file is placed, Claude should review and align:
- `/Hodlneer/CANON/HODLNEER_PRD.md`
- `/Hodlneer/CANON/BADGE_VISUAL_SYSTEM.md`
- `/Hodlneer/CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md`
- `/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`
- `/Hodlneer/COPY/LANDING_PAGE.md`
- `/Hodlneer/COPY/ONBOARDING_COPY_AND_REVEAL_NARRATION.md`
- `/Hodlneer/EXECUTION/EPICS.md`
- `/Hodlneer/INTEGRATION/HODLNEER_TO_HDL.md`
- `/Hodlneer/INTEGRATION/HDL_TO_HODLNEER.md`

If older docs imply:
- one single “gold/silver/bronze” system is enough
- era and verification are the same thing
- users can fully hide credibility level
- proof strength is optional to badge identity
- badge output is just visual flair with no rules underneath

Those docs should be revised to match this model.

---

## Core Model Principle

The Hodlneer identity model is built on **two separate axes**:

1. **Era** — when the user entered crypto
2. **Verification** — how strongly that entry can be proven

These two axes must remain separate.

### Why
Because:
- historical placement and credibility are not the same thing
- a user can be early but poorly proven
- a user can be later but strongly proven
- collapsing both into one “tier” system makes the product feel unfair, shallow, or gameable

---

## Canonical Identity Formula

> **Badge Identity = Era × Verification**

This means a user’s public Hodlneer identity is always the combination of:
- one era classification
- one verification classification

Examples:
- Genesis • Verified
- Breakout • Confirmed
- Breakout • Declared
- Expansion • Verified

This is the public-facing logic the product should use by default.

---

## Era System

### Purpose of Era
Era represents:
- the user’s historical placement in crypto
- the wave or chapter they belong to
- the cultural context of when they entered

Era is not the same as credibility.
Era answers:
> “When did you arrive?”

---

### Canonical Era Names

#### 1. Genesis
**Definition:** Pre–December 2017

**Meaning:**  
Entered before Bitcoin’s first major mainstream $20,000 breakout moment in December 2017.

**Why this boundary exists:**  
This period represents the pre-mainstream era — the time before crypto became a major mainstream retail phenomenon.

**Community meaning:**  
This is the foundational early-believer era.

---

#### 2. Breakout
**Definition:** December 2017 through December 2020

**Meaning:**  
Entered during the first major mainstream breakout and the years immediately following it.

**Why this boundary exists:**  
This period captures the wave of people who entered as Bitcoin and crypto moved into broad public awareness but before the later massive normalization waves of 2021 and beyond.

**Community meaning:**  
This is the early mass-awareness era — still early in the big picture, but not pre-mainstream.

---

#### 3. Expansion
**Definition:** January 2021 and beyond

**Meaning:**  
Entered during the broader public normalization and expansion era.

**Why this boundary exists:**  
This period reflects crypto becoming more broadly recognized through NFTs, broader retail awareness, institutional narratives, and larger social adoption waves.

**Community meaning:**  
This is the growth and normalization era.

---

## Era Design Interpretation

Era should be treated as:
- historical context
- chapter identity
- world atmosphere

Era should influence:
- badge atmosphere
- reveal mood
- visual language family
- contextual positioning

Era should not be treated as:
- moral worth
- superiority score
- final trust score

That would be dumb and would poison the product fast.

---

## Verification System

### Purpose of Verification
Verification represents:
- the strength of proof behind the user’s claimed entry point
- the trustworthiness of the identity result
- the quality of evidence the system can stand behind

Verification answers:
> “How much can we trust it?”

---

### Canonical Verification Names

#### 1. Verified
**Definition:** Strongest proof level

**Meaning:**  
The user’s entry can be strongly established through high-confidence evidence, ideally tied to direct account or on-chain history.

**Examples of evidence sources may include:**
- connected wallet with historical activity
- on-chain transaction history tied to the user
- connected exchange/account history with strong historical signals

**Community meaning:**  
This is the highest-confidence proof state.

---

#### 2. Confirmed
**Definition:** Moderate proof level

**Meaning:**  
The user’s entry is supported by meaningful but less direct evidence than the Verified level.

**Examples of evidence sources may include:**
- onboarding emails
- account age indicators
- platform membership history
- less direct but still credible timeline evidence

**Community meaning:**  
This is a respectable, supported proof state, but not the strongest possible one.

---

#### 3. Declared
**Definition:** Lowest proof level

**Meaning:**  
The user has declared their entry period, but the system does not have strong external evidence to verify it.

**Examples of evidence sources may include:**
- user self-declaration
- weak social proof
- unverified stated history

**Community meaning:**  
This is still a valid participation state, but not a strong credibility state.

---

## Verification Design Interpretation

Verification should be treated as:
- confidence
- proof quality
- trust intensity

Verification should influence:
- badge precision
- confidence of visual treatment
- structural crispness
- secondary labeling
- public trust signaling

Verification should not be fully hideable.
That would destroy the point of the system.

---

## Public Identity Rules

The badge system must clearly distinguish between:
- what is always public
- what is optionally public
- what remains private by default

---

### Always Public
These must be public if the badge is shown:

1. **Era classification**
2. **Verification classification**
3. **Badge visual state derived from both**
4. **Any public-facing badge label or shorthand tied to the above**

### Why
Because the public badge must carry credibility and context.

If a user can hide era or verification while still presenting the same prestige artifact, the system becomes muddy and trust collapses.

---

### Optionally Public
These may be user-controlled:

1. Exact year
2. Exact month/date if ever supported
3. Wallet address details
4. Exchange source details
5. Balances
6. Raw evidence artifacts
7. Supporting timeline evidence
8. External linked accounts

### Why
Because the product promise is:
- credibility without forced exposure
- proof without unnecessary doxxing
- identity with privacy control

---

### Default Privacy Position
Default assumption should be:
- show badge result
- hide raw source details

This is the right balance.

---

## Important Integrity Rule

> Users can hide their raw data.
> They cannot hide or rewrite the badge credibility state.

This is one of the most important principles in the product.

---

## Badge Output Structure

The default badge output should follow this structure:

### Primary Badge Output
`[Era] • [Verification]`

Examples:
- Genesis • Verified
- Breakout • Confirmed
- Expansion • Declared

### Why this is the right format
It is:
- clean
- readable
- fair
- extensible
- easy to represent visually and in copy

---

## Optional Supporting Outputs

The system may later support additional metadata or flavor labels, but these should be secondary.

Possible future examples:
- sub-era distinctions
- earned overlays
- milestone markers
- HDL-specific context layers

These must never replace the core identity formula.

---

## Future Sub-Era Guidance

This is not required for MVP, but should remain open.

### Why it may be needed
Because:
- a 2011 Genesis user and a 2017 Genesis user are both Genesis, but socially they feel different
- the community may eventually want more nuance without destroying the top-level simplicity

### Guidance
If sub-eras are ever introduced:
- they must remain subordinate to the main Era label
- they must not overcomplicate the primary product experience
- they should feel like refined nuance, not category chaos

Example direction:
- Genesis I / Genesis II
- or internal chapter names under Genesis

This is future-facing, not immediate.

---

## Trust Model Summary

### Era gives:
- historical placement
- cultural weight
- context

### Verification gives:
- confidence
- proof strength
- trust level

### Together they create:
- a fairer identity system
- a more honest product
- a more resilient public badge language

---

## Product Interpretation Examples

### Example A — Early but weakly proven
- Era: Genesis
- Verification: Declared

Interpretation:
- historically early
- not strongly proven

### Example B — Slightly later but strongly proven
- Era: Breakout
- Verification: Verified

Interpretation:
- not pre-mainstream, but highly credible and strongly evidenced

### Example C — Newer but real
- Era: Expansion
- Verification: Verified

Interpretation:
- later era, but highly legitimate and well-established within that era

These examples matter because they show why the model is fairer than “early = automatically best.”

---

## Integration Implications for HDL.fun

When Hodlneer identity is displayed inside HDL.fun:
- HDL should inherit the Hodlneer public identity result
- HDL should not reinterpret or downgrade the core identity formula
- HDL may add richer context, utility, or social display power
- HDL must not expose raw data that the user chose to keep private

This protects trust across products.

---

## World / 3D / VR Implications

In world-based or Three.js surfaces:
- Era should influence environmental or atmospheric context
- Verification should influence certainty/quality/strength cues
- the hex-based badge should remain the compact public form of this identity

The world should reflect the logic.
It should not invent a second identity system.

---

## What Good Looks Like

A strong identity model makes people think:
- “That feels fair.”
- “That makes sense.”
- “Early and proven are clearly not the same thing.”
- “I understand what the badge is telling me.”
- “Privacy is respected without making the system fake.”

---

## What Must Never Happen

The identity model must never become:
- a blurry “gold, silver, bronze” soup
- a status flex with no proof logic
- a system where users can hide credibility but keep prestige
- a social ranking game detached from actual evidence
- a naming mess where every surface says something different

---

## Guidance for Future Teams

Any team working on:
- verification
- badge rendering
- reveal copy
- privacy settings
- HDL integration
- world display
- analytics
must reference this document.

This is not optional.
This is the naming and rules backbone of the product.

---

## Final Canonical Statement

> Era tells the world when you arrived.
>
> Verification tells the world how much your entry can be trusted.
>
> Hodlneer identity is the combination of both.

---

## Recommended Related Docs to Update

Claude should review and update:

### `/Hodlneer/CANON/HODLNEER_PRD.md`
Ensure era and verification are explicitly separated.

### `/Hodlneer/CANON/BADGE_VISUAL_SYSTEM.md`
Ensure visual rules map cleanly to era and verification as independent variables.

### `/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`
Ensure dynamic reveal outputs use `[Era] • [Verification]` format.

### `/Hodlneer/COPY/LANDING_PAGE.md`
Ensure public explanation of the model is simplified but aligned.

### `/Hodlneer/COPY/ONBOARDING_COPY_AND_REVEAL_NARRATION.md`
Ensure “proof over claim” messaging reflects this exact structure.

### `/Hodlneer/INTEGRATION/HODLNEER_TO_HDL.md`
Ensure the HDL bridge respects public/private identity rules.

### `/Hodlneer/INTEGRATION/HDL_TO_HODLNEER.md`
Ensure onboarding from HDL into Hodlneer reflects the same identity logic.

---

## Next Recommended Documents

After placing this file, the next documents to produce are:

1. `/Hodlneer/INTEGRATION/HODLNEER_TO_HDL.md`
2. `/Hodlneer/INTEGRATION/HDL_TO_HODLNEER.md`

Those two files will finish the original core canon set by defining how the products support each other without collapsing into each other.
