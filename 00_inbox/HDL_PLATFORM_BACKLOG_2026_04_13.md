# HDL Platform Backlog
**Date Added:** 2026-04-13
**Source:** Security incident investigation + full FE/BE audit
**Notion DB:** HDL Task Management (`233364d4-6d29-80e4-a993-cf688d4056b8`)

> **STATUS: PROCESSED — 2026-04-17**
> Processed by: hardening session
> Destination: `09_feedback/HDL_PLATFORM_BACKLOG_PROCESSED_2026-04-17.md`
> Disposition: Implementation items logged; terminology conflict (Claimed/Social/On-Chain) noted as superseded by canonical Declared/Confirmed/Verified. No vault canon changes required.

---

## High Priority

- [ ] **Fix credentials-in-code** — move all secrets out of `.env` / `app.yaml` into DO App Platform env settings. Do this before any other work.
- [ ] **Add `helmet` security headers** to NestJS backend (`main.ts`)
- [ ] **Add `@nestjs/throttler` rate limiting** to backend — currently wide open to DDoS/brute-force
- [ ] **Fix open CORS** in `main.ts` — `cors: true` accepts all origins, restrict to `hdl.fun`
- [ ] **Re-enable + implement WalletsModule** on backend — frontend wallet UI calls endpoints that return 404. Highest impact item.
- [ ] **Re-enable MailModule** in `app.module.ts` — email verification completely broken
- [ ] **Set up uptime monitoring** (UptimeRobot or similar) — frontend crashed for 6 days undetected. Monitor: `hdl.fun`, `api.hdl.fun`, `assets.hdl.fun`

## Medium Priority

- [ ] **Fix wallet signature** in `AuthContext.tsx:208` — currently a mock (TODO comment)
- [ ] **Implement share functionality** in feed — `feed/page.tsx:566`
- [ ] **Implement comment details** in feed — `feed/page.tsx:570`
- [ ] **Stripe fiat on-ramp** — Add Funds, premium subscriptions (Phase 1.5). Requires: LLC/Corp entity + business bank account + Stripe account.
- [ ] **Badge/Proof system** — DB entities + API + frontend display. On-Chain Since, 3 verification tiers (Claimed → Social → On-Chain). Phase 2.
- [ ] **On-chain proof engine** — scan wallet history to determine Genesis year, assign verification tier. Phase 2.

## Low Priority

- [ ] **Routing engine** — send to `@handle`, engine resolves to correct wallet + chain + bridges. The core canon value prop. Phase 3.

---

## Context

These items surfaced during:
1. A DDoS/botnet security incident on the DO frontend droplet (Jan 2026) — fully remediated Apr 7, 2026
2. A full FE/BE audit cross-referenced against the HDL Universe canon (`github.com/hodlneer/hdl-universe` develop branch)

Full platform status: `/Users/hodlneer/hdl_world/HDL_PLATFORM_STATUS.md`
