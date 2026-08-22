# MOCK ONLY — Option B: Save Turn

> **NOT CAMPAIGN CANON.** This root file is only for comparing terminology before changing Campaign 1.

## What this version does

`turn_save.md` tracks one **Save Turn**, meaning the large persistence unit between completed save revisions. A Save Turn may contain roleplay, exploration, combat rounds, individual creature Combat Turns, and many resolved steps.

A **Combat Turn** remains normal D&D terminology for one creature's activation. Ending a Combat Turn never ends the Save Turn.

The advantage of this name is technical clarity: only an explicitly interpreted **Save Turn end** can begin reconciliation and reset.

## Active Save Turn

- **Save Turn:** 7
- **Status:** in_progress
- **Step:** 4
- **Base save revision:** 12

## Turn Events

### Step 1
Actor: DevilMedlar
Action: Entered the ruined gatehouse.
Result: Position changed in-turn.

### Step 2
Actor: Senpai
Action: Examined the broken ward.
Result: Clue discovered; pending `world_state.md` transfer.

### Step 3 — Combat Round 1 / DevilMedlar Combat Turn
Action: DevilMedlar attacked.
Result: Enemy HP changed in-turn.

Plain `end turn` here means the creature's **Combat Turn** ends. Save Turn 7 continues.

### Step 4 — Combat Round 1 / Senpai Combat Turn
Action: Senpai used a healing item.
Result:
- Senpai HP: 11 -> 15
- Healing Potion: 2 -> 1

## Current In-Turn State

- DevilMedlar: gatehouse entry
- Senpai HP: 15
- Senpai Healing Potion: 1
- Combat Round 1 active

## Pending End-Turn Transfers

- character sheet: persistent HP
- inventory: potion quantity
- world state: clue
- session log: completed Save Turn summary
- active game: completed Save Turn / revision

## End Interpretation Rule

Save reconciliation begins only when the input or gameplay flow explicitly means **end Save Turn**.

Examples:
- `End Save Turn`
- `Finish Save Turn`
- an explicitly defined save boundary

Plain `end turn` during combat means **Combat Turn end** only.

## End-State Flow — Start to Fresh Reset

```text
[READY / FRESH]
Save Turn 7
Status: ready
Step: 0
Base revision: 12
        |
        v
[START SAVE TURN]
Status -> in_progress
        |
        v
[STEP EVENTS]
record actions, rolls, deltas, overlays
        |
        v
[COMBAT]
"end turn" -> COMBAT TURN END
Save Turn remains open
        |
        v
[MORE EVENTS]
        |
        v
[END SIGNAL RECEIVED]
"End Save Turn"
        |
        v
[END INTERPRETED]
Interpretation = SAVE TURN END
Status -> ending / frozen
NO RESET YET
        |
        v
[RECONCILE]
write persistent changes to permanent owners
        |
        v
[SESSION HISTORY]
append completed Save Turn summary
        |
        v
[ACTIVE GAME SAVE]
save_revision: 12 -> 13
        |
        v
[VERIFY]
all transfers complete and synchronized
        |
        v
[RESET ALLOWED]
clear finished temporary turn data
        |
        v
[READY / FRESH]
Save Turn 8
Status: ready
Step: 0
Base revision: 13
```

**Critical boundary:** the file is not reset when the end signal is merely seen. First the end must be interpreted as **Save Turn end**, then reconciliation/save/verification completes, and only then is reset allowed.