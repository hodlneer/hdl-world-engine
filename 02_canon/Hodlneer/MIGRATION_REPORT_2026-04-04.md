# Hodlneer Vault Migration Report — 2026-04-04

---

## 1. Summary

### Before

19 Hodlneer-related markdown files were sitting in the vault root with temporary handoff filenames like `HODLNEER_BADGE_VISUAL_SYSTEM_AND_CANON_UPDATE_INSTRUCTIONS.md`. Each file was wrapped in meta-instructions directed at Claude — placement directives, canon update rules, notes on where to move the file — rather than reading as a permanent vault document. One file had a `(1)` suffix from a duplicate export. No folder structure existed. No index files existed. No internal wiki-links connected documents to each other.

### What Was Done

- Created the canonical `02_canon/Hodlneer/` folder structure with five subfolders
- Rewrote all 19 source files as clean permanent vault docs (stripped all temporary wrapper language)
- Renamed every file from its handoff name to its final canonical name
- Added Obsidian wiki-links (`[[]]`) to every file — both at the top and in a Related Documents section
- Created two index/navigation files and updated the vault-level `CANON_INDEX.md`
- Moved all 19 source files to `archive/hodlneer_temp_handoffs_2026-04-04/`
- Vault root is now clean (4 permanent files remain: `CLAUDE.md`, `README.md`, `SYSTEM_OVERVIEW.md`, `2026-04-01.md`)

### After

21 canonical files live under `02_canon/Hodlneer/` across 5 subfolders. The vault is navigable, graph-friendly, and ready for human or agent contributors.

---

## 2. Folder Structure Created

```
02_canon/Hodlneer/
├── HODLNEER_INDEX.md
├── CANON/
│   ├── CANON_INDEX.md
│   ├── ASSET_PRODUCTION_CHECKLIST.md
│   ├── BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md
│   ├── BADGE_VISUAL_SYSTEM.md
│   ├── ICON_SYSTEM.md
│   ├── IDENTITY_MODEL.md
│   ├── LAUNCH_STRATEGY.md
│   ├── PRODUCT_PRINCIPLES.md
│   └── WALLPAPER_SYSTEM.md
├── COPY/
│   ├── APP_STORE_PAGE.md
│   ├── FAQ.md
│   ├── LANDING_PAGE.md
│   ├── LAUNCH_ANNOUNCEMENT.md
│   ├── MANIFESTO.md
│   ├── ONBOARDING_COPY_AND_REVEAL_NARRATION.md
│   └── SCREENSHOT_STORYBOARD.md
├── EXPERIENCE/
│   └── REVEAL_SEQUENCE_SPEC.md
├── EXECUTION/
│   └── EPICS.md
└── INTEGRATION/
    ├── HDL_TO_HODLNEER.md
    └── HODLNEER_TO_HDL.md
```

Also created: `archive/hodlneer_temp_handoffs_2026-04-04/`

---

## 3. File Migration Table

