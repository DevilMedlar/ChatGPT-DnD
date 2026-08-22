# MOCK ONLY — Option A: Campaign Turn

> **NOT CAMPAIGN CANON.** This root-level file is only a design example for deciding how Campaign 1 should define and use a full Campaign Turn. None of the people, locations, enemies, rolls, HP values, items, clues, or events below become Campaign 1 canon.

# What this version does

`turn_save.md` tracks one complete **Campaign Turn** from its start until the whole gameplay unit is intentionally completed.

A Campaign Turn may contain:

- setup and scene narration
- requested player rolls
- initiative and combat order
- multiple combat rounds
- every creature's individual combat turn
- attacks, damage, healing, conditions, movement, item use, ammunition, charges, and other resources
- dialogue and decisions
- exploration after combat
- discoveries, clues, loot, location changes, and other consequences
- as many numbered Steps as are needed to finish the full Campaign Turn

The Campaign Turn does **not** end because one creature ends a normal D&D combat turn.

The Campaign Turn does **not** end because one combat round ends.

The Campaign Turn does **not** automatically end when combat itself ends if the same gameplay sequence continues into searching, dialogue, movement, choices, or another directly connected action.

All unresolved and changing state remains staged in this file until the **entire Campaign Turn** is explicitly interpreted as complete.

Only after that interpretation does the ledger freeze, reconcile its persistent results into the real campaign files, complete the save revision, verify the transfer, and finally reset fresh for the next Campaign Turn.

---

# Example Starting State

This example assumes the last completed permanent save is:

- **Last completed Campaign Turn:** 6
- **Save revision:** 12
- **Party location:** Ruined Courtyard Entrance
- **DevilMedlar HP:** 24/24
- **Senpai HP:** 21/21
- **DevilMedlar Healing Potions:** 2
- **Senpai Arrows:** 20

Nothing below has been transferred to the permanent campaign files yet.

---

# Turn 7

## Active Campaign Turn

- **Campaign Turn:** 7
- **Status:** in_progress
- **Current Step:** 0
- **Base save revision:** 12
- **Permanent save being overlaid:** Completed Campaign Turn 6

---

## Step 0 — Turn Setup / Combat Begins

DevilMedlar and Senpai enter the ruined courtyard. Three hostile bandits emerge from behind collapsed stonework and block the path.

### 1. Required Rolls

The player physically rolls all required dice.

#### Initiative Rolls

1. **DevilMedlar**
   - Raw initiative roll: 17
   - Modifier: +2
   - Total: 19

2. **Senpai**
   - Raw initiative roll: 14
   - Modifier: +3
   - Total: 17

3. **Bandit A**
   - Raw initiative roll: 12
   - Modifier: +1
   - Total: 13

4. **Bandit B**
   - Raw initiative roll: 9
   - Modifier: +1
   - Total: 10

5. **Bandit C**
   - Raw initiative roll: 6
   - Modifier: +1
   - Total: 7

### 2. Combat Order

1. DevilMedlar
2. Senpai
3. Bandit A
4. Bandit B
5. Bandit C

### 3. Starting Combat State

- **DevilMedlar:** 24/24 HP
- **Senpai:** 21/21 HP
- **Bandit A:** 14/14 HP
- **Bandit B:** 14/14 HP
- **Bandit C:** 14/14 HP
- **Combat Round:** 1
- **Initiative order:** established above

### Step 0 Result

Combat is now active.

No permanent campaign file is updated merely because initiative was rolled.

The initiative order and starting combat state stay in Turn 7's in-progress ledger.

---

## Step 1 — Combat Round 1 / DevilMedlar Combat Turn

DevilMedlar attacks Bandit A.

### 1. Attack Roll

1. Raw d20: 16
2. Attack modifier: +5
3. Total: 21
4. Target AC: 13
5. **Result:** Hit

### 2. Damage

1. Damage die: 7
2. Damage modifier: +3
3. Total damage: 10

### 3. Results

- Bandit A HP: **14 -> 4**
- DevilMedlar HP remains **24/24**
- Bandit A remains conscious

### 4. End of DevilMedlar's Combat Turn

If the gameplay says:

`DevilMedlar ends his turn.`

or simply:

`End turn.`

while DevilMedlar's combat activation is clearly the active context, it means:

**END DEVILMEDLAR'S COMBAT TURN ONLY.**

It does **not** mean End Campaign Turn 7.

