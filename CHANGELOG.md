# HDL Universe — Vault Changelog

Tracks significant structural changes, new documents, and canon updates across the vault. Updated at the end of every working session that modifies the vault.

**Format:** newest entries at top. Each entry lists the date, what changed, and why.

---

## 2026-04-17 (Hardening Session)

### I-1 Tier Model Reconciliation — Resolved
- **Created** `01_governance/decisions/I-1_TIER_MODEL_RECONCILIATION.md` — governance decision doc closing open question I-1. Decision: Material Tier (Bronze/Silver/Gold/Platinum) and Era × Verification are parallel, non-competing systems. Era × Verification = primary public identity. Material Tier = badge visual weight. Both appear on the badge simultaneously. For Bronze/Silver/Gold, tier is informed by both Era and Verification but the exact mapping is a T-2 decision (still open). Platinum is an independent recognition track entirely separate from Era × Verification.
- **Updated** `02_canon/Hodlneer/CANON/TIER_SYSTEM.md` — added Badge Expression Format section (`[Material Tier]` / `[Era] • [Verification]`), linked to decision doc
- **Updated** `02_canon/Hodlneer/CANON/IDENTITY_MODEL.md` — added cross-references to TIER_SYSTEM and I-1 decision doc
- **Updated** `09_feedback/open-questions.md` — marked I-1 resolved with link to decision doc; I-2 remains open

### Admin Review Workflow Spec
- **Created** `08_bridges/hodlneer/ADMIN_REVIEW_WORKFLOW_SPEC.md` — full operational spec for the whitelist admin review layer. Defines: 6 queue states (pending_review, in_review, needs_more_info, approved, rejected, escalated), reviewer role hierarchy (Admin / Senior / Core Canon Leadership), required evidence checklist for approval, rejection reason codes (controlled vocabulary), post-approval badge trigger flow, post-rejection notification rules, needs_more_info end-to-end flow, immutable audit logging requirements (9 fields), admin vs end-user data visibility table, edge case handling (duplicate accounts, pseudonymous figures, withdrawal), and API endpoint mapping to `whitelist-api.yaml`.
- **Updated** `04_capabilities/recognition/WHITELIST_SYSTEM_SPEC.md` — expanded Section 10 (admin workflow states) to include `in_review` and `escalated`; linked to admin review spec; updated dependency table to mark admin review spec as existing

### Inbox Processing — HDL Platform Backlog 2026-04-13
- **Created** `09_feedback/HDL_PLATFORM_BACKLOG_PROCESSED_2026-04-17.md` — processed record for the platform backlog. Key finding: terminology conflict identified — old backlog references "Claimed → Social → On-Chain" verification tiers; canonical model (as of 2026-04-17) is "Declared → Confirmed → Verified". All implementation-level items routed to implementation repos; no vault canon changes required. Phase 1.5 blockers (LLC/EIN/Stripe) confirmed consistent with existing canon.
- **Updated** `00_inbox/HDL_PLATFORM_BACKLOG_2026_04_13.md` — marked PROCESSED with destination reference

### Backend Implementation Handoff
- **Created** `09_feedback/WHITELIST_BACKEND_HANDOFF_2026-04-17.md` — concise handoff note for hdl-node-backend-api. Whitelist matching engine and admin review layer are unblocked. Recommended implementation order: data ingestion → matching engine → review queue + audit log → badge trigger (Platinum) → tier assignment engine (Bronze/Silver/Gold, blocked on T-2). Schema notes included. Remaining blockers listed (T-1, T-2, I-2, T-3).

---

## 2026-04-17

### Whitelist System Spec + OpenAPI Bridge
- **Created** `04_capabilities/recognition/WHITELIST_SYSTEM_SPEC.md` — full system spec for the Platinum recognition pipeline. Defines: purpose (recognition signal, not badge assignment), data layers (source → canonical identity → match evaluation), entity types, eligibility states, match scoring model (exact/alias/handle/fuzzy + thresholds), decision policy (NO auto Platinum at launch — all matches → admin review), admin workflow states, product flow, security rules, and future expansion paths.
- **Created** `08_bridges/hodlneer/whitelist-api.yaml` — OpenAPI 3.0 spec for `hdl-node-backend-api`. Covers: `/whitelist/match` (onboarding match engine), `/whitelist/entities` + `/{id}` (admin entity management), `/whitelist/review-queue` (admin queue), `/whitelist/matches/{id}/approve|reject|flag` (decision endpoints). Full schema definitions: MatchRequest, MatchResult, WhitelistEntity, ReviewCase, ReviewDecision. Security: bearerAuth JWT; admin-only mutations; match_score not exposed to end users.
- **Created** `08_bridges/hodlneer/` folder — first bridge layer for Hodlneer → backend repo translation

