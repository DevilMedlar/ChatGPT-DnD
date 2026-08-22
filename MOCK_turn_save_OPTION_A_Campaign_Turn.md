# MOCK ONLY — Option A: Campaign Turn

> **NOT CAMPAIGN CANON.** This root-level file is only a design example for deciding how Campaign 1 should define and use a full Campaign Turn. None of the people, locations, enemies, rolls, HP values, items, clues, or events below become Campaign 1 canon.

# What this version does

`turn_save.md` tracks one complete **Campaign Turn** from its start until the whole gameplay unit is intentionally completed.

A Campaign Turn may contain setup, narration, rolls, initiative, multiple combat rounds, every creature's individual combat turn, attacks, damage, healing, resources, dialogue, exploration, discoveries, loot, movement, decisions, and as many numbered Steps as needed.

A creature ending its normal D&D combat turn does **not** end the Campaign Turn.

A combat round ending does **not** end the Campaign Turn.

Combat itself ending does **not automatically** end the Campaign Turn if the same gameplay sequence continues.

All unresolved and changing state remains staged in this file until the **entire Campaign Turn** is explicitly interpreted as complete.

After the end is interpreted, the ledger freezes. The final effective state and every planned permanent transfer are reviewed and shown to the player **before any permanent campaign file is changed**.

Permanent reconciliation begins only after the player confirms that final review. After the permanent save is completed and independently verified, the player receives a completion report while the Turn 7 ledger is still intact. The ledger resets only after a separate player confirmation.

---

# Starting State

Campaign Turn 7 begins from the **current completed canonical campaign files** at the recorded base save revision.

- **Base save revision:** 12
- **Permanent save being overlaid:** Completed Campaign Turn 6
- Read starting values from their owning files as needed:
  - `active_game.json`
  - `character_sheet.md`
  - `inventory.md`
  - `NPC-state.md`
  - `world_state.md`
  - `art/art_log.md`
  - other canonical files when relevant

The starting state is **not copied into this file in full**. `turn_save.md` records the changes, rolls, results, and effective in-turn values that occur after that completed state.

---

# Turn 7

## Active Campaign Turn

- **Campaign Turn:** 7
- **Status:** in_progress
- **Current Step:** 0
- **Base save revision:** 12

---

## Roll Format Used In This Mock

Keep roll calculations on one line whenever practical:

`**Actor rolls Roll Name:** dice/results + modifiers - penalties × or ÷ other effects = **final total**`

For attacks:

`**Attack — Attack Name:** dice/results + modifiers = **total** vs AC/target = **Hit/Miss**`

For damage/healing:

`**Damage/Healing — Source:** dice/results + modifiers ×/÷ effects = **final amount**`

Preserve the actual dice expression and individual die results when useful, especially for multiple dice, advantage/disadvantage, critical hits, resistances, or other mechanics.

---

## Step 0 — Turn Setup / Combat Begins

DevilMedlar and Senpai enter the ruined courtyard. Three hostile bandits emerge from behind collapsed stonework and block the path.

### Initiative Rolls

1. **DevilMedlar rolls Initiative:** d20 17 + 2 = **19**
2. **Senpai rolls Initiative:** d20 14 + 3 = **17**
3. **Bandit A rolls Initiative:** d20 12 + 1 = **13**
4. **Bandit B rolls Initiative:** d20 9 + 1 = **10**
5. **Bandit C rolls Initiative:** d20 6 + 1 = **7**

### Combat Order

1. DevilMedlar = **19**
2. Senpai = **17**
3. Bandit A = **13**
4. Bandit B = **10**
5. Bandit C = **7**

### Result

- Combat Round 1 begins.
- Initiative order is established for this combat.
- No permanent campaign file is updated merely because combat began.
- Campaign Turn 7 remains `in_progress`.

---

## Step 1 — Combat Round 1 / DevilMedlar Combat Turn

DevilMedlar attacks Bandit A.

1. **Attack — Longsword:** d20 16 + 5 = **21** vs AC 13 = **Hit**
2. **Damage — Longsword:** 1d8 [7] + 3 = **10 slashing damage**
3. **Result:** Bandit A HP **14 -> 4/14**

DevilMedlar ends his Combat Turn. **Campaign Turn 7 continues.**

If the gameplay says `End turn` while DevilMedlar's combat activation is clearly the active context, it means **end DevilMedlar's Combat Turn only**.

No reconciliation occurs. No save revision is completed. `turn_save.md` does not reset.