Campaign Turn 7 remains:

- **Status:** in_progress
- **Next Step:** 2

No reconciliation occurs.

No `save_revision` increment occurs.

`turn_save.md` does not reset.

---

## Step 2 — Combat Round 1 / Senpai Combat Turn

Senpai fires an arrow at Bandit A.

### 1. Attack Roll

1. Raw d20: 13
2. Attack modifier: +4
3. Total: 17
4. Target AC: 13
5. **Result:** Hit

### 2. Damage

1. Damage die: 5
2. Damage modifier: +2
3. Total damage: 7

### 3. Resource Change

- Senpai arrows: **20 -> 19**

### 4. Results

- Bandit A HP: **4 -> 0**
- Bandit A is defeated
- Senpai HP remains **21/21**

### 5. End of Senpai's Combat Turn

Senpai's individual Combat Turn ends.

Campaign Turn 7 continues without reconciliation or reset.

---

## Step 3 — Combat Round 1 / Bandit A Combat Turn

Bandit A was defeated before its initiative position.

### Results

- Bandit A takes no action
- Bandit A remains at **0/14 HP**
- Combat proceeds to Bandit B

Campaign Turn 7 remains in progress.

---

## Step 4 — Combat Round 1 / Bandit B Combat Turn

Bandit B attacks DevilMedlar.

### 1. Attack Roll

1. Raw d20: 18
2. Attack modifier: +3
3. Total: 21
4. Result: Hit

### 2. Damage

1. Damage roll: 6
2. Total damage: 6

### 3. Results

- DevilMedlar HP: **24 -> 18**
- Bandit B remains **14/14 HP**

Bandit B ends its Combat Turn.

Campaign Turn 7 does not end.

---

## Step 5 — Combat Round 1 / Bandit C Combat Turn

Bandit C attacks Senpai.

### 1. Attack Roll

1. Raw d20: 15
2. Attack modifier: +3
3. Total: 18
4. Result: Hit

### 2. Damage

1. Damage roll: 4
2. Total damage: 4

### 3. Results

- Senpai HP: **21 -> 17**
- Bandit C remains **14/14 HP**

### 4. Combat Round 1 Ends

Every active combatant has reached or passed their initiative position.

**Combat Round 1 is complete.**

This is not the end of Campaign Turn 7.

No permanent files are updated.

No unresolved combat state is pushed into the permanent campaign files.

The next combat round remains inside this same Turn 7 ledger.

---

## Step 6 — Combat Round 2 Begins

### Initiative Order Remains

1. DevilMedlar
2. Senpai
3. Bandit A — defeated / skipped
4. Bandit B
5. Bandit C

### Effective State Entering Round 2

- DevilMedlar: **18/24 HP**
- Senpai: **17/21 HP**
- Bandit A: **0/14 HP — defeated**
- Bandit B: **14/14 HP**
- Bandit C: **14/14 HP**
- Senpai arrows: **19**

Campaign Turn 7 remains `in_progress`.

---

## Step 7 — Combat Round 2 / DevilMedlar Combat Turn

DevilMedlar drinks a Healing Potion, then uses any remaining allowed action according to the established rules.

### 1. Healing Roll

1. Healing roll: 6
2. Healing received: 6

### 2. Resource Change

- DevilMedlar Healing Potions: **2 -> 1**

### 3. HP Change

- DevilMedlar HP: **18 -> 24**
- Healing cannot exceed max HP

### 4. Results

- DevilMedlar: **24/24 HP**
- Healing Potion remaining: **1**

DevilMedlar's Combat Turn ends.

Campaign Turn 7 remains in progress.

---

## Step 8 — Combat Round 2 / Senpai Combat Turn

Senpai fires at Bandit B.

### 1. Attack Roll

1. Raw d20: 19
2. Attack modifier: +4
3. Total: 23
4. Result: Hit

### 2. Damage

1. Damage roll: 8
2. Damage modifier: +2
3. Total damage: 10

### 3. Resource Change

- Senpai arrows: **19 -> 18**

### 4. Results

- Bandit B HP: **14 -> 4**

Senpai's Combat Turn ends.

Campaign Turn 7 remains in progress.

---

## Step 9 — Combat Round 2 / Bandit B Combat Turn

Bandit B attacks DevilMedlar but misses.

### Results

- DevilMedlar remains **24/24 HP**
- Bandit B remains **4/14 HP**

