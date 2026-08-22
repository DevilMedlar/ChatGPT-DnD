# MOCK ONLY — Option A: Campaign Turn

> **NOT CAMPAIGN CANON.** This root file is only for comparing terminology before changing Campaign 1.

## What this version does

`turn_save.md` tracks one **Campaign Turn**, meaning the large persistence/gameplay unit that may contain conversation, exploration, rolls, combat rounds, individual creature combat turns, movement, item use, and multiple resolved steps.

A **Combat Turn** is only one creature's activation inside combat. Ending a Combat Turn never ends the Campaign Turn.

Only an explicitly interpreted **end of Campaign Turn** begins permanent reconciliation and eventually resets this file.

## Active Campaign Turn

- **Campaign Turn:** 7
- **Status:** in_progress
- **Step:** 4
- **Base save revision:** 12

## Turn Events

### Step 1
Actor: DevilMedlar
Action: Entered the ruined gatehouse.
Result:
- Position changed to gatehouse entry.
- No permanent files changed yet.

### Step 2
Actor: Senpai
Action: Examined the broken ward.
Result:
- New clue discovered.
- Pending transfer: `world_state.md` if still relevant at Campaign Turn end.

### Step 3 — Combat Round 1 / DevilMedlar Combat Turn
Action: DevilMedlar attacked.
Result:
- Enemy HP changed in-turn.

`End turn` spoken here means **end DevilMedlar's Combat Turn only** because combat context is active. Campaign Turn 7 continues.

### Step 4 — Combat Round 1 / Senpai Combat Turn
Action: Senpai used a healing item.
Result:
- Senpai HP: 11 -> 15
- Healing Potion: 2 -> 1

## Current In-Turn State

- DevilMedlar: inside gatehouse
- Senpai HP: 15
- Senpai Healing Potion: 1
- Combat: Round 1 in progress

## Pending End-Turn Transfers

- `character_sheet.md`: Senpai HP if still persistent at Campaign Turn end
- `inventory.md`: Senpai Healing Potion -> 1
- `world_state.md`: discovered ward clue
- `session_log.md`: completed Campaign Turn summary
- `active_game.json`: completed Campaign Turn number / scene / revision

## End Interpretation Rule

The persistence save begins only when the gameplay flow explicitly means **end Campaign Turn**, for example:

- `End Campaign Turn`
- `Finish Campaign Turn`
- an established non-combat scene boundary that the rules explicitly treat as Campaign Turn completion

During combat, plain `end turn` means **end the current creature's Combat Turn**, not the Campaign Turn.

## End-State Flow — Start to Fresh Reset

```text
[READY / FRESH]
Campaign Turn 7 prepared
Status: ready
Step: 0
Base revision: 12
        |
        v
[START CAMPAIGN TURN]
Status -> in_progress
        |
        v
[STEP 1]
record event + overlay
        |
        v
[STEP 2]
record event + overlay
        |
        v
[COMBAT ROUND]
Creature Combat Turn ends
"end turn" -> interpreted as COMBAT TURN END
Campaign Turn remains in_progress
        |
        v
[MORE STEPS / ROUNDS / SCENES]
        |
        v
[END SIGNAL RECEIVED]
Example: "End Campaign Turn"
        |
        v
[END INTERPRETED]
Interpretation = CAMPAIGN TURN END
Status -> ending / frozen
NO RESET YET
NO NEW GAMEPLAY ACTIONS
        |
        v
[RECONCILE]
Transfer persistent changes to owners
character_sheet / NPC-state / inventory / world_state / art
        |
        v
[HISTORY]
Append completed Campaign Turn to session_log
        |
        v
[COMPLETE LIVE SAVE]
Update active_game
Campaign Turn 7 becomes completed
save_revision: 12 -> 13
        |
        v
[VERIFY]
Confirm every pending transfer landed
Confirm master/detail records agree
        |
        v
[RESET ALLOWED]
Only now clear old Turn Events / overlays / pending transfers
        |
        v
[READY / FRESH]
Campaign Turn 8 prepared
Status: ready
Step: 0
Base revision: 13
```

**Critical boundary:** `END INTERPRETED` happens **before** reconciliation and well before reset. A creature ending a Combat Turn never reaches that Campaign Turn end gate.