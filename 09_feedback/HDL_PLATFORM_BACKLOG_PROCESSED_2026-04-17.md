---
title: HDL Platform Backlog — Processed Record
source: 00_inbox/HDL_PLATFORM_BACKLOG_2026_04_13.md
processed: 2026-04-17
status: Processed — inbox item archived
---

# HDL Platform Backlog — Processing Record

## Origin

This document processes the inbox item `HDL_PLATFORM_BACKLOG_2026_04_13.md`, dated 2026-04-13. That item surfaced during a security incident investigation and full FE/BE audit. It contains implementation-level items for `hdl-node-backend-api` and `hdl_react`.

---

## Routing Decision

This content belongs in **implementation repos**, not in the vault canon or governance layer.

**Why:** The backlog items are infrastructure, security, and feature work for `hdl-node-backend-api` and `hdl_react`. The vault does not track implementation tasks — that belongs in Notion (HDL Task Management) and in the implementation repos themselves.

**What is extracted to the vault:** Only the items with canon or governance implications — specifically, the badge/proof system terminology note below.

---

## Canon Implication: Terminology Conflict

The backlog item references a "3 verification tiers: Claimed → Social → On-Chain" for the badge/proof system.

**This terminology is superseded.** As of 2026-04-17, the canonical verification system (defined in `02_canon/Hodlneer/CANON/IDENTITY_MODEL.md`) uses:

> **Declared → Confirmed → Verified**

The mapping to the old terminology:
| Old (Backlog — deprecated) | New (Canon) |
|---------------------------|-------------|
| Claimed | Declared |
| Social | Confirmed |
| On-Chain | Verified |

Implementation work on the badge/proof system must use the canonical names. Any tickets in Notion or code references using the old terminology should be updated.

---

## Implementation Items Summary

The following items from the backlog are implementation-level and belong in the implementation repo ticket system (Notion or GitHub issues), NOT the vault. They are listed here for traceability only.

### High Priority (Security / Infrastructure)
| Item | Repo | Notes |
|------|------|-------|
| Move secrets out of `.env`/`app.yaml` to DO env settings | `hdl-node-backend-api` | Security prerequisite — do first |
| Add `helmet` security headers to NestJS `main.ts` | `hdl-node-backend-api` | — |
| Add `@nestjs/throttler` rate limiting | `hdl-node-backend-api` | DDoS/brute-force protection |
| Fix open CORS in `main.ts` (`cors: true` → restrict to `hdl.fun`) | `hdl-node-backend-api` | — |
| Re-enable + implement WalletsModule | `hdl-node-backend-api` | Highest impact — frontend 404s |
| Re-enable MailModule in `app.module.ts` | `hdl-node-backend-api` | Email verification broken |
| Set up uptime monitoring (UptimeRobot or similar) | DevOps | `hdl.fun`, `api.hdl.fun`, `assets.hdl.fun` |

### Medium Priority (Features)
| Item | Repo | Notes |
|------|------|-------|
| Fix wallet signature mock in `AuthContext.tsx:208` | `hdl_react` | TODO comment in code |
| Implement share functionality in feed (`feed/page.tsx:566`) | `hdl_react` | — |
| Implement comment details in feed (`feed/page.tsx:570`) | `hdl_react` | — |
| Stripe fiat on-ramp (Phase 1.5) | `hdl-node-backend-api` + `hdl_react` | Requires LLC, bank account, Stripe — see canon `HDL_PHASE_1_5_CANON.md` |
| Badge/Proof system (Phase 2) | Both repos | Use canonical names (Declared/Confirmed/Verified) |
| On-chain proof engine (Phase 2) | `hdl-node-backend-api` | Scans wallet history for Genesis era classification |

### Low Priority
| Item | Repo | Notes |
|------|------|-------|
| Routing engine (Phase 3) | `hdl-node-backend-api` | Core canon value prop — see `02_canon/hdl_world/ROUTING_ENGINE.md` |

---

## Phase Prerequisites Note

The Phase 1.5 Stripe fiat on-ramp is blocked on entity formation:
- [ ] LLC / EIN
- [ ] Business bank account
- [ ] Stripe account

This matches the canon status in `02_canon/HDL_PHASE_1_5_CANON.md` and `CLAUDE.md`. No vault update required — already documented.

---

## Disposition

- **Inbox item status:** Archived — see `00_inbox/HDL_PLATFORM_BACKLOG_2026_04_13.md` (marked processed at top)
- **Canon update required:** YES — terminology conflict resolved above (Claimed/Social/On-Chain → Declared/Confirmed/Verified); no file change required as the correct canon already exists in `IDENTITY_MODEL.md`
- **Notion tickets:** Implementation items should be loaded or verified in Notion HDL Task Management DB `233364d4-6d29-80e4-a993-cf688d4056b8`
- **Implementation repo action:** None from this vault — items belong in repo issue trackers
