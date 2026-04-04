# HODLNEER_WALLPAPER_SYSTEM_AND_CANON_UPDATE_INSTRUCTIONS.md

## Purpose
This document defines the **wallpaper system** for the standalone **Hodlneer** iOS app.

It exists to clarify that wallpaper is not a throwaway export feature.
It is one of the most important product differentiators and a core distribution mechanic.

This document defines:
- what the wallpaper system is
- why it matters
- how it should behave
- how it should relate to the badge, reveal, and world geometry
- how lock screen and home screen use cases differ
- what visual, motion, and privacy rules must apply
- how future teams should design around wallpaper as a first-class product surface

---

## Placement Instructions for Claude

Place this file in the Obsidian vault at:

`/Hodlneer/CANON/WALLPAPER_SYSTEM.md`

If this file is currently staged in the root of the HDL universe folder, Claude should move it into the path above once the folder structure is ready.

This file belongs in the `CANON` directory because it defines a core product subsystem that influences:
- badge design
- reveal payoff
- app flows
- iOS product behavior
- share/distribution strategy
- visual system coherence
- future marketing and App Store messaging

---

## Canon Update Rules

Claude should treat this file as the canonical source for the Hodlneer wallpaper system.

When this file is placed, Claude should review and align:
- `/Hodlneer/CANON/HODLNEER_PRD.md`
- `/Hodlneer/CANON/BADGE_VISUAL_SYSTEM.md`
- `/Hodlneer/CANON/BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md`
- `/Hodlneer/CANON/PRODUCT_PRINCIPLES.md`
- `/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`
- `/Hodlneer/COPY/LANDING_PAGE.md`
- `/Hodlneer/COPY/APP_STORE_PAGE.md`
- `/Hodlneer/EXECUTION/EPICS.md`

If older docs imply:
- wallpaper is just an export afterthought
- wallpaper is a static screenshot with no design system
- wallpaper should expose raw identity data by default
- wallpaper is unrelated to the badge/world visual language
- wallpaper is optional enough to ignore during core design

Those docs should be revised.

---

## Core Wallpaper Principle

> The Hodlneer wallpaper is not a background.
>
> It is the ambient living display state of a proven identity artifact.

That is the mindset.

Wallpaper is one of the strongest bridges between:
- private ownership
- visible pride
- real-world sharing
- iPhone-native expression
- product virality

This is not decorative fluff.
This is one of the product’s strongest strategic hooks.

---

## Why Wallpaper Matters

The wallpaper system matters because it turns the badge into something that:
- lives beyond the app
- stays visible without effort
- can be shown in real life
- creates ambient identity signaling
- reinforces emotional attachment to the badge
- makes the product feel natively iOS-first

People do not always share links.
They do show their phones.

That matters more than most teams realize.

---

## Product Positioning of Wallpaper

Wallpaper is not:
- a bonus feature
- an export-only utility
- a marketing gimmick
- a generic image generator

Wallpaper is:
- a first-class use case
- a product differentiator
- a prestige display mode
- a core payoff after reveal
- a major bridge between badge and daily life

---

## Wallpaper System Goals

The wallpaper system must:

1. Make the badge feel worth carrying every day
2. Preserve the premium integrity of the badge
3. Work beautifully on iPhone lock and home contexts
4. Support subtle motion where appropriate
5. Respect privacy defaults
6. Reinforce the same visual language as the badge and Bitcoin world
7. Be instantly recognizable as Hodlneer, even without explanation

---

## Wallpaper Modes

The system should support at least two primary wallpaper modes.

### 1. Lock Screen Mode
This is the more minimal, prestige-focused mode.

#### Purpose
To make the badge feel:
- elegant
- iconic
- ambient
- worthy of being glanced at constantly

#### Characteristics
- cleaner composition
- stronger visual restraint
- fewer secondary details
- emphasis on badge silhouette and premium atmosphere
- suitable for always-visible presence

### 2. Home Screen Mode
This is the more expressive, immersive mode.

#### Purpose
To let the badge live in a richer visual field.

#### Characteristics
- more atmospheric support
- subtle environmental geometry
- more room for depth, particles, or structural world echoes
- still must remain calm and premium

### Important Rule
Lock and Home modes should feel related, not identical.
They serve different psychological jobs.

---

## Wallpaper Visual Hierarchy