---

## Step 2 — Combat Round 1 / Senpai Combat Turn

Senpai fires an arrow at Bandit A.

1. **Attack — Longbow:** d20 13 + 4 = **17** vs AC 13 = **Hit**
2. **Damage — Longbow:** 1d8 [5] + 2 = **7 piercing damage**
3. **Resource:** Senpai arrows **20 -> 19**
4. **Result:** Bandit A HP **4 -> 0/14, defeated**

Senpai ends her Combat Turn. **Campaign Turn 7 continues.**

---

## Step 3 — Combat Round 1 / Bandit A Combat Turn

Bandit A was defeated before its initiative position.

1. **Result:** Bandit A takes no action and remains defeated.

Campaign Turn 7 continues.

---

## Step 4 — Combat Round 1 / Bandit B Combat Turn

Bandit B attacks DevilMedlar.

1. **Attack — Shortsword:** d20 18 + 3 = **21** vs DevilMedlar AC = **Hit**
2. **Damage — Shortsword:** 1d6 [6] = **6 piercing damage**
3. **Result:** DevilMedlar HP **24 -> 18/24**

Bandit B ends its Combat Turn. **Campaign Turn 7 continues.**

---

## Step 5 — Combat Round 1 / Bandit C Combat Turn

Bandit C attacks Senpai.

1. **Attack — Shortsword:** d20 15 + 3 = **18** vs Senpai AC = **Hit**
2. **Damage — Shortsword:** 1d6 [4] = **4 piercing damage**
3. **Result:** Senpai HP **21 -> 17/21**

### Combat Round 1 Ends

Every active combatant has reached or passed its initiative position.

**Combat Round 1 ending does not end Campaign Turn 7.**

No unresolved combat state is pushed into permanent files. The next combat round remains inside this same Turn 7 ledger.

---

## Step 6 — Combat Round 2 Begins

The established initiative order continues:

1. DevilMedlar = **19**
2. Senpai = **17**
3. Bandit A = **13, defeated / skipped**
4. Bandit B = **10**
5. Bandit C = **7**

Campaign Turn 7 remains `in_progress`.

---

## Step 7 — Combat Round 2 / DevilMedlar Combat Turn

DevilMedlar drinks a Healing Potion.

1. **Healing — Healing Potion:** 1d8 [6] = **6 HP restored**
2. **Resource:** DevilMedlar Healing Potions **2 -> 1**
3. **Result:** DevilMedlar HP **18 -> 24/24**, capped at max HP

DevilMedlar ends his Combat Turn. **Campaign Turn 7 continues.**

---

## Step 8 — Combat Round 2 / Senpai Combat Turn

Senpai fires at Bandit B.

1. **Attack — Longbow:** d20 19 + 4 = **23** vs Bandit B AC = **Hit**
2. **Damage — Longbow:** 1d8 [8] + 2 = **10 piercing damage**
3. **Resource:** Senpai arrows **19 -> 18**
4. **Result:** Bandit B HP **14 -> 4/14**

Senpai ends her Combat Turn. **Campaign Turn 7 continues.**

---

## Step 9 — Combat Round 2 / Bandit B Combat Turn

Bandit B attacks DevilMedlar.

1. **Attack — Shortsword:** d20 7 + 3 = **10** vs DevilMedlar AC = **Miss**
2. **Result:** No HP change.

Bandit B ends its Combat Turn. **Campaign Turn 7 continues.**

---

## Step 10 — Combat Round 2 / Bandit C Combat Turn

Bandit C sees Bandit A defeated and Bandit B badly wounded, then attempts to flee through the northern archway.

1. **Result:** Bandit C changes position to fleeing toward the northern archway.

Combat Round 2 ends. **Campaign Turn 7 continues.**

---

## Step 11 — Combat Round 3 / DevilMedlar Combat Turn

DevilMedlar attacks Bandit B.

1. **Attack — Longsword:** d20 14 + 5 = **19** vs Bandit B AC = **Hit**
2. **Damage — Longsword:** 1d8 [5] + 3 = **8 slashing damage**
3. **Result:** Bandit B HP **4 -> 0/14, defeated**

DevilMedlar ends his Combat Turn. **Campaign Turn 7 continues.**

---

## Step 12 — Combat Round 3 / Senpai Combat Turn

Senpai takes a final shot at the fleeing Bandit C.

