# Whitelist System Spec

**Status:** Draft v1
**Owner:** Hodlneer Core
**Domain:** Recognition / Identity
**Related:** [[02_canon/HODLNEER_PRD|HODLNEER_PRD]] | [[01_governance/vision/HODLNEER_BADGE_PRD|HODLNEER_BADGE_PRD]] | [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]]

See also: [[04_capabilities/recognition/]] | [[08_bridges/hodlneer/whitelist-api|whitelist-api.yaml]]

---

## 1. Purpose

The whitelist system identifies real-world, notable crypto figures eligible for Platinum / Origin tier consideration.

It does **NOT** assign badges directly.
It produces **recognition candidates**.

---

## 2. Core Principle

> **Whitelist = Recognition Signal**
> **Badge = Final Outcome**

---

## 3. System Role

| System | Role |
|--------|------|
| Hodlneer | Identity + badge generation |
| Whitelist System | Recognition candidate detection |
| Badge System | Tier assignment |
| HDL | Identity display layer |

---

## 4. Data Layers

### 4.1 Source Layer

Raw ingestion:

- CoinDesk Most Influential lists → `03_data/whitelists/COINDESK_INFLUENTIAL_WHITELIST.md`
- Future curated sources

Preserves:
- raw names
- years appeared
- source URLs
- notes

### 4.2 Canonical Identity Layer

Each individual becomes one normalized entity.

```json
{
  "id": "person_vitalik_buterin",
  "canonical_name": "Vitalik Buterin",
  "aliases": ["vbuterin"],
  "entity_type": "individual",
  "eligibility": "eligible",
  "confidence": "high",
  "years_appeared": [2014, 2015, 2016, 2017, 2018],
  "appearance_count": 5
}
```

### 4.3 Match Evaluation Layer

Generated at onboarding. Tracks:

- match score
- reasoning
- decision state

---

## 5. Entity Types

| Type | Eligible |
|------|---------|
| `individual` | ✅ eligible |
| `organization` | ❌ excluded |
| `symbolic` | ❌ excluded |
| `anonymous` | ❌ excluded |
| `collective` | ❌ excluded |

---

## 6. Eligibility States

| State | Meaning |
|-------|---------|
| `eligible` | auto matching allowed |
| `manual_only` | requires admin review |
| `excluded` | ignored |

---

## 7. Matching Strategy

### Levels

1. Exact name match
2. Alias match
3. Handle match
4. Fuzzy match
5. Admin resolution

---

## 8. Match Scoring

| Signal | Score |
|--------|-------|
| Exact name | 1.00 |
| Alias match | 0.95 |
| Handle match | 0.90 |
| Fuzzy match | 0.80 |

**Thresholds:**
- ≥ 0.95 → high confidence
- 0.80–0.94 → review
- < 0.80 → ignore

---

## 9. Decision Policy

### Launch Rule

> **NO auto Platinum assignment.**
> **ALL matches → admin review.**

This is a permanent constraint at launch. Automated approval may be introduced post-launch via [[01_governance/]] decision — never by product convenience.

---

## 10. Admin Workflow

States:

| State | Meaning |
|-------|---------|
| `pending_review` | Candidate detected; awaiting admin |
| `in_review` | Reviewer has claimed and is actively evaluating |
| `approved` | Badge assignment authorized |
| `rejected` | No badge |
| `needs_more_info` | Additional verification requested |
| `escalated` | Flagged for senior review or Core Canon Leadership |

**Full admin review workflow spec:** `08_bridges/hodlneer/ADMIN_REVIEW_WORKFLOW_SPEC.md`

That document defines: reviewer roles, required evidence, action types, rejection reason codes, post-approval/rejection flows, audit logging requirements, and admin vs end-user data visibility rules.

---

## 11. Product Flow

```
User onboarding
    ↓
Match engine runs
    ↓
Candidate detected?
    ↓ yes
Review case created
    ↓
Admin decision
    ↓ approved
Badge assigned
```

---

## 12. Security Rules

- Whitelist data is **NOT** public
- Confidence scores are **NOT** exposed to users
- Only admin-level roles may mutate whitelist entries
- All decisions require audit logging
- Match results must never reveal which list the candidate appeared on

---

## 13. Dependencies

| Dependency | Location | Status |
|-----------|----------|--------|
| Hodlneer system PRD | `02_canon/HODLNEER_PRD.md` | Exists |
| Badge PRD | `01_governance/vision/HODLNEER_BADGE_PRD.md` | Exists |
| Tier system canon | `02_canon/Hodlneer/CANON/TIER_SYSTEM.md` | Exists |
| CoinDesk whitelist data | `03_data/whitelists/COINDESK_INFLUENTIAL_WHITELIST.json` | Exists |
| Backend API spec | `08_bridges/hodlneer/whitelist-api.yaml` | Exists |
| Admin review workflow spec | `08_bridges/hodlneer/ADMIN_REVIEW_WORKFLOW_SPEC.md` | Exists |
| Admin review UI | `08_bridges/hodlneer/` | Spec defined; UI not yet built |
| Onboarding flow | `02_canon/Hodlneer/COPY/ONBOARDING_COPY_AND_REVEAL_NARRATION.md` | Exists |

---

## 14. Future Expansion

- Social handle verification (Twitter/X, Farcaster)
- Institutional onboarding path (privacy-preserving proof for whales)
- Token-based Platinum privileges (HDLNR — future)
- Automated approval rules for clear-signal high-confidence matches
- Additional source lists (Forbes, TIME, others)

---

## 15. Summary

**The whitelist system is:**
- A recognition engine
- A filtering layer
- A trust amplifier

**It is NOT:**
- A ranking system
- A public leaderboard
- A badge assignment engine

---

## 16. Next Steps

- [ ] Implement API layer (`08_bridges/hodlneer/whitelist-api.yaml` → `hdl-node-backend-api/openapi/`)
- [ ] Ingest CoinDesk dataset into backend database
- [ ] Build admin review UI
- [ ] Connect to onboarding flow
- [ ] Define audit log schema

---

## Related Documents

- [[02_canon/HODLNEER_PRD|HODLNEER_PRD]] — system boundaries this spec operates within
- [[01_governance/vision/HODLNEER_BADGE_PRD|HODLNEER_BADGE_PRD]] — Platinum tier definition and assignment rules
- [[Hodlneer/CANON/TIER_SYSTEM|TIER_SYSTEM]] — Origin tier criteria
- [[03_data/whitelists/COINDESK_INFLUENTIAL_WHITELIST|COINDESK_INFLUENTIAL_WHITELIST]] — first source list
- [[08_bridges/hodlneer/whitelist-api|whitelist-api.yaml]] — OpenAPI spec for backend implementation
