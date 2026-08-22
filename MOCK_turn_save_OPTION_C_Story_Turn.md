# MOCK ONLY — Option C: Story Turn

> **NOT CAMPAIGN CANON.** This root file is only for comparing terminology before changing Campaign 1.

## What this version does

`turn_save.md` tracks one **Story Turn**, meaning a larger narrative/persistence unit that can contain multiple actions, rolls, conversations, exploration beats, combat rounds, and individual creature Combat Turns.

A **Combat Turn** is still one creature's activation. Ending a Combat Turn never ends the Story Turn.

The name feels natural in play, but it requires a clear rule for what narrative boundary counts as Story Turn completion.

## Active Story Turn

- **Story Turn:** 7
- **Status:** in_progress
- **Step:** 4
- **Base save revision:** 12

## Turn Events

### Step 1
DevilMedlar enters the ruined gatehouse.

### Step 2
Senpai examines the broken ward and discovers a clue.

### Step 3 — Combat Round 1 / DevilMedlar Combat Turn
DevilMedlar attacks.

Plain `end turn` here means **Combat Turn end** only.

### Step 4 — Combat Round 1 / Senpai Combat Turn
Senpai uses a healing item.
- HP: 11 -> 15
- Healing Potion: 2 -> 1

## Current In-Turn State

- Party location: gatehouse
- Senpai HP: 15
- Senpai Healing Potion: 1
- Combat Round 1 active

## Pending End-Turn Transfers

- character sheet: persistent HP
- inventory: potion quantity
- world state: ward clue
- session log: Story Turn summary
- active game: completed Story Turn / revision

## End Interpretation Rule

A Story Turn ends only when the gameplay flow explicitly identifies the current story unit as complete.

Examples:
- `End Story Turn`
- `Finish Story Turn`
- an explicitly defined story boundary

A creature saying or doing `end turn` during combat remains **Combat Turn end** only.

Because "story boundary" can be subjective, narration alone should not silently finalize a Story Turn unless the campaign rules clearly define that boundary.

## End-State Flow — Start to Fresh Reset

```text
[READY / FRESH]
Story Turn 7 ready
Step: 0
Base revision: 12
        |
        v
[START STORY TURN]
Status -> in_progress
        |
        v
[ROLEPLAY / EXPLORATION / COMBAT STEPS]
        |
        v
[COMBAT TURN ENDS]
"end turn" -> COMBAT TURN END
Story Turn remains in_progress
        |
        v
[MORE STORY STEPS]
        |
        v
[STORY END SIGNAL]
"End Story Turn" or defined story boundary
        |
        v
[END INTERPRETED]
Interpretation = STORY TURN END
Status -> ending / frozen
NO RESET YET
        |
        v
[RECONCILE]
transfer persistent changes
        |
        v
[WRITE HISTORY]
append completed Story Turn summary
        |
        v
[COMPLETE LIVE SAVE]
save_revision: 12 -> 13
        |
        v
[VERIFY]
all required changes landed
        |
        v
[RESET ALLOWED]
clear old temporary state
        |
        v
[READY / FRESH]
Story Turn 8 ready
Step: 0
Base revision: 13
```

**Critical boundary:** `END INTERPRETED` must happen before reconciliation and reset. The main risk with this naming option is deciding exactly what counts as a story boundary.