The wallpaper must always preserve a clean visual hierarchy.

### 1. Badge Core
The badge remains the hero object.

### 2. Supporting Field
The background field should reinforce atmosphere, not compete with the badge.

### 3. Structural Geometry
Hex-based or network-inspired geometry may exist behind or around the badge, but it must remain subordinate.

### 4. Ambient Motion / Light
Motion and light should support the badge’s living presence, not turn the wallpaper into a noisy screensaver.

---

## Visual Language Requirements

The wallpaper must inherit the same world logic as:
- the badge
- the reveal
- the Bitcoin sphere / adoption visualization
- future 3D / VR surfaces

### Required Traits
- hex-based structural logic
- premium material atmosphere
- controlled lighting behavior
- coherent energy/signal language
- world-native feeling

### Desired Emotional Read
Someone should be able to see the wallpaper and feel:
- “This is not just some random crypto wallpaper.”
- “This feels like a serious artifact.”
- “This looks connected to a bigger digital world.”

---

## Privacy Rules for Wallpaper

The wallpaper should never force the user into more exposure than intended.

### Default Wallpaper Rule
The wallpaper should prioritize:
- badge object
- visual identity
- atmosphere
- optional public-safe label

It should not automatically expose:
- wallet addresses
- balances
- raw evidence sources
- detailed verification trail
- private linked account context

### Optional Public Text
Depending on the selected wallpaper mode, the system may optionally allow:
- era label
- verification label
- short identity line

But these must remain user-controlled and visually disciplined.

---

## Text on Wallpaper

### Rule
Text is optional, not mandatory.

The wallpaper must still work when the badge is shown with minimal or no text.

### Why
Because:
- the strongest wallpapers are emotionally readable at a glance
- too much text kills elegance
- a wallpaper should not look like a dashboard

### Recommended Text Tiers
1. **Visual-Only Mode**
   - badge only
   - no text
   - pure prestige

2. **Minimal Identity Mode**
   - badge + short public identity line
   - e.g. `Genesis • Verified`

3. **Expanded Mode**
   - badge + optional subtle supporting details
   - only if it still feels premium and uncluttered

Expanded mode must be used carefully.
Most users should probably gravitate toward Visual-Only or Minimal.

---

## Motion Principles

If motion is used, it must feel:
- subtle
- expensive
- alive
- low-noise
- battery-conscious
- emotionally restrained

### Good Motion
- slow breathing light
- subtle depth shift
- gentle signal travel through seams
- faint parallax or field movement
- low-frequency structural shimmer

### Bad Motion
- constant spinning
- hyperactive particles
- neon chaos
- obvious “look at me” gaming motion
- fake luxury loops

If the motion looks like a cheap crypto lock screen from 2021, it failed.

---

## Composition Principles

### Lock Screen Composition
Should favor:
- centered or intentionally offset badge anchor
- enough breathing room for clock/date areas
- silhouette-first clarity
- restrained field design

### Home Screen Composition
Should favor:
- badge in relationship with a wider field
- enough openness for app icons
- environmental geometry that supports but does not overpower

### Important iOS Rule
The design must respect native iPhone UI overlays and icon layouts.
The wallpaper should never look amazing only in a full-bleed mockup and then collapse under real icon/clock constraints.

That would be amateur hour.

---

## Badge-to-World Tie-In in Wallpaper

Wallpaper is one of the best places to subtly connect the personal badge to the macro world.

### Recommended Tie-In Cues
- faint hex field structures
- geometric gradients suggesting larger network curvature
- subtle world fragments or node fields
- depth cues hinting that the badge came from a larger living system

### Important Rule
Do not turn the wallpaper into a full Bitcoin sphere scene.
That is too literal and too busy.

The wallpaper should suggest relationship, not dump the whole universe into the background.

---

## Wallpaper as Post-Reveal Payoff

The wallpaper flow should feel like a natural continuation of the reveal.

### Emotional Sequence
1. Identity is verified
2. Badge is revealed
3. User experiences pride
4. Product offers:
   - Set as Wallpaper
   - Share Your Reveal
   - Continue

### Why This Matters
Wallpaper should feel like:
> “Take this moment with you.”

Not:
> “Export image now.”

That emotional framing changes everything.

---

## Wallpaper Flow Recommendations

