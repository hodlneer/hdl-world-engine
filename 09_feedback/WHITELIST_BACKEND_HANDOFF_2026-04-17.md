---
title: Whitelist Backend Implementation Handoff
date: 2026-04-17
target_repo: hdl-node-backend-api
status: Ready for implementation (partial — see blockers)
---

# Whitelist Backend Implementation Handoff

## Summary

The Hodlneer whitelist recognition pipeline is now defined at the vault level. The backend implementation for the matching and admin review layer is **unblocked**. The badge tier assignment engine has remaining blockers noted below.

---

## What Is Unblocked

### 1. Whitelist Data Ingestion
- Source: `03_data/whitelists/COINDESK_INFLUENTIAL_WHITELIST.json`
- Action: Ingest into backend database as the initial whitelist entity set
- Schema: defined in `08_bridges/hodlneer/whitelist-api.yaml` (`WhitelistEntity` schema)
- 173 individual entries; confidence levels HIGH / MEDIUM / EXCLUDED
- ID namespace: `cdwl_001` – `cdwl_173`
- Excluded entries (`is_anonymous`, `is_organization`, `entity_type != individual`) must be filtered out at ingestion

### 2. Matching Engine
- Endpoint: `POST /whitelist/match` — triggers during onboarding
- Spec: `08_bridges/hodlneer/whitelist-api.yaml`
- Match levels: exact name → alias → handle → fuzzy
- Score thresholds: ≥ 0.95 high confidence; 0.80–0.94 review; < 0.80 ignore
- **NO auto Platinum.** All matches at any threshold → create a review case in `pending_review` state
- Match score must NOT be exposed in any user-facing response

### 3. Review Queue + Admin API
- Full workflow spec: `08_bridges/hodlneer/ADMIN_REVIEW_WORKFLOW_SPEC.md`
- Endpoints: `GET /whitelist/review-queue`, `POST /whitelist/matches/{id}/approve|reject|flag`
- Schema: `ReviewCase`, `ReviewDecision` in `whitelist-api.yaml`
- State machine: `pending_review` → `in_review` → `approved | rejected | needs_more_info | escalated`
- Reviewer role authorization: approve requires Senior Reviewer or above; reject and escalate available to Admin Reviewer
- All state transitions must produce immutable audit log entries (schema defined in section 12 of `ADMIN_REVIEW_WORKFLOW_SPEC.md`)

### 4. Post-Approval Badge Trigger
- On approval: queue a badge assignment event for the associated user account (Platinum tier)
- Badge assignment should be decoupled from the review action (event-driven, async)
- Notification to user on approval: generic (no whitelist name, no score, no process details)

---

## What Is Still Blocked

### B-1: Badge Tier Assignment Rules Engine (Bronze / Silver / Gold)
**Blocked on:** T-2 — Precise validation thresholds (which Era × Verification combination yields which material tier)

**Impact:** Cannot implement the rule engine that converts a user's submitted proof signals into a Bronze/Silver/Gold tier assignment.

**Not blocking:** The database schema can be designed now. Store `era`, `verification_level`, and `material_tier` as independent fields. Populate `material_tier` with a rules engine TBD. The whitelist/Platinum path is completely independent of this.

### B-2: Canonical Tier Names in Copy / Notifications
**Blocked on:** T-1 — Final canonical tier names for Bronze/Silver/Gold/Platinum

**Impact:** Cannot write notification copy, badge display labels (canonical meaning layer), or in-app tier descriptions.

**Not blocking:** Backend schema uses material tier names (Bronze/Silver/Gold/Platinum) as enum values. Canonical names are a copy/display concern, not a data schema concern.

### B-3: Declared Verification Abuse Prevention
**Blocked on:** I-2 — "Declared" has no integrity mechanism; self-declaration is unvalidated

**Impact:** The onboarding proof engine accepts self-declarations with no validation gate. This is a trust model gap that must be addressed before the verification system is considered complete.

**Not blocking:** Declared verification can be stored and displayed. The abuse prevention mechanism is a separate policy layer.

---

## Implementation Order Recommendation

1. **Ingest whitelist data** — no dependencies, zero blockers
2. **Build matching engine** (`/whitelist/match`) — depends only on ingested data
3. **Build review queue + admin API** — depends on matching engine creating cases
4. **Build audit logging** — should be built alongside review queue
5. **Build badge assignment trigger** (Platinum only) — depends on approval flow
6. **Build badge tier assignment engine** (Bronze/Silver/Gold) — blocked on T-2; implement last

---

## Key Files for Implementers

| File | Purpose |
|------|---------|
| `08_bridges/hodlneer/whitelist-api.yaml` | OpenAPI 3.0 spec — primary implementation reference |
| `08_bridges/hodlneer/ADMIN_REVIEW_WORKFLOW_SPEC.md` | Admin workflow policy — operational rules for the review layer |
| `03_data/whitelists/COINDESK_INFLUENTIAL_WHITELIST.json` | Source data for ingestion |
| `04_capabilities/recognition/WHITELIST_SYSTEM_SPEC.md` | Capability spec — system architecture and principles |
| `02_canon/Hodlneer/CANON/TIER_SYSTEM.md` | Tier canon — Platinum criteria and anti-gaming rules |
| `02_canon/Hodlneer/CANON/IDENTITY_MODEL.md` | Identity model — Era × Verification canonical formula |
| `01_governance/decisions/I-1_TIER_MODEL_RECONCILIATION.md` | Confirms Material Tier and Era × Verification are separate fields in the data model |

---

## Schema Notes

Based on the canonical model, the backend user badge record should include:

```
{
  era: "genesis" | "breakout" | "expansion",
  verification_level: "verified" | "confirmed" | "declared",
  material_tier: "bronze" | "silver" | "gold" | "platinum",
  platinum_source: "whitelist" | "manual_admin" | null,
  review_case_id: string | null,       // links to whitelist review case if Platinum
  badge_assigned_at: timestamp,
  badge_version: integer               // increments on upgrades
}
```

`material_tier` for Platinum is written by the admin approval flow. `material_tier` for Bronze/Silver/Gold is written by the proof engine (rules TBD — B-1).

---

## Remaining Vault Blockers (for Core Canon Leadership)

| ID | Question | Impact |
|----|----------|--------|
| T-1 | Final canonical tier names | Copy / display only; no backend schema impact |
| T-2 | Validation thresholds per tier | Blocks bronze/silver/gold rules engine |
| I-2 | Declared verification abuse prevention | Blocks trust model completeness |
| T-3 | Private verification path for whales | Blocks Platinum path for privacy-sensitive candidates |