### CoinDesk Most Influential Whitelist
- **Created** `03_data/whitelists/COINDESK_INFLUENTIAL_WHITELIST.md` — canonical whitelist of individuals featured on CoinDesk's annual "Most Influential in Crypto" lists (2014–2025). v1.1.0: 173 total entries, 153 HIGH confidence, 8 MEDIUM, 12 EXCLUDED. 2019 and 2020 years complete (100%). 2023 at 76% (38/50 confirmed), 2024 at 95%. Includes master deduplicated table, yearly breakdown, confidence tiers, data quality flags, and backend matching usage rules. Purpose: seed dataset for Hodlneer Platinum (Origin) tier recognition.
- **Created** `03_data/whitelists/COINDESK_INFLUENTIAL_WHITELIST.json` — normalized JSON schema version. Per-entry confidence (HIGH/MEDIUM/EXCLUDE), flags, is_anonymous and is_organization booleans, yearly breakdown with entry ID lists, corrections log in metadata, multi-year appearance statistics. ID namespace: cdwl_001 through cdwl_173.
- **Created** `03_data/` folder — new data layer for structured datasets supporting Hodlneer and other verticals

### Hodlneer Canonical App-Level PRD
- **Created** `02_canon/HODLNEER_PRD.md` — root document for the Hodlneer vertical. Defines Hodlneer as identity infrastructure + badge generation system. Covers: system role in HDL ecosystem, core user journey, onboarding system, badge generation lifecycle, HDL integration boundaries, recognition tier summary, system constraints, future expansion paths, full dependency table. Does not duplicate badge logic — references `HODLNEER_BADGE_PRD.md` and `TIER_SYSTEM.md`.
- **Updated** `02_canon/Hodlneer/HODLNEER_INDEX.md` — Document Status section now reflects both PRDs with correct scopes
- **Updated** `02_canon/Hodlneer/CANON/HODLNEER_CANON_INDEX.md` — Document Status section updated to match
- **Created** `00_inbox/2026-04-17_hodlneer-canonical-prd-app-level_INTAKE.md` — OD session preserved

### Vault Deduplication Audit
- **Archived** `02_canon/btc_world/BTC_HEX_NETWORK_CANON.md` → `archive/btc_deprecated_2026-04-17/` (deprecated, superseded by `BTC_HEX_NETWORK_SPEC.md`)
- **Archived** `02_canon/btc_world/BTC_HEX_NETWORK_CANON_FULL_SPEC.md` → same archive folder (deprecated, superseded)
- **Renamed** `02_canon/Hodlneer/CANON/CANON_INDEX.md` → `HODLNEER_CANON_INDEX.md` — eliminated naming collision with vault-level `02_canon/CANON_INDEX.md`
- **Updated** 8 CANON doc wiki-links: `[[CANON_INDEX]]` → `[[HODLNEER_CANON_INDEX]]`
- **Moved** `02_canon/Hodlneer/MIGRATION_REPORT_2026-04-04.md` → `09_feedback/` (operational record, not canon)
- **Moved** `2026-04-01.md` from vault root → `00_inbox/` (dated notes belong in inbox)
- **Updated** `HODLNEER_INDEX.md` and `HODLNEER_CANON_INDEX.md` — distinguished governance PRD (exists) from missing app-level canon PRD
- **Added** `TIER_SYSTEM.md` to `HODLNEER_CANON_INDEX.md` canon table
- **Created** `09_feedback/VAULT_DEDUPLICATION_AUDIT_2026-04-17.md` — full audit report with naming conventions, version rules, AI workflow rules, remaining checklist

### Intake Processing — 2026-04-17 OD Session
- **Created** `00_inbox/2026-04-17_hodlneer-badge-prd-tier-discussions_INTAKE.md` — preserved OD session
- **Created** `02_canon/Hodlneer/CANON/TIER_SYSTEM.md` — dual-layer tier model (Bronze→Platinum), canonical meaning mapping, validation framework, Platinum admin assignment, evolution/revocation rules
- **Created** `09_feedback/open-questions.md` — structured open questions log with blocking context
- **Updated** `01_governance/vision/HODLNEER_BADGE_PRD.md` → v2 — added evolution/revocation section, refined Platinum flagging path, linked TIER_SYSTEM

