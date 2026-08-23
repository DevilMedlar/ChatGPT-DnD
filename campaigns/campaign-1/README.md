# Campaign 1

Fresh adult fantasy campaign. No prior campaign canon is imported.

Campaign 1 inherits repository-wide gameplay rules from `../../GAME_MASTER_RULES.md` and shared numbered-campaign architecture from `../GAME_MASTER_RULES.md`.

`GAME_MASTER_RULES.md` in this folder is a **Campaign 1-only overlay**. It contains DevilMedlar/Senpai-specific canon and agency rules that would be wrong to impose on future campaigns. It must not duplicate the shared rulebooks.

## Current Campaign 1 Phase

Campaign 1 is in character creation before Campaign Turn 1.

`active_game.json` owns the authoritative last completed Campaign 1 state. `turn_save.md` remains prepared for Campaign Turn 1 and is not used as a character-creation ledger.

Finalized character-creation choices use the shared confirmed character-creation checkpoint workflow in `../GAME_MASTER_RULES.md`.

## Rule Conflict Order

When two **rules** conflict for Campaign 1, use:

1. the player's newest explicit Campaign 1 instruction
2. this folder's `GAME_MASTER_RULES.md` local overlay
3. `../GAME_MASTER_RULES.md` shared campaign architecture
4. `../../GAME_MASTER_RULES.md` repository-wide gameplay rules

Campaign 1's canonical state files remain authoritative for the campaign facts and state each file owns. They are not a lower-priority rulebook.

## Canonical Campaign 1 Files

- `GAME_MASTER_RULES.md` — Campaign 1-only canon and overrides, currently including DevilMedlar/Senpai relationship and agency rules.
- `active_game.json` — authoritative last completed Campaign 1 live state, including completed Campaign Turn, completed/pre-game `current_scene_name`, location, character-creation status, completed PC Level/XP advancement state, and save revision.
- `turn_save.md` — temporary authoritative ledger for the current unfinished Campaign Turn: Campaign Turn number, Current Step, Current Scene, numbered events, current in-turn state, pending shop transactions, pending transfers, final review, permanent-save verification, and reset approval.
- `character_sheet.md` — DevilMedlar and Senpai statistics, abilities, traits, synchronized human-readable Level/XP mirrors, appearance, personal state, and established PC relationship continuity.
- `NPC-state.md` — persistent NPC master state and the Campaign 1 NPC record schema, including stable IDs, NPC mechanics/relationships, possessions, vendor/business state, and shop stock.
- `routine_item_prices.md` — authoritative Campaign 1 classification and recurring Base Price reference for routine/basic repeat goods.
- `inventory.md` — detailed active mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by current party NPCs, including owned-item mechanics snapshots and stack handling.
- `world_state.md` — Campaign 1 locations, factions, overall quests/missions, clues, discoveries, world consequences, player-known world secrets, and lightweight NPC references.
- `session_log.md` — Campaign 1's chronological completed-save checkpoint history.
- `art/art_log.md` — Campaign 1's visual-canon and verified reference-art metadata.

Shared ownership, Campaign Turn, NPC reconciliation, vendor/shop, save, recovery, fresh-start, and visual-staging rules are defined outside this folder in the inherited shared rulebooks.

## Campaign 1-Specific Relationship and Agency

DevilMedlar and Senpai's established relationship facts and Senpai's ChatGPT-controlled agency belong in this campaign's local `GAME_MASTER_RULES.md` and Campaign 1 state files as appropriate.

Those facts are Campaign 1 canon, not repository-wide assumptions for future campaigns.

## Visual Continuity

Campaign 1 uses `art/art_log.md` as its visual-continuity index. Repository-wide image behavior lives in `../../GAME_MASTER_RULES.md`; Campaign Turn staging of visual metadata lives in `../GAME_MASTER_RULES.md`.