### Flow A — Immediate Post-Reveal Wallpaper Path
- reveal completes
- user taps “Set as Wallpaper”
- enters wallpaper preview/editor
- chooses mode:
  - Visual-Only
  - Minimal Identity
  - Expanded
- selects lock/home/both treatment
- exports/applies

### Flow B — Badge Detail Wallpaper Path
- user later opens badge details
- chooses wallpaper option
- can reconfigure badge display style

### Flow C — Seasonal / Future Variant Path
- future versions may support alternate atmospheres or layouts
- only if badge integrity stays intact

---

## Customization Rules

Customization is good only when it does not corrupt the object.

### Users may customize:
- wallpaper mode
- amount of text shown
- background intensity
- some atmospheric styling
- lock vs home composition preference

### Users should not be allowed to:
- radically alter badge meaning
- remove mandatory public badge identity if text mode depends on it
- turn the badge into something visually unrelated to Hodlneer canon
- make it tacky

Freedom is not the same thing as turning the product into a sticker factory.

---

## Wallpaper System and HDL.fun

Hodlneer wallpaper should stand on its own.

If HDL.fun later references or showcases a user’s wallpaper state, HDL must treat it as:
- a Hodlneer-origin artifact
- a premium extension of the badge
- a display surface, not a redefined object

HDL must not:
- restyle the wallpaper into something off-brand
- imply the wallpaper only matters inside HDL
- flatten the artifact into a generic profile background

---

## Technical and Product Constraints

The wallpaper system should be designed with real iOS constraints in mind.

### Required Practical Considerations
- iPhone UI overlays
- safe composition under clock/date/notch/dynamic island areas
- performance and export practicality
- motion fallback paths
- screenshot/share compatibility
- clarity at multiple device sizes

This cannot be designed as fantasy art first and product second.

---

## Accessibility Considerations

The wallpaper system should support:
- reduced motion mode
- strong readability at a glance
- enough contrast without harshness
- simple composition choices for users who want less stimulation

Reduced motion should still feel premium.
It should not feel like the “boring disabled version.”

---

## What Good Looks Like

A strong wallpaper system should make people think:
- “That looks incredible on a phone.”
- “I can tell that means something.”
- “That feels premium.”
- “I want mine.”
- “This doesn’t look like a generic crypto wallpaper.”

---

## What Must Never Happen

The wallpaper system must never feel like:
- a static export nobody actually uses
- a cluttered infographic
- a privacy leak
- a random aesthetic unrelated to the badge
- a busy world scene that swallows the badge
- a gimmick added late in the process

That would waste one of the app’s most powerful advantages.

---

## Notes for Claude

When integrating this file:
- Treat wallpaper as a first-class subsystem
- Make sure badge design and wallpaper composition are designed together
- Keep the wallpaper emotionally tied to the reveal
- Preserve the visual/world language connection
- Ensure App Store and landing page messaging accurately reflect wallpaper’s importance

---

## Recommended Related Docs to Update

Claude should review and update:

### `/Hodlneer/COPY/APP_STORE_PAGE.md`
Ensure wallpaper remains a primary differentiator in the App Store story.

### `/Hodlneer/COPY/LANDING_PAGE.md`
Ensure wallpaper is framed as an important ambient identity surface.

### `/Hodlneer/EXECUTION/EPICS.md`
Ensure wallpaper has dedicated implementation workstreams and does not get buried as a “later” feature.

### `/Hodlneer/CANON/BADGE_VISUAL_SYSTEM.md`
Ensure the badge is designed to survive wallpaper use at a glance.

### `/Hodlneer/EXPERIENCE/REVEAL_SEQUENCE_SPEC.md`
Ensure the post-reveal path into wallpaper feels natural and premium.

---

## Final Canonical Statement

> The Hodlneer wallpaper is the ambient daily-life form of the badge.
>
> It must feel like a premium identity artifact living on the phone, not a background image exported from an app.

---

## Next Recommended Documents

After placing this file, the next strongest supporting docs to produce are:

1. `/Hodlneer/CANON/LAUNCH_STRATEGY.md`
2. `/Hodlneer/COPY/SCREENSHOT_STORYBOARD.md`

The launch strategy doc will define how the product enters the world.
The screenshot storyboard doc will help turn the App Store and reveal system into actual launch assets.