| Old Filename (vault root) | New Filename | New Path |
|---|---|---|
| `HDL_TO_HODLNEER_INTEGRATION_AND_CANON_UPDATE_INSTRUCTIONS.md` | `HDL_TO_HODLNEER.md` | `02_canon/Hodlneer/INTEGRATION/` |
| `HODLNEER_APP_STORE_PAGE_AND_CANON_UPDATE_INSTRUCTIONS.md` | `APP_STORE_PAGE.md` | `02_canon/Hodlneer/COPY/` |
| `HODLNEER_ASSET_PRODUCTION_CHECKLIST_AND_CANON_UPDATE_INSTRUCTIONS.md` | `ASSET_PRODUCTION_CHECKLIST.md` | `02_canon/Hodlneer/CANON/` |
| `HODLNEER_BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM_CANON.md` | `BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md` | `02_canon/Hodlneer/CANON/` |
| `HODLNEER_BADGE_VISUAL_SYSTEM_AND_CANON_UPDATE_INSTRUCTIONS.md` | `BADGE_VISUAL_SYSTEM.md` | `02_canon/Hodlneer/CANON/` |
| `HODLNEER_EPICS_AND_EXECUTION_PLAN_CANON_UPDATE_INSTRUCTIONS.md` | `EPICS.md` | `02_canon/Hodlneer/EXECUTION/` |
| `HODLNEER_FAQ_AND_CANON_UPDATE_INSTRUCTIONS.md` | `FAQ.md` | `02_canon/Hodlneer/COPY/` |
| `HODLNEER_ICON_SYSTEM_AND_CANON_UPDATE_INSTRUCTIONS.md` | `ICON_SYSTEM.md` | `02_canon/Hodlneer/CANON/` |
| `HODLNEER_IDENTITY_MODEL_AND_CANON_UPDATE_INSTRUCTIONS.md` | `IDENTITY_MODEL.md` | `02_canon/Hodlneer/CANON/` |
| `HODLNEER_LANDING_PAGE_COPY_AND_CANON_UPDATE_INSTRUCTIONS.md` | `LANDING_PAGE.md` | `02_canon/Hodlneer/COPY/` |
| `HODLNEER_LAUNCH_ANNOUNCEMENT_AND_CANON_UPDATE_INSTRUCTIONS.md` | `LAUNCH_ANNOUNCEMENT.md` | `02_canon/Hodlneer/COPY/` |
| `HODLNEER_LAUNCH_STRATEGY_AND_CANON_UPDATE_INSTRUCTIONS.md` | `LAUNCH_STRATEGY.md` | `02_canon/Hodlneer/CANON/` |
| `HODLNEER_MANIFESTO_AND_CANON_UPDATE_INSTRUCTIONS.md` | `MANIFESTO.md` | `02_canon/Hodlneer/COPY/` |
| `HODLNEER_ONBOARDING_COPY_AND_CANON_UPDATE_INSTRUCTIONS (1).md` | `ONBOARDING_COPY_AND_REVEAL_NARRATION.md` | `02_canon/Hodlneer/COPY/` |
| `HODLNEER_PRODUCT_PRINCIPLES_AND_CANON_UPDATE_INSTRUCTIONS.md` | `PRODUCT_PRINCIPLES.md` | `02_canon/Hodlneer/CANON/` |
| `HODLNEER_REVEAL_SEQUENCE_SPEC_AND_CANON_UPDATE_INSTRUCTIONS.md` | `REVEAL_SEQUENCE_SPEC.md` | `02_canon/Hodlneer/EXPERIENCE/` |
| `HODLNEER_SCREENSHOT_STORYBOARD_AND_CANON_UPDATE_INSTRUCTIONS.md` | `SCREENSHOT_STORYBOARD.md` | `02_canon/Hodlneer/COPY/` |
| `HODLNEER_TO_HDL_INTEGRATION_AND_CANON_UPDATE_INSTRUCTIONS.md` | `HODLNEER_TO_HDL.md` | `02_canon/Hodlneer/INTEGRATION/` |
| `HODLNEER_WALLPAPER_SYSTEM_AND_CANON_UPDATE_INSTRUCTIONS.md` | `WALLPAPER_SYSTEM.md` | `02_canon/Hodlneer/CANON/` |

**Total:** 19 source files → 19 canonical files. No content was lost.

---

## 4. Files Cleaned and Normalized

Every file was rewritten, not just renamed. The following was stripped from all files:

**Removed entirely:**
- `## Placement Instructions for Claude` sections — these directed Claude to move the file and explained where it belonged. Once the file is in its final home, this is noise.
- `## Notes for Claude` sections — agent-facing instructions with no permanent vault value.
- Inline sentences like "If this document is currently staged at the root..." and "Claude should treat this file as the canonical source for..."

**Transformed:**
- `## Canon Update Rules` — the intro language ("Claude should...") was removed. The cross-reference doc lists were preserved and folded into `## Related Documents` sections with wiki-links.
- `## Recommended Related Docs to Update` → `## Related Documents` with `[[wiki-links]]` replacing bare paths.
- `## Next Recommended Documents` — absorbed into Related Documents or removed where the recommendation was already complete (i.e., the file now exists).

**Duplicate normalized:**
- `HODLNEER_ONBOARDING_COPY_AND_CANON_UPDATE_INSTRUCTIONS (1).md` was the only file with a `(1)` suffix, indicating a second export of the same document. The content matched the intended single file. It was normalized into `ONBOARDING_COPY_AND_REVEAL_NARRATION.md` with no duplication — the `(1)` original is archived.

**Paths updated:**
- All internal doc references were converted from bare paths like `/Hodlneer/CANON/IDENTITY_MODEL.md` to Obsidian wiki-links like `[[IDENTITY_MODEL]]` pointing to final canonical locations.

---

## 5. Archived Files

All 19 source files were moved (not deleted) to:

`archive/hodlneer_temp_handoffs_2026-04-04/`

**Decision rationale:** Deletion would be irreversible and the source files serve as a record of the original handoff format. The archive folder is date-stamped to make its purpose clear. If a future contributor needs to verify what content existed before migration, the originals are recoverable. After a reasonable review period, these can be permanently deleted.

---

## 6. Index Files Created

### `02_canon/Hodlneer/HODLNEER_INDEX.md`
Top-level navigation for the entire Hodlneer vertical. Contains the full folder tree, a table linking to every doc with a one-line description of its purpose, a list of core invariants, and a callout for missing docs (specifically the PRD). This is the first file a new contributor should read.

### `02_canon/Hodlneer/CANON/CANON_INDEX.md`
Canon-specific navigation. Lists all 8 CANON docs with their purpose, describes the canon hierarchy (which doc is foundational, which are derived), and notes the missing PRD. Intended for contributors who are specifically working within the CANON subfolder and need to understand authority relationships between files.

### `02_canon/CANON_INDEX.md` (updated, not created)
The existing vault-level canon index was updated to add a **Product Verticals** section above the **Current Worlds** section. This registers Hodlneer as a recognized product vertical with a pointer to its entry point. No existing content was modified.

---

## 7. Linking Improvements

Every canonical file now has:
1. A top-of-file breadcrumb line with wiki-links to `HODLNEER_INDEX` and 2–3 immediate peer documents
2. A `## Related Documents` section at the bottom with annotated wiki-links to all directly related files

Key cross-links that did not exist before:
- `BADGE_VISUAL_SYSTEM` ↔ `BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM` (these two are peer visual canons that must be read together)
- `IDENTITY_MODEL` ↔ `BADGE_VISUAL_SYSTEM` (era/verification naming governs visual treatment)
- `IDENTITY_MODEL` ↔ `REVEAL_SEQUENCE_SPEC` (the `[Era] • [Verification]` format originates here)
- `LAUNCH_STRATEGY` ↔ `LAUNCH_ANNOUNCEMENT` (strategy → actual copy)
- `APP_STORE_PAGE` ↔ `SCREENSHOT_STORYBOARD` (these must stay in sync)
- `WALLPAPER_SYSTEM` ↔ `BADGE_VISUAL_SYSTEM` (badge must survive wallpaper use)
- `HODLNEER_TO_HDL` ↔ `HDL_TO_HODLNEER` (both directions reference each other explicitly)
- `PRODUCT_PRINCIPLES` ↔ `MANIFESTO` (principles operationalize the manifesto)
- `EPICS` references all canon docs it executes against (IDENTITY_MODEL, REVEAL_SEQUENCE_SPEC, BADGE_VISUAL_SYSTEM, WALLPAPER_SYSTEM, etc.)

The Obsidian graph should now have meaningful clusters around identity canon, visual canon, copy, and integration — rather than 19 isolated nodes.

---

## 8. Current Vault State Assessment

### Strong
- Folder structure is clean and matches the intended canonical layout exactly
- All 19 source docs are in their final homes with permanent filenames
- Content fidelity is intact — no copy was lost, condensed, or altered in substance
- Internal linking is complete — every file can navigate to its peers
- Vault root is clean
- `HODLNEER_INDEX.md` gives any new contributor a reliable entry point
- The two integration docs (`HODLNEER_TO_HDL` and `HDL_TO_HODLNEER`) are clearly separated and cross-referenced

### Still Slightly Messy
- `COPY/SCREENSHOT_STORYBOARD.md` and `COPY/APP_STORE_PAGE.md` partially duplicate screenshot copy. The App Store page already contains a screenshot section, and the storyboard contains the same frames in more detail. This is intentional duplication (one is store-facing, one is production direction), but a future contributor could get confused about which is authoritative for headline copy. Worth a clarifying note in one of the two files.
- The `EXPERIENCE/` folder has exactly one file. This is not wrong — the reveal spec is complex enough to warrant its own subfolder — but it may look sparse. If additional UX/interaction docs are created (e.g., onboarding flow diagram, wallpaper composition spec), they belong here.

