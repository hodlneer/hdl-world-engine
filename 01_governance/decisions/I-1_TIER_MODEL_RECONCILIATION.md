---
id: I-1
title: Tier Model Reconciliation — Material Tiers vs Era × Verification
status: Resolved
date: 2026-04-17
owner: Core Canon Leadership
source: open-questions.md
---

# Decision: Tier Model Reconciliation

## The Question

Two independent tier-like systems are active in the Hodlneer canon:

1. **Material Tier System** (`02_canon/Hodlneer/CANON/TIER_SYSTEM.md`)
   — Bronze / Silver / Gold / Platinum

2. **Era × Verification Identity Formula** (`02_canon/Hodlneer/CANON/IDENTITY_MODEL.md`)
   — Genesis / Breakout / Expansion × Verified / Confirmed / Declared

The open question (I-1): Are these competing systems that must be unified, or parallel systems that must be explicitly separated?

---

## Decision

**These are parallel systems. They are not competing and must not be collapsed into one.**

Each answers a different question about the user. Both appear on the badge simultaneously.

| System | Answers | Output |
|--------|---------|--------|
| Era × Verification | When did you arrive? How proven is that? | Primary public identity — e.g. "Genesis • Verified" |
| Material Tier | What is the visual weight and credibility standing of this badge? | Badge material — Bronze / Silver / Gold / Platinum |

---

## Relationship Between the Two Systems

### For Bronze, Silver, and Gold

The material tier is **informed by** both Era and Verification but is not mechanically identical to either.

- **Verification** determines the minimum floor: stronger proof produces higher tier eligibility.
- **Era** can be an elevating factor: early arrival with strong proof supports higher tier outcomes.
- The **exact mapping** (which combination of Era + Verification yields which tier) is a product threshold decision — see open question T-2, which remains open.

The key invariant: a user with a weaker verification level cannot receive a higher material tier than their evidence supports, regardless of Era. A user can be early but under-proven; the badge will reflect both facts truthfully.

### For Platinum

Platinum is **completely independent** of Era × Verification.

Platinum represents external recognition — ecosystem impact, protocol contribution, public standing in crypto. It is admin-assigned. It does not derive from the Era × Verification formula and cannot be earned through the standard onboarding proof flow.

A Platinum badge holder still has an Era × Verification identity (they are, for example, "Genesis • Verified"), but that identity does not grant Platinum. Recognition does.

---

## Badge Expression

A Hodlneer badge carries both systems simultaneously:

```
[Material Tier]
[Era] • [Verification]
```

Example:
```
Gold
Genesis • Verified
```

The material tier is the visual weight layer. The Era × Verification formula is the identity layer. These are additive, not redundant.

The canonical meaning names (pending T-1 decision) are internal labels for the material tier — they are the Layer 1 meaning beneath the Layer 2 visual. They do not replace Era × Verification.

---

## What This Resolves

- ✅ These systems are not competing — no unification required
- ✅ Neither system is deprecated or subordinate to the other
- ✅ Platinum is explicitly separated from the Era × Verification track
- ✅ For Bronze/Silver/Gold, tier is informed by Era × Verification but the specific mapping is a separate decision (T-2)
- ✅ The badge expression format is defined: Material Tier above, Era • Verification below

---

## What Remains Open

| Question | File | Status |
|----------|------|--------|
| T-1: Final canonical tier names for Bronze/Silver/Gold/Platinum | `09_feedback/open-questions.md` | Open |
| T-2: Precise validation thresholds — which Era × Verification combination yields which material tier | `09_feedback/open-questions.md` | Open |

These are not blocking for backend schema design. The database can store `era`, `verification`, and `material_tier` as independent fields. The rules engine that populates `material_tier` depends on T-2.

---

## Impacted Documents

| Document | Required Action | Status |
|----------|----------------|--------|
| `02_canon/Hodlneer/CANON/TIER_SYSTEM.md` | Add reference to this decision; add badge expression format | Update needed |
| `02_canon/Hodlneer/CANON/IDENTITY_MODEL.md` | Add cross-reference to TIER_SYSTEM and this decision | Update needed |
| `09_feedback/open-questions.md` | Remove I-1 row; mark resolved with link to this doc | Update needed |

---

## Related Documents

- `02_canon/Hodlneer/CANON/TIER_SYSTEM.md` — material tier canon
- `02_canon/Hodlneer/CANON/IDENTITY_MODEL.md` — era × verification canon
- `09_feedback/open-questions.md` — remaining open questions (T-1, T-2)
- `04_capabilities/recognition/WHITELIST_SYSTEM_SPEC.md` — Platinum recognition pipeline