Bandit B's Combat Turn ends.

Campaign Turn 7 remains in progress.

---

## Step 10 — Combat Round 2 / Bandit C Combat Turn

Bandit C sees Bandit A defeated and Bandit B badly wounded, then attempts to flee through the northern archway.

### Results

- Bandit C changes position to fleeing toward northern archway
- Bandit C remains **14/14 HP**
- Bandit C is still part of the unresolved Turn 7 state

Combat Round 2 ends.

Campaign Turn 7 continues.

---

## Step 11 — Combat Round 3 / DevilMedlar Combat Turn

DevilMedlar attacks Bandit B.

### 1. Attack Roll

1. Raw d20: 14
2. Attack modifier: +5
3. Total: 19
4. Result: Hit

### 2. Damage

1. Damage roll: 5
2. Damage modifier: +3
3. Total damage: 8

### 3. Results

- Bandit B HP: **4 -> 0**
- Bandit B is defeated

DevilMedlar's Combat Turn ends.

Campaign Turn 7 remains in progress.

---

## Step 12 — Combat Round 3 / Senpai Combat Turn

Senpai takes a final shot at the fleeing Bandit C.

### 1. Attack Roll

1. Raw d20: 9
2. Attack modifier: +4
3. Total: 13
4. Result: Miss

### 2. Resource Change

- Senpai arrows: **18 -> 17**

### 3. Results

- Bandit C remains **14/14 HP**
- Bandit C escapes through the northern archway

---

## Step 13 — Combat Ends

No hostile creature remains actively fighting in the courtyard.

### Final Combat State

- DevilMedlar: **24/24 HP**
- Senpai: **17/21 HP**
- Bandit A: **defeated**
- Bandit B: **defeated**
- Bandit C: **escaped**
- DevilMedlar Healing Potions: **1**
- Senpai arrows: **17**

### Important Rule Demonstrated Here

**Combat ending does not automatically reset `turn_save.md`.**

Campaign Turn 7 is still in progress because DevilMedlar and Senpai continue acting in the same gameplay sequence.

The combat results remain staged here.

They have not yet been written to permanent Campaign 1 files.

---

## Step 14 — Search the Courtyard

DevilMedlar searches the defeated bandits and nearby rubble.

### 1. Investigation Roll

1. Raw d20: 15
2. Modifier: +3
3. Total: 18
4. Result: Successful search

### 2. Discoveries

- 12 gp discovered
- Iron key discovered
- Scratched symbol found on the underside of a broken stone
- A locked cellar door is discovered beneath collapsed timber

### 3. Current Turn-State Changes

Potential persistent transfers now include:

- Party currency: **+12 gp**
- Inventory: **Iron Key +1**
- World discovery: locked cellar door
- World clue: scratched symbol

These remain staged in Turn 7 until the Campaign Turn ends.

---

## Step 15 — Senpai Examines the Cellar Door

Senpai examines the lock and surrounding stonework.

### 1. Check

1. Raw d20: 12
2. Relevant modifier: +4
3. Total: 16
4. Result: Senpai determines the iron key likely fits the cellar lock

### 2. Results

- The cellar entrance becomes the party's immediate point of interest
- The key has not yet been used
- No permanent file changes yet

Campaign Turn 7 remains in progress.

---

## Step 16 — Party Decision / Turn Objective Completes

DevilMedlar and Senpai decide to stop in front of the cellar entrance before opening it.

### Results

- Immediate combat is over
- The courtyard has been searched
- Loot and clues have been discovered
- The fleeing Bandit C escaped
- Party moves from the courtyard battle area to the cellar entrance
- The next gameplay sequence can begin with deciding whether and how to enter the cellar

At this point the gameplay flow determines that **Campaign Turn 7 as a complete unit is ready to end**.

Nothing resets yet.

---

# Current In-Turn State Before End

This is the effective state immediately before interpreting the end of Campaign Turn 7.

## DevilMedlar

- HP: **24/24**
- Healing Potions: **1**
- Position: Cellar Entrance

## Senpai

- HP: **17/21**
- Arrows: **17**
- Position: Cellar Entrance

## Enemies

- Bandit A: defeated
- Bandit B: defeated
- Bandit C: escaped through northern archway

## Acquired / Discovered

- Gold: **+12 gp**
- Iron Key: **+1**
- Locked cellar door discovered
- Scratched symbol discovered

