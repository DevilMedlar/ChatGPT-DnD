# Turn Save

This file is the temporary authoritative ledger for the current unfinished **Campaign Turn**.

When this skeleton is copied into a numbered campaign, keep its explanatory text and labeled templates as fill-out guidance. A template is documentation, not an event, roll, transaction, or canonical state record.

`../../Rule/CAMPAIGN_TURNS_AND_STEPS.md` governs Campaign Turn operation. `../../Rule/CORE_GAME_MECHANICS.md` governs campaign time. `../../Rule/REPRODUCTION_AND_LINEAGE.md` governs reproductive checks and lifecycle events. `../../Rule/SAVES_VERIFICATION_AND_RECOVERY.md` governs final review, reconciliation, verification, recovery, and reset.

The effective state during an unfinished Turn is the last completed permanent state at `Base save revision` plus this ledger's overlay.

## Active Campaign Turn

- **Campaign Turn:** 1
- **Status:** ready
- **Current Step:** 0
- **Current Scene:** Morning at Briarbridge
- **Base save revision:** 1
- **Start hold:** The player approved character creation with "yes but not starting yet". Keep this Turn ready, not in progress. Do not narrate the prepared opening, create Step 1, roll, or advance the clock until the player explicitly asks to start play. The prepared baseline frame is in `world_state.md`.

## Campaign Clock

- **Start Clock:** Campaign Day 1, 08:00:00
- **Current In-Turn Clock:** Campaign Day 1, 08:00:00
- **Total Elapsed This Turn:** 0 seconds

### Time Changes

Record each material time change in order:

```text
- Step N: Start clock -> End clock; elapsed duration; activity or reason; scheduled events reached or crossed
```

Do not advance time for out-of-fiction discussion. Do not silently skip an appointment, deadline, effect expiration, biological milestone, laying date, hatching date, or other scheduled event crossed by a time jump.

## Turn Events

Record numbered Steps, player decisions, rolls and results, narration with recovery value, scene changes, mechanical outcomes, and state deltas.

### Pre-play reference-art intake — Step 0, out of fiction

The player supplied the two repository images below and requested handling under the art rules. Both paths were verified on `main` and both images were visually inspected on 2026-09-07; downloaded bytes matched the listed Git blob SHAs. This is reference intake during the existing start hold, not a numbered gameplay Step or a played scene. Preserve these pending records when Turn 1 later starts.

- Art: `campaigns/campaign-1/art/Seren.png` — Seren Ashvale, ChatGPT-controlled PC / co-protagonist. Verified blob `1a5b755ece0002ca04aeb0864308c4e18671b00a`.
- Art: `campaigns/campaign-1/art/Cutlor_Awakened.png` — Cutlor Ashvale, player-controlled PC; manifested / awakened presentation reference only. Verified blob `fdccd041c5c20ef1e1760b369a0a23d4d5f2a7bb`.

Provenance: player-supplied, manually added repository images. Original generator, prompt, and creation date are not independently established. Apply `../../Rule/IMAGES_VISUALS_AND_REFERENCE_ART.md` and the structure in `art/art_log.md` at the normal Turn Final Review; image existence does not finalize permanent reference metadata.

**Seren — pending visual-reference notes**

- Canonical matches: humanlike face, warm light-brown skin and freckles, amber/gold eyes, wavy copper-auburn hair with partly gathered styling, two rust-red fox ears with dark tips and pale interiors, one rust-red tail with an ivory tip, fitted leather collar with brass-colored hardware, cream lace bra, charcoal mini skirt, white thigh-high socks, brown boots, plum leaf-stitched cloak, belt gear, and wooden lute.
- Inspiration only: pose, expression, warm lighting, distant town/landscape, exact lute ornament, cloak fastener, and photographic proportions. The background establishes no campaign location, scene, clock, or weather; the portrait does not verify numerical height/weight or unseen hair length.
- Inaccuracies / limits: three dagger hilts are visible at the belt, whereas the inventory arrangement is two belt daggers and two packed daggers, four owned total. Leather Armor is not visibly worn in the portrait, but remains equipped in current state. An apparent human-ear/earring detail near the hair is noncanonical: written appearance specifies no separate visible human ears and no added jewelry. Her left-hand scar, second pouch, and other obscured details are not reliably verified here; omission does not remove them. Collar color and other colors remain governed by written canon under the warm lighting.
- Existing text discrepancy: the character-sheet appearance owner describes the reference-matching bra/skirt/socks outfit, while the inventory's Traveler's Clothes description still says cream blouse and charcoal trousers. Reference comparison uses the character-sheet appearance authority. The image intake does not itself resolve this pre-existing text inconsistency or change the owned clothing set.

