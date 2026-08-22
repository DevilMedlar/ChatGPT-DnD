# MOCK Turn Save

> **MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file shows the proposed full shape of a campaign `turn_save.md` during an unfinished turn.

# Turn Save — Mock Campaign

This file is the temporary authoritative ledger for the current unfinished gameplay turn.

The permanent mock files represent the last completed save. While this file is `in_progress`, the state below overlays them.

## Active Turn Data

- **Turn:** 7
- **Status:** in_progress
- **Step:** 4
- **Base save revision:** 12

## Turn Events

### Step 1

- **Actor:** DevilMedlar
- **Action:** Moved from the broken gate to the western barricade.
- **Roll:** None required
- **Result:**
  - Position: Broken Gate -> Western Barricade
  - No HP/resource change

### Step 2

- **Actor:** Bandit Raider
- **Action:** Struck Mara Stonehand with a shortsword.
- **Roll:** Player rolled attack and damage as required.
- **Result:**
  - Mara HP: 25 -> 20
  - Change: -5 HP
  - Mara position unchanged

### Step 3

- **Actor:** Mara Stonehand
- **Action:** Used one Healing Potion.
- **Roll:** Player rolled healing dice.
- **Result:**
  - Healing roll: +4 HP
  - Mara HP: 20 -> 24
  - Healing Potion: 2 -> 1
  - Change: -1 Healing Potion

### Step 4

- **Actor:** Senpai
- **Action:** Fired one arrow at the Bandit Raider.
- **Roll:** Player rolled attack and damage as required.
- **Result:**
  - Arrow quantity: 20 -> 19
  - Bandit Raider HP: 14 -> 8
  - Bandit Raider remains active

## Current In-Turn State

These are the latest effective values needed to continue Turn 7 correctly.

### DevilMedlar

- **HP:** 18 / 18
- **Position:** Western Barricade
- **Healing Potions:** 2
- **Conditions:** None

### Senpai

- **HP:** 16 / 16
- **Position:** Broken Gate
- **Arrows:** 19
- **Healing Potions:** 1
- **Conditions:** None

### Mara Stonehand

- **HP:** 24 / 25
- **Position:** Center Courtyard
- **Healing Potions:** 1
- **Brace uses:** 1 / 1
- **Conditions:** None

### Bandit Raider

- **HP:** 8 / 14
- **Position:** Center Courtyard
- **Conditions:** None

## Pending End-Turn Transfers

### `MOCK_character_sheet.md`

- No DevilMedlar HP change currently pending.
- No Senpai HP change currently pending.

### `MOCK_NPC-state.md`

Mara Stonehand:
- HP -> 24 / 25 if this remains her end-turn HP
- Conditions -> None

Bandit Raider:
- If the Bandit Raider becomes important/persistent, create or update an NPC record as appropriate.
- If the enemy is defeated and has no continuing relevance, permanent NPC-state entry may not be needed.

### `MOCK_inventory.md`

Mara Stonehand:
- Healing Potion -> 1

Senpai:
- Arrows -> 19

### `MOCK_world_state.md`

- None currently needed.

### `MOCK_session_log.md`

At end turn, append a concise chronological checkpoint containing only important rolls, actions, consequences, and persistent state changes.

### `MOCK_active_game.json`

At successful end-turn reconciliation:
- turn_number -> 7 completed
- next gameplay turn -> 8
- save_revision -> 13
- update current scene/location if changed
- update last_sync_note

## End-Turn Verification

- **Status:** not_started
- **Required transfers checked:** No
- **Permanent files prepared:** No
- **Session log prepared:** No
- **active_game prepared last:** No
- **Atomic commit prepared:** No
- **Ready to reset turn save:** No

## Recovery Rule

If a conversation ends now, resume Turn 7 from this file.

Do not use the older HP/item/ammunition values in permanent files as the effective current state while this file is `in_progress`.

The effective current state is:

`last completed permanent state + this turn-save overlay`.

Do not reset this file until end-turn transfer is verified and the completed save revision succeeds.