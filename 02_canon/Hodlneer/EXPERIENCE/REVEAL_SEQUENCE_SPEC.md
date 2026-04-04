# Reveal Sequence Spec

## Purpose
This document defines the frame-by-frame reveal sequence specification for the standalone Hodlneer product vertical. It is intended for: iOS engineering, motion design, 3D implementation, product design, creative direction, and execution planning.

This document translates the approved onboarding copy and reveal narration into a production-ready experience specification.

See also: [[HODLNEER_INDEX]] | [[ONBOARDING_COPY_AND_REVEAL_NARRATION]] | [[BADGE_VISUAL_SYSTEM]] | [[IDENTITY_MODEL]]

---

## Reveal Experience Goals

The reveal sequence exists to create a **high-value emotional payoff** after verification. It must:
- feel premium
- feel cinematic
- feel collectible
- reinforce legitimacy
- make users proud to share
- make the final badge feel earned, not assigned

This sequence is inspired by the emotional tension and reward of elite sports card reveals and premium collectible unveilings, but must remain original to Hodlneer.

---

## Core Reveal Principles

1. **Reveal, do not merely display**
2. **Build anticipation before certainty**
3. **Let verification feel meaningful**
4. **Treat the badge like a digital artifact**
5. **End in pride, not noise**
6. **Support future wallpaper and social sharing outputs by design**

---

## Experience Summary

The reveal sequence begins immediately after verification signals are processed. The experience is divided into five phases:

1. Detection
2. Signal Processing
3. Energy Build
4. Reveal Drop
5. Identity Lock

**Total ideal duration:** 8 to 14 seconds
- Anything shorter risks feeling flat
- Anything much longer risks feeling self-indulgent

---

## Visual Direction Summary

The reveal should feel: futuristic, dark-luxury, minimal but high-impact, luminous rather than noisy, precise, not chaotic.

Avoid: cartoon effects, cheap gaming FX, overcluttered interfaces, too much text on screen, generic "success" animations.

---

## Badge Reveal Object Model

The center object of the reveal is the **Hodlneer 3D Badge Card**.

This card should feel like: a collectible identity artifact, a hybrid of premium trading card, digital passport, and prestige badge, something worthy of display on a phone wallpaper.

The card must support: badge frame, era designation, verification designation, animated lighting state, subtle depth/parallax, and future personalization hooks.

---

# Frame-by-Frame Reveal Sequence

## Phase 1 — Detection
**Duration:** 1.5 to 2.5 seconds

**Visual State:** Dark background with subtle depth, ambient particles or faint energy dust, low-volume motion only, no badge visible yet, light pulse suggests system awakening.

**On-Screen Copy:**
- Scanning your crypto footprint…
- Signals detected.

**Motion Behavior:** Text fades in with calm confidence, background remains restrained, small signal flashes suggest data recognition, optional micro-line sweeps or distant grid motion.

**Sound Direction:** Low, cinematic hum. Small audio confirmation when "Signals detected" appears.

**Emotional Goal:** Curiosity, seriousness, legitimacy.

---

## Phase 2 — Signal Processing
**Duration:** 2 to 3 seconds

**Visual State:** Data fragments begin to appear — soft flashes of timeline markers, transaction-like traces, wallet signal motifs, verification geometry. These should remain abstract, not literal UI dashboards.

**On-Screen Copy:**
- Verifying origin…
- Cross-referencing activity…
- Establishing timeline…

**Motion Behavior:** Smooth layered animation, slight escalation of speed, background illumination begins to intensify based on detected badge output, early hints of final era color begin to bleed in subtly.

**Dynamic Logic:** Era color influence can begin here:
- Genesis = deep premium tone
- Breakout = high-energy premium tone
- Expansion = future-forward premium tone

**Sound Direction:** Rhythmic pulses, subtle rising tonal texture.

**Emotional Goal:** Anticipation, trust, "something real is being determined."

---

## Phase 3 — Energy Build
**Duration:** 2 to 3 seconds

**Visual State:** Light intensity rises, geometry starts converging toward center frame, card silhouette or badge outline begins to form indirectly, background energy becomes more focused, era color is now more apparent, but the final classification is still not shown.

**On-Screen Copy:**
- Your entry has been identified.
- Your proof has been validated.

**Motion Behavior:** Increase visual compression toward center, camera or composition subtly tightens, small pauses between lines to let weight land, build tension without rushing into the reveal.

**Sound Direction:** Stronger rise, controlled swell, sense of imminent drop.

**Emotional Goal:** Pressure, excitement, "this is my moment."

---

## Phase 4 — Reveal Drop
**Duration:** 1 to 2 seconds