1. **Attack — Longbow:** d20 9 + 4 = **13** vs Bandit C AC = **Miss**
2. **Resource:** Senpai arrows **18 -> 17**
3. **Result:** Bandit C escapes through the northern archway.

---

## Step 13 — Combat Ends

No hostile creature remains actively fighting in the courtyard.

1. **Result:** Bandit A defeated; Bandit B defeated; Bandit C escaped.
2. **State:** Combat ends, but Campaign Turn 7 remains `in_progress`.

**Combat ending does not automatically reset `turn_save.md`.**

The party continues acting in the same gameplay sequence, so all combat results remain staged here rather than being prematurely pushed into permanent files.

---

## Step 14 — Search the Courtyard

DevilMedlar searches the defeated bandits and nearby rubble.

1. **DevilMedlar rolls Investigation:** d20 15 + 3 = **18**
2. **Result:** 12 gp, an Iron Key, a scratched symbol, and a locked cellar door are discovered.
3. **Potential transfers:** Gold **+12 gp**; Iron Key **+1**; cellar discovery; scratched-symbol clue.

These remain staged in Turn 7.

---

## Step 15 — Senpai Examines the Cellar Door

Senpai examines the lock and surrounding stonework.

1. **Senpai rolls relevant check:** d20 12 + 4 = **16**
2. **Result:** Senpai determines the Iron Key likely fits the cellar lock.

Campaign Turn 7 remains in progress.

---

## Step 16 — Party Decision / Turn Objective Completes

DevilMedlar and Senpai decide to stop at the cellar entrance before opening it.

1. **Result:** Combat is over, courtyard search is complete, loot/clues are discovered, Bandit C escaped, and the party's immediate position becomes the cellar entrance.
2. **Turn state:** The gameplay flow now determines that the **full Campaign Turn 7** is ready to end.

Nothing resets yet.

---

# Current In-Turn State

This section is maintained as the compact latest effective state needed to continue or recover Turn 7. It is **not** repeated in full after every Step.

- **DevilMedlar HP:** 24/24
- **Senpai HP:** 17/21
- **DevilMedlar Healing Potions:** 1
- **Senpai Arrows:** 17
- **Bandit A:** defeated
- **Bandit B:** defeated
- **Bandit C:** escaped through northern archway
- **Acquired / discovered:** +12 gp, Iron Key +1, locked cellar door, scratched symbol
- **Combat:** ended
- **Current immediate position:** Cellar Entrance
- **Campaign Turn:** 7, still `in_progress` until the full-turn end is interpreted

---

# Pending End-Turn Transfers

Nothing below is considered transferred merely because it appears here.

- `character_sheet.md`: persistent PC HP / conditions / other character-state changes as applicable
- `inventory.md`: Healing Potions -> 1; Senpai Arrows -> 17; +12 gp; Iron Key +1
- `NPC-state.md`: create/update persistent NPC records only if an NPC actually merits persistence
- `world_state.md`: cellar entrance discovery, scratched-symbol clue, and other world-relevant consequences
- `session_log.md`: completed Campaign Turn 7 summary after successful reconciliation
- `active_game.json`: completed Campaign Turn 7, final scene/location/step as appropriate, and new save revision

---

# End Signal Received

The gameplay flow explicitly reaches the end of the **whole Campaign Turn**, not merely the end of a combatant's turn or combat round.

Example:

`End Campaign Turn 7.`

---

# END INTERPRETED

Before anything is transferred or reset, the end signal is interpreted.

- **Interpretation:** END FULL CAMPAIGN TURN 7
- **Status:** `ending_review`
- **Turn ledger:** frozen
- **New gameplay actions allowed:** No
- **Permanent file changes allowed:** No
- **Reset allowed:** No

A plain `End turn` during an active creature's combat activation would have meant **end that creature's Combat Turn** and would never have reached this Campaign Turn end state.

At this point, the `Current In-Turn State` stops being a moving snapshot. It becomes the proposed **Final Turn State — Awaiting Confirmation**.

---

# Final Turn Review — Awaiting Player Confirmation

Before any permanent transfer begins, review **all Steps 0-16** and verify that the final state below is 100% consistent with the recorded rolls, actions, damage, healing, resource use, discoveries, movement, and results.

If anything is missing, contradictory, unresolved, or uncertain, stop here and correct the temporary Turn 7 record first.

## Final Turn State

