# HDL World — Proof Engine (Technical Specification)

## Purpose

Defines the system responsible for determining and validating a user's Genesis (On-Chain Since).

This document is implementation-focused and intended for engineering.

## Related Documents

Parent world docs:
- `_WORLD_OVERVIEW.md`
- `RULES.md`

Shared dependencies:
- `../shared/WALLET_MODEL.md`
- `../shared/ENGINE_PIPELINE.md`

Sibling implementation docs:
- `IDENTITY_ANCHOR.md`
- `ROUTING_ENGINE.md`
- `PROOF_ENGINE_LORE.md`

---

## Core Definition

Genesis = earliest provable signal of crypto participation

Sources:
- On-chain transaction timestamp
- Wallet creation activity
- Social signal (optional)
- Exchange account age (optional)

---

## Badge Tiers

### Tier 1 — Claimed
- User inputs year
- No validation

### Tier 2 — Social Verified
- Public signals (tweets, posts, etc.)
- Timestamp extracted and validated

### Tier 3 — On-Chain Verified
- Wallet linked
- Earliest transaction detected
- Highest authority

---

## Data Inputs

### On-Chain
- BTC (UTXO scan)
- ETH (tx history)
- SOL, XRP, etc.

### Off-Chain
- Twitter/X
- Reddit
- GitHub
- Exchange APIs (optional)

---

## Processing Pipeline

1. Identity Resolution
   - HDL handle → linked accounts

2. Data Collection
   - Pull tx history
   - Pull social timestamps

3. Normalization
   - Convert all timestamps to epoch ms
   - Standardize formats

4. Genesis Detection
   - Find earliest timestamp across all sources

5. Confidence Scoring

Example:
confidence = onchain_weight + social_weight + account_weight

---

## Priority Rules

- On-chain > social > claimed
- Earliest valid timestamp wins
- Conflicts resolved deterministically

---

## Anti-Gaming

- Require ownership proof for wallets
- Detect recycled wallets
- Flag abnormal patterns
- Prevent future-dated spoofing

---

## Privacy Controls

Users can:
- Hide wallet addresses
- Hide balances
- Reveal only verification status

---

## Output Model

{
  genesisYear: number,
  tier: "claimed" | "social" | "onchain",
  confidenceScore: number
}

---

## Display

Label:

ON-CHAIN SINCE {year}

---

## Status

Production Spec — Ready for Implementation