**Cutlor — pending visual-reference notes**

- Canonical matches: broad muscular humanlike build, strong jaw and clean-shaven face, warm medium-brown skin, black swept-back hair, green eyes, dark horns, a pair of copper-brown membraned wings, tapering dark/copper-toned tail, sleeveless dark leather armor with copper-colored stitching, open-finger metal-knuckle gauntlets, round shield, belt pouch, dark trousers, and brown boots.
- Inspiration only: stance, expression, warm lighting, architectural background and banner, and exact leather-panel or metalwork detailing. No depicted heraldry, location, allegiance, equipment property, or additional possession is adopted.
- Inaccuracies / limits: face/neck/arm scales are much more prominent and armorlike than the established barely noticeable, fine, smooth, low-profile charcoal scales with restrained copper sheen. Written subtle texture remains authoritative in both forms. Horn visibility and perspective do not supersede the symmetrical pair or written horn length, wing span, tail length, height, or weight. Natural claws and omitted travel gear remain established even where not clearly visible.
- Form scope: the image illustrates an available manifested / awakened appearance; it is not an ordinary veiled-form portrait or evidence of a transformation, Rage, Awakening use, healing, Temporary HP, AC change, flight, or elapsed time. Current horns/wings/tail stay withdrawn and Awakening stays inactive.

No image difference is adopted as new textual appearance or equipment canon by this intake.

## Current In-Turn State

Maintain a compact current overlay needed to continue or recover the Turn. Do not copy every permanent file here.

- **Pre-play art overlay:** The two verified reference images and their continuity notes above await the normal Turn Final Review and save confirmation. Keep Turn 1 ready at Step 0 and preserve the existing start hold.
- **Gameplay state:** No Step, scene, clock, character appearance, equipment, HP, resource, XP, or currency change. Campaign Day 1, 08:00:00; base save revision 1. Cutlor remains veiled with horns/wings/tail withdrawn, Rage inactive and Awakening inactive.

## Pending Reproductive Events

Record only qualifying mechanical and continuity facts. Do not store graphic scene detail merely to prove that an event occurred.

### Conception Check Template

- **In-world clock:**
- **Female parent / stable reference:**
- **Male parent / stable reference:**
- **Compatibility:** Naturally compatible / Cross-species compatible / Conditionally compatible
- **Conditional requirements and status:**
- **Male fertility status / modifier:**
- **Female fertility status / modifier:**
- **Prevention / contraception:** None / Effective block / Chance-based method / Other established effect
- **Prevention failure roll, when required:**
- **Base Conception Target:**
- **Explicit effect modifiers:**
- **Final Conception Target:**
- **First player d10, tens digit:**
- **Second player d10, ones digit:**
- **Combined percentile result:** `00` = `100`
- **Outcome:** Conception / No conception / Blocked before roll
- **Next conception-eligible clock for this exact pair:** Check clock + 24 hours
- **Female development route on success:** Live-bearing / Egg production and laying
- **Offspring or fertilized-egg count roll and result on success:**
- **Calculated due date or laying date:**
- **Calculated hatching date, when applicable:**
- **What the core PCs know:**
- **Pending permanent destinations:** Both participants' cooldown state; female parent state and world schedule on success
- **Notes:**

Use at most one conception check per exact male/female pairing during any 24 in-world hours. The cooldown survives the Campaign Turn save and ledger reset until its next eligible clock passes.

Do **not** roll biological sex, visible appearance, or final mechanical hybrid traits at conception. Biological sex and visible appearance are resolved at live birth or hatching. Mechanical hybrid traits remain TBD after birth during aging.

After conception succeeds, do not make later conception checks for that female until the blocking pregnancy or egg-production state ends.

### Reproductive Lifecycle Event Template

Use for detection, pregnancy or egg milestones, laying, incubation risks, birth, hatching, visible appearance, developmental milestones, or adult fertility establishment.

