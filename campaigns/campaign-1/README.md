# Campaign 1

Fresh adult fantasy campaign. No prior campaign canon is imported.

Campaign 1 inherits repository-wide gameplay rules from `../../GAME_MASTER_RULES.md` and shared numbered-campaign architecture from `../GAME_MASTER_RULES.md`.

`GAME_MASTER_RULES.md` in this folder is now a **Campaign 1-only overlay**. It contains the DevilMedlar/Senpai-specific canon and agency rules that would be wrong to impose on future campaigns. It does not duplicate the shared rulebooks.

## Current Campaign 1 phase

Campaign 1 is in character creation before Campaign Turn 1.

`active_game.json` owns the authoritative last completed Campaign 1 state. `turn_save.md` remains prepared for Campaign Turn 1 and is not used as a character-creation ledger.

Finalized character-creation choices use the shared confirmed character-creation checkpoint workflow in `../GAME_MASTER_RULES.md`.

## Rule order for Campaign 1

1. the player's newest explicit Campaign 1 instruction
2. this folder's `GAME_MASTER_RULES.md` local overlay
3. `../GAME_MASTER_RULES.md` shared campaign architecture
4. `../../GAME_MASTER_RULES.md` repository-wide gameplay rules
5. current Campaign 1 canonical state files

## Canonical Campaign 1 files

- `GAME_MASTER_RULES.md` — Campaign 1-only canon and overrides, currently including DevilMedlar/Senpai relationship and agency rules.
- `active_game.json` — authoritative last completed Campaign 1 live state, including completed Campaign Turn, completed/pre-game `current_scene_name`, location, character-creation status, completed PC Level/XP advancement state, and save revision.
- `turn_save.md` — temporary authoritative ledger for the current unfinished Campaign Turn: Campaign Turn number, Current Step, Current Scene, numbered events, current in-turn state, pending shop transactions, pending transfers, final review, permanent-save verification, and reset approval.
- `character_sheet.md` — DevilMedlar and Senpai statistics, abilities, traits, synchronized human-readable Level/XP mirrors, appearance, personal state, and established PC relationship continuity.
- `NPC-state.md` — authoritative master database for persistent NPC stable IDs, identity, appearance, stats, abilities, conditions, personality, relationship and attraction state, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, NPC knowledge/secrets, and NPC-specific continuity.
- `routine_item_prices.md` — authoritative Campaign 1 classification and recurring Base Price reference for routine/basic repeat goods. Vendor stock rows mirror these Base Prices; the file does not own quantity, mechanics, merchant modifiers, Final Price, or inventory.
- `inventory.md` — detailed active mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by current party NPCs. For NPCs, `NPC-state.md` remains the master ownership list.
- `world_state.md` — locations, factions, overall quests/missions, clues, discoveries, world consequences, player-known world secrets, and lightweight references to persistent NPCs by stable NPC ID and current name where they matter to world state.
- `session_log.md` — chronological completed character-creation checkpoint saves and completed Campaign Turn checkpoints, including the completed save revision for each checkpoint.
- `art/art_log.md` — canonical Campaign 1 visual continuity and verified reference-art notes.

## Campaign 1 ownership notes

Persistent NPC information should be referenced rather than duplicated across multiple files. Every persistent Campaign 1 NPC receives one stable ID such as `NPC-0001` in `NPC-state.md`; the ID never changes or gets reused for another NPC.

- `world_state.md` answers **where and why an NPC matters to the world**.
- `NPC-state.md` answers **who the NPC is**, owns the stable ID and persistent NPC state, and owns vendor/business state when applicable.
- `routine_item_prices.md` answers **which Campaign 1 shop goods use a campaign-wide recurring Base Price and what that Base Price currently is**.
- `inventory.md` answers **what the active party is carrying and how those items currently work**.
- Shop stock stays in the relevant NPC's `NPC-state.md` record as business inventory until a party member actually acquires an item.
- `world_state.md` owns overall quest/mission state; `NPC-state.md` owns each NPC's involvement in that quest or mission.
- `turn_save.md` temporarily overlays changing Campaign 1 state during an unfinished Campaign Turn.

The detailed ownership, NPC join/leave, vendor transaction, stack compatibility, save, and reconciliation procedures are inherited from `../GAME_MASTER_RULES.md`.

## Campaign 1-specific relationship and agency

DevilMedlar and Senpai's established relationship facts and Senpai's ChatGPT-controlled agency belong in this campaign's local `GAME_MASTER_RULES.md` and `character_sheet.md` as appropriate.

Those facts are Campaign 1 canon, not repository-wide assumptions for future campaigns.

## Fresh-start boundary

Only information currently stored in Campaign 1 or explicitly established by the player during this fresh campaign is Campaign 1 canon.

Do not import Campaign 1 content from deleted material, previous chats, memory, another campaign, or repository history unless the player explicitly requests a specific import. The complete shared fresh-start rule is in `../GAME_MASTER_RULES.md`.

## Visual continuity

Campaign 1 uses `art/art_log.md` as its visual-continuity index. Repository-wide image behavior lives in `../../GAME_MASTER_RULES.md`; Campaign Turn staging of visual metadata lives in `../GAME_MASTER_RULES.md`.
