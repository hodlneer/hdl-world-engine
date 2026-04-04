# Onboarding Copy and Reveal Narration

## Purpose
This document provides the production-ready onboarding copy and reveal narration for the standalone Hodlneer iOS app. It defines onboarding tone, reveal language, privacy framing, identity framing, and the separation between Hodlneer and HDL.fun.

- **Hodlneer** = identity authority, verification layer, badge issuance, reveal moment, 3D wallpaper product.
- **HDL.fun** = social, wallet utility, profile amplification, optional enhanced showcase layer.
- Both products support each other, but neither is documented as fully dependent on the other.

See also: [[HODLNEER_INDEX]] | [[REVEAL_SEQUENCE_SPEC]] | [[IDENTITY_MODEL]] | [[LANDING_PAGE]]

---

## Core Principles

1. Identity over feature
2. Proof over claim
3. Mystery over explanation
4. Emotion over information

---

## Onboarding Flow (Screen-by-Screen Copy)

### Screen 1 — Entry
**Headline:** You don't claim your crypto story.

**Subtext:** You prove it.

**CTA:** Begin

---

### Screen 2 — Framing
**Headline:** Everyone says they were early.

**Subtext:** Few can prove when they started.

**CTA:** Continue

---

### Screen 3 — Reframe Identity
**Headline:** This isn't about when you say you entered crypto.

**Subtext:** It's about what you can verify.

**CTA:** Continue

---

### Screen 4 — What is Hodlneer
**Headline:** Become a Hodlneer

**Subtext:** A Hodlneer is someone who didn't just witness crypto — they stayed through it.

**CTA:** Continue

---

### Screen 5 — Privacy Assurance
**Headline:** Your data stays yours

**Subtext:** You choose what to reveal. We only verify what matters.

**CTA:** Continue

---

### Screen 6 — Verification Setup
**Headline:** Let's verify your origin

**Subtext:** Connect a wallet or account to begin.

**Options:**
- Connect Wallet
- Connect Exchange
- I'll declare manually

---

### Screen 7 — Transition to Reveal
**Headline:** Analyzing your crypto history…

**Subtext (animated / rotating):**
- Scanning signals
- Detecting activity
- Verifying origin

This screen transitions directly into the reveal sequence (see [[REVEAL_SEQUENCE_SPEC]]).

---

## What to Avoid
- Over-explaining blockchain mechanics
- Using technical jargon early
- Making users feel late or excluded

## Anchor Line
**You don't claim Hodlneer. You prove it.**

---

# Production-Ready Reveal Narration

## Purpose
This is the emotional and narrative layer of the Hodlneer Reveal Experience. It is intended for: text overlays, optional voiceover, timing-based motion copy, and reveal-state messaging.

The reveal is broken into five phases:
1. Detection
2. Signal Processing
3. Energy Build
4. Reveal Drop
5. Identity Lock

## Tone
Minimal. Confident. Cinematic. Never cheesy.

---

### Phase 1 — Detection
**Text:** Scanning your crypto footprint…

**Text:** Signals detected.

---

### Phase 2 — Signal Processing
**Text:** Verifying origin…

**Text:** Cross-referencing activity…

**Text:** Establishing timeline…

---

### Phase 3 — Energy Build
**Text:** Your entry has been identified.

**Text:** Your proof has been validated.

---

### Phase 4 — The Reveal
**Primary Text:** You are a Hodlneer.

**Secondary Text:** `[Dynamic Era] • [Dynamic Verification]`

Examples:
- Genesis • Verified
- Breakout • Confirmed
- Expansion • Declared

---

### Phase 5 — Identity Lock
**Text:** Your identity is now proven.

**Text:** You decide how to show it.

---

## Post-Reveal CTAs
- Set as Wallpaper
- Share Your Reveal
- Continue

---

## Optional Future Voiceover
In crypto, everyone claims they were early.
Few can prove it.
Today, you did.

---

## Emotional Goal
The user should feel: validated, seen, proud, curious to share.

## Final Line
Your identity is proven. What you do with it is up to you.

---

## Related Documents

- [[REVEAL_SEQUENCE_SPEC]] — frame-by-frame production spec for design, animation, iOS engineering
- [[IDENTITY_MODEL]] — era and verification taxonomy used in the dynamic reveal outputs
- [[LANDING_PAGE]] — landing page copy should echo the same identity-first language
- [[MANIFESTO]] — same philosophical foundation
- [[EPICS]] — onboarding and reveal implementation lanes (Epics 3 and 4)
