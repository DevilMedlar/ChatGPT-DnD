# MOCK Campaign README

> **MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file shows the proposed full shape of a campaign `README.md`.

# Mock Campaign

This is a complete example campaign structure flattened into the repository root for design review only.

## Live State Authority

`MOCK_active_game.json` is the authoritative **last completed live save**.

`MOCK_turn_save.md` is the temporary authoritative state for the **current unfinished gameplay turn**.

If the turn save is `in_progress`, use:

`last completed permanent state + MOCK_turn_save.md overlay`

as the effective current state.

## Mock File Map

- `MOCK_campaign_README.md` — this file; static campaign documentation
- `MOCK_GAME_MASTER_RULES.md` — mock campaign rules and ownership model
- `MOCK_active_game.json` — last completed session/turn/scene/location/levels/XP/save revision
- `MOCK_turn_save.md` — unfinished-turn ledger, step state, recovery, pending transfers
- `MOCK_character_sheet.md` — DevilMedlar and Senpai full PC records
- `MOCK_NPC-state.md` — all persistent NPC master records, shops, NPC possessions, relationships, quest roles
- `MOCK_inventory.md` — detailed PC inventory and expanded current-party-NPC inventory
- `MOCK_world_state.md` — locations, factions, quests, clues, consequences, NPC references
- `MOCK_session_log.md` — chronological completed-turn history
- `MOCK_art_log.md` — visual continuity

## Current Mock Situation

The last completed save is revision 12 at the end of Turn 6.

Turn 7 is currently unfinished and staged in `MOCK_turn_save.md`.

This deliberately demonstrates why the permanent files may show older HP/item quantities while `MOCK_turn_save.md` holds the effective current values.

## NPC Ownership Example

Mara Stonehand demonstrates the proposed NPC flow:

- `MOCK_world_state.md` says where Mara matters to the world and points to her NPC record.
- `MOCK_NPC-state.md` owns who Mara is, her stats, relationships, party membership, shop, personal possessions, and off-party location.
- `MOCK_inventory.md` expands Mara's carried items because she is currently in the party.
- `MOCK_turn_save.md` currently overlays Mara's HP and potion quantity during Turn 7.
- `MOCK_session_log.md` records completed historical interactions with Mara.
- `MOCK_art_log.md` records her visual continuity.

## Non-Canon Rule

Nothing in any `MOCK_*` root file is campaign canon.

These files exist only for design review and should never be imported into Campaign 1 or another campaign unless the player explicitly adopts specific material.