### Missing
- **`CANON/HODLNEER_PRD.md`** — The single biggest gap. This file is referenced by name in nearly every canon doc but was never included in the handoff set. Until it exists, the canon folder has a dead reference. This is the highest-priority doc to create. See Section 10 for recommended content scope.
- `COPY/ICON_EXPLORATION_BRIEF.md` — Mentioned in `ICON_SYSTEM.md` and `ASSET_PRODUCTION_CHECKLIST.md` as a recommended next doc. Turns icon system canon into actionable creative directions. Lower priority than the PRD but useful before any design work starts.
- `CANON/APP_PREVIEW_SCRIPT.md` — Mentioned in `ASSET_PRODUCTION_CHECKLIST.md`. Turns App Store and reveal logic into a motion-ready trailer plan. Pre-production asset.
- No `08_bridges/hodlneer/` folder exists yet. The bridge layer (which translates canon into product repo requirements) is absent for this vertical. This is expected for now but will be needed before implementation begins in `hdl_react` or `hdl-node-backend-api`.

---

## 9. Recommended Next Steps

**1. Write `CANON/HODLNEER_PRD.md` immediately.**
This is the most-referenced missing file. Minimum viable content: standalone iOS app definition, core feature = the 3D Badge, signature moment = cinematic reveal, iOS wallpaper as primary distribution vector, privacy-first identity controls (public badge / private raw data), optional HDL integration. It should be short, authoritative, and consistent with the identity model already in place.

**2. Add a clarifying note to `COPY/APP_STORE_PAGE.md` or `COPY/SCREENSHOT_STORYBOARD.md`.**
One sentence at the top of each explaining the relationship: `APP_STORE_PAGE.md` owns final store-facing copy; `SCREENSHOT_STORYBOARD.md` owns production direction and visual composition intent. This prevents contributors from editing the wrong doc.

**3. Create `08_bridges/hodlneer/` with a product alignment gaps doc.**
Before any implementation work begins, a bridge doc should translate IDENTITY_MODEL + EPICS into concrete acceptance criteria for the product repos. Follow the pattern of `08_bridges/hdl-platform/HDL_PRODUCT_ALIGNMENT_GAPS.md`.

**4. Create `COPY/ICON_EXPLORATION_BRIEF.md`.**
A short creative brief (1–2 pages) that turns `ICON_SYSTEM.md` into actionable directions a designer can explore. Useful before any app icon work begins and referenced in the asset checklist.

**5. Validate graph in Obsidian.**
Open the graph view and confirm that the Hodlneer cluster looks coherent — `HODLNEER_INDEX` should be a high-connectivity hub, `IDENTITY_MODEL` should be the most-connected canon node, and integration docs should bridge the Hodlneer cluster toward HDL world docs. If any links are broken (wrong capitalization, path mismatch), fix them before onboarding new contributors.

---

## 10. Canon Integrity Check

The core message hierarchy is consistent across all docs:

1. Proof
2. Badge / reveal
3. Wallpaper
4. Privacy
5. HDL connection (optional, last)

This order appears consistently in `LAUNCH_STRATEGY`, `LAUNCH_ANNOUNCEMENT`, `APP_STORE_PAGE`, `LANDING_PAGE`, `SCREENSHOT_STORYBOARD`, and `PRODUCT_PRINCIPLES`. No doc inverts this or leads with HDL.

The two-axis identity formula (`Badge = Era × Verification`) is stated consistently in `IDENTITY_MODEL`, `FAQ`, `LANDING_PAGE`, `ONBOARDING_COPY_AND_REVEAL_NARRATION`, `REVEAL_SEQUENCE_SPEC`, and `BADGE_VISUAL_SYSTEM`. No doc collapses era and verification into a single tier system.

The standalone product principle is stated consistently across `MANIFESTO`, `PRODUCT_PRINCIPLES`, `HODLNEER_TO_HDL`, `HDL_TO_HODLNEER`, `LAUNCH_STRATEGY`, and `APP_STORE_PAGE`. No doc describes Hodlneer as a feature of HDL.fun.

**Known minor ambiguity:** `BADGE_TO_BITCOIN_WORLD_VISUAL_SYSTEM.md` references "any HDL world docs related to the Bitcoin sphere" that should be updated to acknowledge the badge as the personal-scale version of the hex geometry family. Those HDL world docs (`02_canon/btc_world/BTC_HEX_NETWORK_SPEC.md`, etc.) were not touched in this migration. The conceptual link exists in Hodlneer canon but is not yet written into the BTC world canon. This is a cross-vertical alignment task, not a Hodlneer-internal contradiction, but it should be addressed before 3D implementation begins.

**No contradictions found** within the Hodlneer vertical itself.

---

*Report generated 2026-04-04. Migration performed in a single session.*