## Scene

- Combat: ended
- Courtyard search: completed
- Current immediate location: Cellar Entrance

---

# Pending End-Turn Transfers

Nothing below is considered transferred merely because it appears here.

## `character_sheet.md`

- Senpai HP -> 17/21 if HP belongs in the persistent character state
- DevilMedlar HP -> 24/24 if a persistent HP update is required

## `inventory.md`

- DevilMedlar Healing Potions -> 1
- Senpai Arrows -> 17
- Party / appropriate character gold -> +12 gp
- Iron Key -> +1

## `NPC-state.md`

- Bandit C may become a persistent NPC only if the campaign determines the escaped bandit matters enough to track
- Do not automatically create a persistent NPC record for every defeated or fleeing enemy

## `world_state.md`

- Locked cellar entrance discovered
- Scratched symbol discovered if continuity-relevant
- Courtyard battle consequence if world-relevant

## `session_log.md`

Append the completed Campaign Turn 7 summary after successful reconciliation.

## `active_game.json`

After supporting files are synchronized:

- completed Campaign Turn -> 7
- current completed location -> Cellar Entrance
- completed scene / step -> appropriate final Turn 7 values
- save revision -> 13
- last sync note -> Campaign Turn 7 completed and reconciled

---

# End Signal Received

The gameplay flow now explicitly reaches:

`End Campaign Turn 7.`

This is **not yet the reset**.

This first creates an interpretation checkpoint.

---

# END INTERPRETED

- **Signal received:** End Campaign Turn 7
- **Context:** Full Campaign Turn completion
- **Interpretation:** CAMPAIGN TURN END
- **Status:** ending / frozen
- **Current Step:** 16
- **Base save revision:** 12

## What happens immediately at this point

1. No new gameplay actions may be added to Turn 7.
2. The complete Turn 7 ledger is frozen for reconciliation.
3. Nothing in `turn_save.md` is cleared yet.
4. `save_revision` is still 12 until the completed save is successfully prepared.
5. Permanent campaign files still represent the last completed save plus whatever synchronized changes are deliberately written during reconciliation.
6. If reconciliation fails, Turn 7 must remain recoverable rather than being erased.

**The file must never jump directly from `End Campaign Turn` to a fresh Turn 8.**

---

# End-Turn Reconciliation

## 1. Review the Complete Turn

Review:

- Step 0 through Step 16
- all rolls
- initiative order
- all combat rounds
- every creature's combat actions
- HP changes
- item/resource use
- ammunition
- defeated/escaped enemies
- post-combat search
- loot
- clues
- discoveries
- location change
- Current In-Turn State
- Pending End-Turn Transfers

## 2. Determine What Is Persistent

Do not transfer temporary noise merely because it occurred.

Transfer only persistent, mechanically necessary, continuity-relevant, or historically useful results.

## 3. Prepare Supporting Permanent Files

Examples for this mock sequence:

### Character state

- Senpai final HP -> 17/21
- DevilMedlar final HP -> 24/24 if a write is actually necessary

### Inventory state

- DevilMedlar Healing Potion quantity -> 1
- Senpai arrow quantity -> 17
- Gold -> +12 gp
- Iron Key -> +1

### World state

- Cellar entrance discovered
- Relevant scratched-symbol clue recorded

### NPC state

- Create/update Bandit C only if it becomes persistent enough to require a continuing NPC record

## 4. Prepare Session History

Append a compact completed Turn 7 checkpoint to `session_log.md`.

The session log does not need every attack line because this Turn Save already held the granular temporary sequence while the turn was unresolved.

## 5. Prepare Completed Live State

Prepare `active_game.json` as the **last completed save**:

- completed Campaign Turn: 7
- completed location: Cellar Entrance
- appropriate final scene / step
- save revision: **12 -> 13**
- compact synchronization note

---

# End-Turn Verification

Before reset, verify all required transfers.

- [x] Character persistent state checked
- [x] Inventory quantities checked
- [x] Consumed Healing Potion reflected
- [x] Senpai arrows reflected
- [x] Gold acquisition reflected
- [x] Iron Key acquisition reflected
- [x] World discoveries checked
- [x] Escaped Bandit C persistence decision handled
- [x] Session-log checkpoint prepared
- [x] `active_game.json` prepared as completed Turn 7
- [x] `save_revision` increments exactly once
- [x] No unresolved Turn 7 state is being discarded
- [x] Permanent master/detail records agree

