# MOCK ONLY — Option D: Game Turn

> **NOT CAMPAIGN CANON.** This root file is only for comparing terminology before changing Campaign 1.

## What this version does

`turn_save.md` tracks one **Game Turn**, meaning the large persistence/gameplay unit that can contain roleplay, exploration, rolls, combat rounds, and individual creature Combat Turns.

A **Combat Turn** is one creature's activation in combat.

This option keeps familiar game language, but `Game Turn` and `Combat Turn` are close enough that the interpretation rule must be especially strict.

## Active Game Turn

- **Game Turn:** 7
- **Status:** in_progress
- **Step:** 4
- **Base save revision:** 12

## Turn Events

### Step 1
DevilMedlar enters the ruined gatehouse.

### Step 2
Senpai discovers a broken-ward clue.

### Step 3 — Combat Round 1 / DevilMedlar Combat Turn
DevilMedlar attacks.

Plain `end turn` here means **Combat Turn end** only. Game Turn 7 continues.

### Step 4 — Combat Round 1 / Senpai Combat Turn
Senpai uses a healing item.
- HP: 11 -> 15
- Healing Potion: 2 -> 1

## Current In-Turn State

- Party: gatehouse
- Senpai HP: 15
- Senpai Healing Potion: 1
- Combat active

## Pending End-Turn Transfers

- character sheet: persistent HP
- inventory: potion quantity
- world state: ward clue
- session log: Game Turn summary
- active game: completed Game Turn / revision

## End Interpretation Rule

The larger persistence unit ends only when the signal explicitly identifies **Game Turn** completion.

Examples:
- `End Game Turn`
- `Finish Game Turn`

During combat:
- `end turn` = end current **Combat Turn**
- `end game turn` = request to end the larger persistence unit

If wording is ambiguous, do not reset or reconcile the Game Turn merely because a creature's turn ended.

## End-State Flow — Start to Fresh Reset

```text
[READY / FRESH]
Game Turn 7
Status: ready
Step: 0
Base revision: 12
        |
        v
[START GAME TURN]
Status -> in_progress
        |
        v
[STEPS]
roleplay / exploration / combat
        |
        v
[COMBAT CONTEXT]
"end turn" -> COMBAT TURN END
Game Turn remains open
        |
        v
[MORE STEPS]
        |
        v
[END SIGNAL]
"End Game Turn"
        |
        v
[END INTERPRETED]
Interpretation = GAME TURN END
Status -> ending / frozen
NO RESET YET
        |
        v
[RECONCILE]
transfer persistent state
        |
        v
[LOG]
append completed Game Turn history
        |
        v
[COMPLETE SAVE]
save_revision: 12 -> 13
        |
        v
[VERIFY]
confirm all transfers
        |
        v
[RESET ALLOWED]
clear temporary data
        |
        v
[READY / FRESH]
Game Turn 8
Status: ready
Step: 0
Base revision: 13
```

**Critical boundary:** the system must explicitly classify the end signal as **GAME TURN END** before reconciliation. Because the words `Game Turn` and `Combat Turn` are similar, this option has the highest wording-confusion risk of the four turn-based names.