# Turn Save

This file is the temporary authoritative ledger for the current unfinished **Campaign Turn**.

When this skeleton is copied into a numbered campaign, keep its explanatory text and labeled templates as fill-out guidance. A template is documentation, not an event, roll, transaction, or canonical state record.

`../Rule/CAMPAIGN_TURNS_AND_STEPS.md` governs Campaign Turn operation. `../Rule/CORE_GAME_MECHANICS.md` governs campaign time. `../Rule/REPRODUCTION_AND_LINEAGE.md` governs reproductive checks and lifecycle events. `../Rule/SAVES_VERIFICATION_AND_RECOVERY.md` governs final review, reconciliation, verification, recovery, and reset.

The effective state during an unfinished Turn is the last completed permanent state at `Base save revision` plus this ledger's overlay.

## Active Campaign Turn

- **Campaign Turn:**
- **Status:**
- **Current Step:**
- **Current Scene:**
- **Base save revision:**

## Campaign Clock

- **Start Clock:**
- **Current In-Turn Clock:**
- **Total Elapsed This Turn:**

### Time Changes

Record each material time change in order:

```text
- Step N: Start clock -> End clock; elapsed duration; activity or reason; scheduled events reached or crossed
```

Do not advance time for out-of-fiction discussion. Do not silently skip an appointment, deadline, effect expiration, biological milestone, laying date, hatching date, or other scheduled event crossed by a time jump.

## Turn Events

Record numbered Steps, player decisions, rolls and results, narration with recovery value, scene changes, mechanical outcomes, and state deltas.

## Current In-Turn State

Maintain a compact current overlay needed to continue or recover the Turn. Do not copy every permanent file here.

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