### Verification Result

- **Status:** verified
- **Completed Campaign Turn:** 7
- **New save revision:** 13

Only now is reset allowed.

---

# RESET ALLOWED

The successfully reconciled and verified Turn 7 can now be cleared from the active staging sections.

This reset does **not** erase Turn 7 from campaign history:

- the important permanent results now live in their authoritative files
- the completed turn summary lives in `session_log.md`
- `active_game.json` records Campaign Turn 7 as the last completed live save
- the Git commit can preserve the completed synchronized save when repository writing is available

Now and only now can the active Turn Save return to a fresh state.

---

# Fresh State After Successful Reset

## Active Campaign Turn

- **Campaign Turn:** 8
- **Status:** ready
- **Current Step:** 0
- **Base save revision:** 13
- **Permanent save being overlaid:** Completed Campaign Turn 7

## Turn Events

None yet.

## Current In-Turn State

None yet.

## Pending End-Turn Transfers

None yet.

## End-Turn Verification

- **Status:** not_started
- **Notes:** None.

Campaign Turn 8 has not begun until the next gameplay sequence starts.

---

# Full Campaign-Turn Flow — Start to Finish

```text
[LAST COMPLETED PERMANENT SAVE]
Campaign Turn 6
save_revision: 12
        |
        v
[FRESH TURN SAVE]
Campaign Turn 7
Status: ready
Step: 0
Base revision: 12
        |
        v
[START CAMPAIGN TURN 7]
Status -> in_progress
        |
        v
[STEP 0]
scene setup
required rolls
initiative
combat order
starting state
        |
        v
[STEP 1]
DevilMedlar Combat Turn
attack / damage / results
        |
        v
[COMBAT TURN ENDS]
Campaign Turn 7 DOES NOT END
NO reconciliation
NO permanent-state push
NO reset
        |
        v
[STEP 2...5]
Senpai / enemies act
Combat Round 1 ends
        |
        v
[COMBAT ROUND ENDS]
Campaign Turn 7 DOES NOT END
NO reconciliation
NO reset
        |
        v
[STEP 6...12]
Combat Rounds 2 and 3
all actions remain inside Turn 7
        |
        v
[STEP 13]
Combat ends
        |
        v
[COMBAT ENDS]
Campaign Turn 7 STILL DOES NOT AUTOMATICALLY END
NO unresolved state pushed out
NO reset
        |
        v
[STEP 14...16]
search courtyard
discover loot/clue
examine cellar
move to cellar entrance
complete Turn 7 objective
        |
        v
[END SIGNAL RECEIVED]
"End Campaign Turn 7"
        |
        v
[END INTERPRETED]
Interpretation = FULL CAMPAIGN TURN END
Status -> ending / frozen
NO NEW GAMEPLAY ACTIONS
NO RESET YET
        |
        v
[RECONCILE COMPLETE TURN 7]
review Steps 0-16
transfer only persistent results
        |
        v
[SUPPORTING FILES]
character_sheet / inventory / NPC-state / world_state / art as needed
        |
        v
[SESSION HISTORY]
append completed Turn 7 checkpoint
        |
        v
[COMPLETE LIVE SAVE]
active_game -> Campaign Turn 7 completed
save_revision: 12 -> 13
        |
        v
[VERIFY]
all required transfers landed
no unresolved Turn 7 state lost
master/detail records agree
        |
        v
[RESET ALLOWED]
        |
        v
[FRESH TURN SAVE]
Campaign Turn 8
Status: ready
Step: 0
Base revision: 13
```

# Critical Rule Demonstrated by This Mock

A **Campaign Turn is the complete outer gameplay/save unit**.

It may contain any number of Steps, including multiple D&D combat rounds and every combatant's individual turns.

`turn_save.md` must **not** reset, finalize, increment `save_revision`, or push unresolved mid-turn state into the permanent campaign files merely because:

- a creature ends its Combat Turn
- a Combat Round ends
- combat moves into another round
- combat itself ends

All of those events can occur **inside the same Campaign Turn**.

Only when the **full Campaign Turn** is explicitly interpreted as complete does the sequence become:

`END INTERPRETED -> FREEZE -> RECONCILE -> SAVE -> VERIFY -> RESET`.

That is the boundary that protects unfinished gameplay state from being fragmented across permanent files in the middle of the turn.
