# Campaign 1

Fresh adult fantasy campaign. No prior campaign canon is imported.

Campaign 1 inherits repository-wide gameplay rules from `../../GAME_MASTER_RULES.md` and shared numbered-campaign architecture from `../GAME_MASTER_RULES.md`.

`GAME_MASTER_RULES.md` in this folder is a **Campaign 1-only rules overlay**. It contains Campaign 1-specific core-PC mapping, agency, and relationship-informed behavior rules that would be wrong to impose on future campaigns. Ordinary character and relationship facts belong in `character_sheet.md`, not the local rulebook.

## Current-state routing

This README is static documentation and does not duplicate live campaign state.

- `active_game.json` owns the authoritative last completed Campaign 1 state header.
- `turn_save.md` owns the current unfinished Campaign Turn ledger and recovery status.
- `character_sheet.md` owns DevilMedlar and Senpai's established character and relationship facts.

Finalized character-creation choices use the shared confirmed character-creation checkpoint workflow in `../GAME_MASTER_RULES.md`.

## Rule conflict order

When two **rules** conflict for Campaign 1, use:

1. the player's newest explicit Campaign 1 instruction
2. this folder's `GAME_MASTER_RULES.md` local rules overlay
3. `../GAME_MASTER_RULES.md` shared campaign architecture
4. `../../GAME_MASTER_RULES.md` repository-wide gameplay rules

Campaign 1's canonical state files remain authoritative for the campaign facts and state each file owns. They are not a lower-priority rulebook.

## Canonical Campaign 1 files

- `GAME_MASTER_RULES.md` — Campaign 1-only core-PC mapping, agency, relationship-informed behavior rules, and any future Campaign 1-specific operating/mechanical overrides.
- `active_game.json` — authoritative last completed Campaign 1 state header, including completed Campaign Turn, completed/pre-game `current_scene_name`, location, character-creation completion state, completed PC Level/XP advancement state, and save revision.
- `turn_save.md` — temporary authoritative ledger for the current unfinished Campaign Turn: Campaign Turn number, Current Step, Current Scene, numbered events, current in-turn state, pending shop transactions, pending transfers, final review, permanent-save verification, and reset approval.
- `character_sheet.md` — DevilMedlar and Senpai statistics, abilities, traits, textual appearance canon, synchronized human-readable Level/XP mirrors, personal state, and established relationship continuity.
- `NPC-state.md` — persistent NPC master state and the Campaign 1 NPC record schema, including stable IDs, NPC mechanics/relationships, possessions, vendor/business state, and shop stock.
- `routine_item_prices.md` — authoritative Campaign 1 classification and recurring Base Price reference for routine/basic repeat goods.
- `inventory.md` — detailed active mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by current party NPCs, including owned-item mechanics snapshots and stack handling.
- `world_state.md` — Campaign 1 locations, factions, overall quests/missions, clues, discoveries, world consequences, player-known world secrets, unresolved threads, and lightweight NPC references.
- `session_log.md` — Campaign 1's chronological completed-save checkpoint history.
- `art/art_log.md` — Campaign 1 verified visual-reference paths and visual-reference continuity metadata. Textual appearance canon remains in the owning state files.

Shared ownership, Campaign Turn, NPC reconciliation, vendor/shop, save, recovery, fresh-start, and visual-reference staging rules are defined outside this folder in the inherited shared rulebooks.

## Campaign 1 core PCs and relationship behavior

Campaign 1's local `GAME_MASTER_RULES.md` identifies DevilMedlar as the player-controlled core PC and Senpai as the ChatGPT-controlled PC / co-protagonist. Both use PC-format state and remain together under the repository-wide core-party rule.

Their actual relationship facts are owned by `character_sheet.md`. The local rules define how established relationship continuity should influence Senpai's behavior without duplicating those facts or removing her independent agency.

## Visual continuity

Textual appearance canon belongs to `character_sheet.md`, `NPC-state.md`, `world_state.md`, or `inventory.md` according to the entity involved. `art/art_log.md` is the Campaign 1 visual-reference index. Repository-wide image behavior lives in `../../GAME_MASTER_RULES.md`; Campaign Turn staging of visual-reference metadata lives in `../GAME_MASTER_RULES.md`.
