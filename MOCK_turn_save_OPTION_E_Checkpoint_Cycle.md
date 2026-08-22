# MOCK ONLY — Option E: Checkpoint Cycle

> **NOT CAMPAIGN CANON.** This root file is only for comparing terminology before changing Campaign 1.

## What this version does

This option stops calling the large persistence unit a `Turn` at all.

`turn_save.md` instead tracks one **Checkpoint Cycle**, meaning the temporary state accumulated between completed campaign save revisions. A Checkpoint Cycle may contain any number of scenes, actions, rolls, combat rounds, and creature Combat Turns.

Normal D&D terminology stays untouched:
- **Combat Round** = one initiative cycle
- **Combat Turn** = one creature's activation

The persistence layer uses **Checkpoint Cycle**, so `end turn` can only mean a Combat Turn when combat is active.

## Active Checkpoint Cycle

- **Checkpoint Cycle:** 7
- **Status:** in_progress
- **Step:** 4
- **Base save revision:** 12

## Events

### Step 1
DevilMedlar enters the ruined gatehouse.

### Step 2
Senpai discovers a broken-ward clue.

### Step 3 — Combat Round 1 / DevilMedlar Combat Turn
DevilMedlar attacks.

`End turn` here means **Combat Turn end**. It has no persistence meaning.

### Step 4 — Combat Round 1 / Senpai Combat Turn
Senpai uses a healing item.
- HP: 11 -> 15
- Healing Potion: 2 -> 1

## Current Temporary State

- Party: gatehouse
- Senpai HP: 15
- Senpai Healing Potion: 1
- Combat Round 1 active

## Pending Checkpoint Transfers

- character sheet: persistent HP
- inventory: potion quantity
- world state: ward clue
- session log: completed cycle summary
- active game: completed checkpoint / revision

## End Interpretation Rule

Because this option does not use `Turn` for persistence, a persistence save begins only when the flow explicitly means **finish/close the Checkpoint Cycle**.

Examples:
- `Complete Checkpoint`
- `Close Checkpoint Cycle`
- `Save and close checkpoint`

During combat, `end turn` always refers to the current creature's Combat Turn and cannot itself close the Checkpoint Cycle.

## End-State Flow — Start to Fresh Reset

```text
[READY / FRESH]
Checkpoint Cycle 7
Status: ready
Step: 0
Base revision: 12
        |
        v
[OPEN CHECKPOINT CYCLE]
Status -> in_progress
        |
        v
[STEP EVENTS]
roleplay / exploration / combat / resource changes
        |
        v
[COMBAT TURN ENDS]
"end turn" -> COMBAT TURN END ONLY
Checkpoint Cycle stays open
        |
        v
[MORE EVENTS]
        |
        v
[CHECKPOINT END SIGNAL]
"Complete Checkpoint"
        |
        v
[END INTERPRETED]
Interpretation = CHECKPOINT CYCLE END
Status -> ending / frozen
NO RESET YET
        |
        v
[RECONCILE]
transfer persistent state to canonical owners
        |
        v
[LOG]
append completed cycle history
        |
        v
[COMPLETE LIVE SAVE]
save_revision: 12 -> 13
        |
        v
[VERIFY]
confirm all pending transfers and synchronized records
        |
        v
[RESET ALLOWED]
clear temporary event/state data
        |
        v
[READY / FRESH]
Checkpoint Cycle 8
Status: ready
Step: 0
Base revision: 13
```

**Critical boundary:** `END INTERPRETED` is a distinct state before reconciliation and reset. This option removes the persistence/combat `turn` collision almost entirely, but the terminology is more technical and less natural for ordinary play.