- **DevilMedlar HP:** 24/24
- **Senpai HP:** 17/21
- **DevilMedlar Healing Potions:** 1
- **Senpai Arrows:** 17
- **Bandit A:** defeated
- **Bandit B:** defeated
- **Bandit C:** escaped through northern archway
- **Acquired / discovered:** +12 gp, Iron Key +1, locked cellar door, scratched symbol
- **Combat:** ended
- **Final immediate position:** Cellar Entrance

## Exact Planned Permanent Transfers

- `character_sheet.md`: persistent PC HP / conditions / other character-state changes that actually belong there
- `inventory.md`: Healing Potions -> 1; Senpai Arrows -> 17; +12 gp; Iron Key +1
- `NPC-state.md`: create/update persistent NPC records only if an NPC actually merits persistence
- `world_state.md`: cellar entrance discovery, scratched-symbol clue, and other world-relevant consequences
- `session_log.md`: append the completed Campaign Turn 7 summary
- `active_game.json`: completed Campaign Turn 7, final scene/location/step as appropriate, `save_revision` 12 -> 13, and sync note

## Confirmation Gate 1 — Save Approval

Show the player the **Final Turn State** and **Exact Planned Permanent Transfers** above and ask:

`Confirm Campaign Turn 7 save? Yes / No / Corrections`

### If the player says No

- Keep `Status: ending_review`.
- Do not change permanent campaign files.
- Do not reset this ledger.

### If the player gives corrections

1. Correct the temporary Turn 7 events/state first.
2. Recalculate the Final Turn State.
3. Recalculate the Exact Planned Permanent Transfers.
4. Show the revised review again.
5. Ask for save confirmation again.

### If the player says Yes

- Record that the final Turn 7 state was approved.
- Set **Status:** `reconciling`.
- Begin permanent reconciliation.

---

# End-Turn Reconciliation

**This section begins only after Confirmation Gate 1 is approved.**

1. Transfer the approved persistent and continuity-relevant changes to their owning permanent files.
2. Do not transfer temporary details that no longer matter.
3. Synchronize master/detail representations when one fact exists in more than one required bookkeeping location.
4. Append the completed Turn 7 checkpoint to `session_log.md`.
5. Update supporting permanent files first when writes must be sequential.
6. Update `active_game.json` last as the completed-state marker.
7. Increment `save_revision` exactly once: **12 -> 13**.
8. Do **not** reset `turn_save.md` yet.

---

# COMPLETE LIVE SAVE

When the permanent writes have landed, Campaign Turn 7 is provisionally saved, but the temporary ledger remains intact.

- **Completed Campaign Turn:** 7
- **New save revision:** 13
- **Temporary Turn 7 ledger:** retained
- **Reset allowed:** Not yet

The permanent save must now be independently verified against the approved Final Turn State and Exact Planned Permanent Transfers.

---

# Permanent Save Verification

Read/check the affected permanent files again rather than assuming the writes succeeded.

Verify:

- expected character-state changes landed correctly
- expected inventory/resource changes landed correctly
- required NPC master/detail records agree when applicable
- required world/clue changes landed correctly
- `session_log.md` contains the completed Turn 7 checkpoint
- `active_game.json` represents completed Campaign Turn 7
- `save_revision` is exactly **13**, advanced exactly once
- every approved planned transfer is accounted for
- no unrelated campaign state was changed
- no unresolved Turn 7 state remains stranded only in the temporary ledger

If any verification fails:

- keep the Turn 7 ledger intact
- do not request reset
- reconcile the permanent state until it matches the approved final state

When every verification passes:

- set **Status:** `saved_awaiting_reset`
- send the player a save-completion report

---

# Save Completion Report

Example report shown to the player:

> **Campaign Turn 7 save complete and verified.**
>
> - Campaign Turn saved: 7
> - Save revision: 13
> - Final location: Cellar Entrance
> - All approved permanent transfers verified
> - No unrelated state changes found
> - `turn_save.md` has **NOT** been reset and still contains the complete Turn 7 safety ledger
>
> **Confirm reset for Campaign Turn 8? Yes / No**

---

# Confirmation Gate 2 — Reset Approval

The successful permanent save does **not** automatically destroy the temporary Turn 7 ledger.

### If the player says No

- Keep **Status:** `saved_awaiting_reset`.
- Keep Turn 7 events, Final Turn State, planned transfers, and verification information intact.
- Do not replay or resave Turn 7 because its permanent save is already complete.

### If the player says Yes

