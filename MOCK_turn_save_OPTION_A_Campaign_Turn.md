# MOCK ONLY — Option A: Campaign Turn

> **NOT CAMPAIGN CANON.** This root-level file is only a design example for deciding how Campaign 1 should define and use a full Campaign Turn. None of the people, locations, enemies, rolls, HP values, items, clues, or events below become Campaign 1 canon.

# What this version does

`turn_save.md` tracks one complete **Campaign Turn** from its start until the whole gameplay unit is intentionally completed.

A Campaign Turn may contain setup, narration, rolls, initiative, multiple combat rounds, every creature's individual combat turn, attacks, damage, healing, resources, dialogue, exploration, discoveries, loot, movement, decisions, and as many numbered Steps as needed.

A creature ending its normal D&D combat turn does **not** end the Campaign Turn.

A combat round ending does **not** end the Campaign Turn.

Combat itself ending does **not automatically** end the Campaign Turn if the same gameplay sequence continues.

All unresolved and changing state remains staged in this file until the **entire Campaign Turn** is explicitly interpreted as complete.

Only after that interpretation does the ledger freeze, reconcile persistent results into the real campaign files, complete the save revision, verify the transfer, and finally reset fresh for the next Campaign Turn.

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

Before anything is reset, the end signal is interpreted.

- **Interpretation:** END FULL CAMPAIGN TURN 7
- **Status:** ending / frozen
- **New gameplay actions allowed:** No
- **Reset allowed:** No
- **Permanent reconciliation begun:** Yes

This is the critical gate.

A plain `End turn` during an active creature's combat activation would have meant **end that creature's Combat Turn** and would never have reached this Campaign Turn end state.

---

# End-Turn Reconciliation

Review **all Steps 0-16**, the Current In-Turn State, and Pending End-Turn Transfers.

1. Determine which changes are persistent, continuity-relevant, or historically important.
2. Update the proper owning permanent files.
3. Do not transfer temporary details that no longer matter.
4. Do not push unresolved mid-combat state into permanent files because no mid-combat reset occurred.
5. Append the completed Turn 7 checkpoint to `session_log.md`.
6. Prepare `active_game.json` as the final completed-state marker.
7. Increment `save_revision` exactly once: **12 -> 13**.

---

# End-Turn Verification

Before reset, verify:

- required character-state changes landed
- required inventory/resource changes landed
- required NPC master/detail records agree when applicable
- required world/clue changes landed
- completed Turn 7 was appended to session history
- `active_game.json` represents the completed Turn 7 state
- `save_revision` advanced exactly once
- no unresolved Turn 7 state remains stranded only in this ledger

If verification fails, **do not reset**.

---

# Reset Allowed

Only after reconciliation and verification succeed may the old Turn 7 events, overlay state, and pending transfers be cleared.

The reset itself does not erase completed history because the relevant persistent results have already been transferred and the completed-turn summary has already been appended.

---

# Fresh State After Successful Reset

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
Status -> ending / frozen
NO RESET YET
        |
        v
[RECONCILE]
transfer persistent results to owning files
        |
        v
[HISTORY]
append completed Turn 7 to session_log
        |
        v
[COMPLETE LIVE SAVE]
active_game -> completed Turn 7
save_revision 12 -> 13
        |
        v
[VERIFY]
all required transfers landed
        |
        v
[RESET ALLOWED]
        |
        v
[FRESH TURN 8]
Status: ready
Step: 0
Base save revision: 13
```

**Critical rule demonstrated by this mock:** a full Campaign Turn can contain the entire combat, multiple combat rounds, every combatant's turns, and post-combat actions. `turn_save.md` does not reset in the middle of that sequence and does not prematurely push unresolved state into the permanent campaign files.