**Visual State:** Sudden premium-impact reveal, bright controlled flash or energy break, the full Hodlneer 3D Badge Card enters frame decisively, card rotates or settles into an ideal presentation angle, lighting resolves around the badge in its final classification state.

**Primary Text:** You are a Hodlneer.

**Secondary Text:** `[Dynamic Era] • [Dynamic Verification]`

Examples:
- Genesis • Verified
- Breakout • Confirmed
- Expansion • Declared

**Motion Behavior:** The badge should not simply pop in. It should feel like it has been forged, found, or unlocked. One decisive impact moment is encouraged. Rotation/parallax should stop just short of becoming flashy.

**Sound Direction:** Signature reveal hit, followed by a confident, premium tail.

**Emotional Goal:** Pride, validation, emotional payoff, ownership.

---

## Phase 5 — Identity Lock
**Duration:** 2 to 4 seconds

**Visual State:** Motion settles into elegant idle state, badge remains fully visible, lighting breathes subtly, background reduces noise, final state is wallpaper-worthy and screenshot-worthy.

**On-Screen Copy:**
- Your identity is now proven.
- You decide how to show it.

**CTA Options:**
- Set as Wallpaper
- Share Your Reveal
- Continue

**Motion Behavior:** Slow idle animation only, badge remains premium and stable. This state should transition cleanly into: wallpaper preview, share export, or profile/badge details view.

**Sound Direction:** Resolve into confidence. Do not overplay the ending.

**Emotional Goal:** Calm pride, confidence, desire to show someone.

---

## Dynamic Content Logic

The reveal must support dynamic rendering based on: era classification, verification classification, privacy configuration, and future personalization systems.

### Required Dynamic Outputs
1. Era Label
2. Verification Label
3. Badge Frame Style
4. Lighting / accent behavior
5. Share output metadata

### Important Rule
Raw source data is **not** automatically revealed in the reveal moment. The reveal should emphasize badge identity, era, and verification strength. It should **not** automatically expose: exact wallet data, balances, exact timestamps, source accounts, or sensitive proof details.

---

## Era vs Verification Design Guidance

These are separate systems and must remain visually distinguishable (see [[IDENTITY_MODEL]]).

**Era communicates:** historical placement, community context, wave of entry.

**Verification communicates:** credibility, proof strength, trust level.

The design must avoid collapsing both into one single undifferentiated "tier" system.

---

## Social and Wallpaper Output Requirements

The final reveal state must be designed to support three downstream outputs:

**1. Social Share** — screenshot-friendly, short-form video export friendly, visually understandable without deep explanation.

**2. iOS Wallpaper** — adaptable to lock screen composition, adaptable to home screen composition, supports elegant idle motion. See [[WALLPAPER_SYSTEM]].

**3. HDL Integration Surface** — displayable later inside HDL.fun as a richer identity artifact. HDL may enhance or contextualize the badge, but should not redefine it.

---

## Post-Reveal Branching

After the reveal, the user should be able to choose:

**A. Set as Wallpaper** — takes user into wallpaper-specific composition and preview flow

**B. Share Your Reveal** — exports or prepares visual/video share output

**C. Continue** — moves user into badge details, privacy settings, optional HDL connection prompt

---

## Performance and Engineering Notes

The reveal must feel premium, but should not lag, overheat the device, depend on extreme particle counts, or require always-on network calls during the animation.

**Recommended approach:**
- Precompute reveal payload before animation begins
- Load dynamic badge state before entering Phase 1
- Treat the reveal sequence as a deterministic playback based on resolved badge outcome

---

## Accessibility Notes

The reveal must remain accessible even though it is cinematic:
- Reduced motion fallback
- Captions or readable text timing
- Haptic-safe alternatives
- Non-audio-dependent meaning
- Graceful fallback for lower-performance devices

A reduced motion version should preserve dignity, clarity, and reveal significance. It should not feel like a broken or stripped-down afterthought.

---

## Final Canonical Statement

> The reveal should make a user feel: "That felt important. I want to show this to someone. This feels like mine. This feels legit."

---

## Related Documents

- [[ONBOARDING_COPY_AND_REVEAL_NARRATION]] — narrative source that this spec implements
- [[BADGE_VISUAL_SYSTEM]] — badge hierarchy that the reveal camera and assembly must honor
- [[BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM]] — hex assembly language tied to world geometry
- [[WALLPAPER_SYSTEM]] — post-reveal path into wallpaper must feel natural and premium
- [[IDENTITY_MODEL]] — `[Era] • [Verification]` format used in Phase 4 dynamic outputs
- [[EPICS]] — Epic 4 (Signature Reveal System) implements this spec
- [[PRODUCT_PRINCIPLES]] — Principle 6: "Reveal Over Display"