- Reset is authorized.
- Clear the completed Turn 7 temporary events, overlays, pending transfers, final review, and verification state.
- Prepare the next Campaign Turn from the newly completed permanent save.

---

# Fresh State After Confirmed Reset

## Active Campaign Turn

- **Campaign Turn:** 8
- **Status:** ready
- **Current Step:** 0
- **Base save revision:** 13

## Turn Events

None yet.

## Current In-Turn State

None yet.

## Pending End-Turn Transfers

None yet.

## End-Turn Verification

- **Status:** not_started
- **Notes:** None

---

# Recovery Meaning of Status

The temporary ledger status tells exactly where recovery should resume:

- `ready` — no unfinished Campaign Turn exists
- `in_progress` — Campaign Turn is actively being played; resume from completed permanent state + this ledger overlay
- `ending_review` — full-turn end was interpreted; ledger is frozen; **nothing permanent should be written until player save confirmation**
- `reconciling` — player approved the final state; permanent save may be partly written; verify/reconcile before doing anything else
- `saved_awaiting_reset` — permanent Turn 7 save is complete and verified; **do not replay or resave it**; only reset confirmation remains

---

# Full Flow Summary

```text
[CURRENT COMPLETED CAMPAIGN FILES]
Read starting state from owning files
Base save revision 12
        |
        v
[CAMPAIGN TURN 7 STARTS]
Status -> in_progress
        |
        v
[STEP 0]
setup / rolls / initiative
        |
        v
[STEP 1...]
combatant actions, rolls, damage, resources, results
        |
        v
[COMBAT TURN ENDS]
only that creature's combat activation ends
Campaign Turn 7 continues
        |
        v
[COMBAT ROUND ENDS]
Campaign Turn 7 continues
        |
        v
[MORE COMBAT ROUNDS]
same Turn 7 ledger
        |
        v
[COMBAT ENDS]
Campaign Turn 7 can still continue
NO permanent mid-combat dump
NO reset
        |
        v
[POST-COMBAT STEPS]
search / dialogue / movement / loot / clues / decisions
        |
        v
[FULL CAMPAIGN TURN END SIGNAL]
        |
        v
[END INTERPRETED]
Interpretation = END CAMPAIGN TURN 7
Status -> ending_review
TURN FROZEN
NO PERMANENT WRITES
NO RESET
        |
        v
[FINAL TURN REVIEW]
verify Current In-Turn State against all Steps
freeze it as Final Turn State
verify Pending End-Turn Transfers
        |
        v
[SHOW PLAYER]
exact Final Turn State
+
exact Planned Permanent Transfers
        |
        v
[CONFIRMATION GATE 1]
Confirm save? Yes / No / Corrections
        |
        +---- No / Corrections ----> remain ending_review
        |                            fix temp ledger / review again
        v
       Yes
        |
        v
[RECONCILE]
Status -> reconciling
transfer approved persistent results to owning files
        |
        v
[HISTORY]
append completed Turn 7 to session_log
        |
        v
[COMPLETE LIVE SAVE]
active_game -> completed Turn 7
save_revision 12 -> 13
TURN 7 LEDGER STILL INTACT
        |
        v
[VERIFY PERMANENT SAVE]
read/check affected permanent files
confirm exact approved state landed
confirm no unrelated state changed
        |
        v
[SAVE VERIFIED]
Status -> saved_awaiting_reset
        |
        v
[SEND COMPLETION REPORT]
Permanent save complete
Turn 7 temp ledger NOT reset
        |
        v
[CONFIRMATION GATE 2]
Confirm reset? Yes / No
        |
        +---- No ----> keep saved_awaiting_reset
        |             do NOT replay/resave Turn 7
        v
       Yes
        |
        v
[RESET TEMP LEDGER]
clear completed Turn 7 temporary data
        |
        v
[FRESH TURN 8]
Status: ready
Step: 0
Base save revision: 13
```

**Critical rules demonstrated by this mock:**

1. A full Campaign Turn can contain the entire combat, multiple combat rounds, every combatant's turns, and post-combat actions.
2. `turn_save.md` does not reset in the middle of that sequence and does not prematurely push unresolved state into permanent campaign files.
3. After the full Campaign Turn ends, the final effective state and planned permanent transfers must be verified and shown to the player before any permanent write.
4. Permanent reconciliation requires explicit player confirmation.
5. After the permanent save is completed, the affected files are checked again against the approved final state.
6. A verified permanent save does not erase its temporary source ledger until the player separately confirms the reset.