### HODLNEER Badge PRD
- **Created** `01_governance/vision/HODLNEER_BADGE_PRD.md` — badge product definition: dual-layer tier model, issuance model, share system, visibility rules, constraints

---

## 2026-04-16

### Paperclip System Design
- **Created** `06_paperclip/HODLNEER_PAPERCLIP_SYSTEM_DESIGN.md` — 7-role Paperclip org structure, CrewAI execution model, workflow types, delegation model, Claude's strict role boundaries, repo strategy (MetaGPT reference / CrewAI runtime / MSAF future), Phase 1 minimal runnable system

### 3D Rendering Capabilities
- **Created** `04_capabilities/3D_RENDERING_APPROACH.md` — rendering stack (R3F + Three.js), SAM3D for AI-assisted asset generation, Hodlneer badge implementation approach, Bitcoin sphere implementation approach, agent instructions

---

## 2026-04-04

### Hodlneer Vertical Migration
Full migration of 19 temp handoff files from vault root into canonical `02_canon/Hodlneer/` structure.

**Created — Canon:**
- `02_canon/Hodlneer/HODLNEER_INDEX.md`
- `02_canon/Hodlneer/CANON/HODLNEER_CANON_INDEX.md` (originally `CANON_INDEX.md`, renamed 2026-04-17)
- `02_canon/Hodlneer/CANON/IDENTITY_MODEL.md`
- `02_canon/Hodlneer/CANON/BADGE_VISUAL_SYSTEM.md`
- `02_canon/Hodlneer/CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md`
- `02_canon/Hodlneer/CANON/PRODUCT_PRINCIPLES.md`
- `02_canon/Hodlneer/CANON/WALLPAPER_SYSTEM.md`
- `02_canon/Hodlneer/CANON/LAUNCH_STRATEGY.md`
- `02_canon/Hodlneer/CANON/ICON_SYSTEM.md`
- `02_canon/Hodlneer/CANON/ASSET_PRODUCTION_CHECKLIST.md`

**Created — Copy:**
- `02_canon/Hodlneer/COPY/MANIFESTO.md`
- `02_canon/Hodlneer/COPY/LANDING_PAGE.md`
- `02_canon/Hodlneer/COPY/ONBOARDING_COPY_AND_REVEAL_NARRATION.md`
- `02_canon/Hodlneer/COPY/APP_STORE_PAGE.md`
- `02_canon/Hodlneer/COPY/SCREENSHOT_STORYBOARD.md`
- `02_canon/Hodlneer/COPY/LAUNCH_ANNOUNCEMENT.md`
- `02_canon/Hodlneer/COPY/FAQ.md`

**Created — Experience / Execution / Integration:**
- `02_canon/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`
- `02_canon/Hodlneer/EXECUTION/EPICS.md`
- `02_canon/Hodlneer/INTEGRATION/HODLNEER_TO_HDL.md`
- `02_canon/Hodlneer/INTEGRATION/HDL_TO_HODLNEER.md`

**Updated:**
- `02_canon/CANON_INDEX.md` — added Product Verticals section registering Hodlneer

**Archived:** 19 source temp handoff files → `archive/hodlneer_temp_handoffs_2026-04-04/`

**Created — Feedback:**
- `09_feedback/MIGRATION_REPORT_2026-04-04.md` (moved from `02_canon/Hodlneer/` on 2026-04-17)

---

## Pre-vault (prior structure)

Prior to the April 2026 vault migration, the repository held:

- `02_canon/hdl_world/` — HDL world doctrine, routing, identity, proof engine, topology, disciples, entities
- `02_canon/btc_world/` — Bitcoin world doctrine, rendering, data binding, entities, hex network spec
- `02_canon/shared/` — Cross-world rules: wallet model, visualization, rendering, LOD, particles, portals, glossary, agents, brand
- `08_bridges/hdl-platform/` — Frontend + backend integration plans, API catalog, product alignment gaps, QA protocol
- `CLAUDE.md`, `README.md`, `SYSTEM_OVERVIEW.md` — vault operating instructions and overview

---

## How to maintain this file

- Add an entry at the top for every session that modifies the vault
- Group changes under the date they occurred
- One line per change: **action** + filename + brief reason
- Do not list trivial fixes (typos, formatting). List structural and content changes only.
- This file is updated by Claude at the end of every working session upon request, or when files are added/moved/archived