- **In-world clock:**
- **Event type:**
- **Parent / child / egg records and stable references:**
- **Established trigger or milestone:**
- **Required player roll, if any:**
- **Player result and calculation:**
- **Outcome:**
- **Next eligible detection clock, after a failed mundane check:** Check clock + 24 hours
- **What the core PCs know:**
- **New or changed persistent state:**
- **Pending permanent destinations:**
- **Scheduled next milestone:**
- **Notes:**

After a failed mundane detection check, no further mundane detection check for that same reproductive state occurs until 24 in-world hours later, regardless of examiner. The cooldown survives save and reset until it expires.

At live birth or hatching, resolve biological sex and visible appearance for each individual and create the persistent child record. Mechanical hybrid traits are not invented at conception or birth; they are resolved only later during aging under a player-approved mechanic.

A healthy ordinary milestone succeeds without a random complication roll. A risk roll requires a documented risk, stated DC, actor, and possible outcomes before the player rolls.

## Pending Shop Transactions

When a shop purchase occurs during an active Campaign Turn, keep the connected transaction temporary here until Confirmation Gate 1.

### Shop Transaction Template

- **Shop NPC ID / business:**
- **Buyer:**
- **Official item reference:** If applicable
- **Item:**
- **Quantity:**
- **Base Price for one item:**
- **Base Price basis:** Routine recurring / GM-established
- **Factors already included in Base Price:** None / list each distinct factor once
- **Final Unit Price modifiers applied:** None / list each distinct modifier once
- **Final Unit Price after copper rounding:**
- **Final Transaction Price:** Quantity × Final Unit Price
- **Vendor stock before / after:**
- **Buyer currency delta:**
- **Inventory target / acquisition:**
- **Acquisition mechanics snapshot:**
- **Stack result:** New entry / Merge / Keep separate / Not applicable
- **Notes:**

Two identical items cost exactly twice the Final Unit Price, three cost three times that price, and so on. A Final Unit Price cannot be negative; `0 CP` means free.

Vendor quantity, buyer currency, acquired inventory, acquisition snapshot, and any required NPC master-ownership update reconcile as one transaction. Do not permanently apply only one side.

## Pending Permanent Transfers

List only actual new or changed persistent state and required mirrors, organized by destination file.

### `art/art_log.md`

Pending new visual-reference metadata only; this file is currently blank of established references. At Final Review, re-read it and `character_sheet.md`, compare these proposals with current content, and remove anything already recorded or unchanged before showing Exact Planned Permanent Transfers.

- **Player-Controlled PC references:** Set Primary reference to `campaigns/campaign-1/art/Cutlor_Awakened.png`, explicitly scoped to manifested / awakened presentation only. Other verified references: none; no ordinary veiled-form image supplied. Transfer the provenance, canonical matches, inspiration-only details, inaccuracies, and form-scope notes from this intake.
- **ChatGPT-Controlled PC / Co-Protagonist references:** Set Primary reference to `campaigns/campaign-1/art/Seren.png`. Other verified references: none. Transfer the provenance, canonical matches, inspiration-only details, and inaccuracies/limits from this intake.
- Retain the log's authority text and its other sections. These portraits create no NPC, location, or separate equipment-reference record.

### `character_sheet.md`

Pending reference-status consistency corrections only, in the same eventual approved save; no underlying textual appearance change.

- Cutlor, Appearance — replace `- **Reference art:** None established; no generated portrait or repository image path is claimed` with `- **Reference art:** See [Art Continuity Log](art/art_log.md) for verified visual references, their form scope, and continuity notes. This section remains the textual appearance authority.`
- Seren, Appearance — replace `- **Reference art:** None established; no generated image or repository art path exists for this build` with `- **Reference art:** See [Art Continuity Log](art/art_log.md) for verified visual references and continuity notes. This section remains the textual appearance authority.`

Permanent transfers remain pending the normal Campaign Turn Final Review and player save confirmation. This intake neither requests nor records save/reset approval and does not increment the completed save revision.

## Final Turn Review

- **Status:**
- **Campaign Turn Start Clock:**
- **Proposed End Clock:**
- **Total Elapsed Time:**
- **Material Time Changes:**
- **Scheduled Events / Deadlines Reached or Crossed:**
- **Final Turn State:**
- **Exact Planned Permanent Transfers:**
- **Player save confirmation:**

## Permanent Save Verification

- **Status:**
- **Completed save revision:**
- **Verified completed clock:**
- **Verification notes:**

## Reset Approval

- **Status:**
- **Player reset confirmation:**
