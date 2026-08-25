# Campaigns

Each numbered campaign lives in its own folder and keeps its own **canon and mutable state**. Shared numbered-campaign operating rules live here in `GAME_MASTER_RULES.md` so future campaigns do not need another full copy of the persistence architecture.

Repository-wide gameplay rules live one level above in `../GAME_MASTER_RULES.md`.

## Shared rule inheritance

Every numbered campaign inherits:

1. `../GAME_MASTER_RULES.md` — repository-wide gameplay rules, including the required two-core-PC party structure
2. `GAME_MASTER_RULES.md` — shared numbered-campaign persistence and ownership rules
3. an optional local `campaign-N/GAME_MASTER_RULES.md` — campaign-specific operating, agency, behavior, or mechanical overrides only

A local campaign rule file must not duplicate the shared rulebooks or ordinary campaign facts merely for convenience. Character, NPC, relationship, world, inventory, quest, and other state facts belong in their assigned state files.

## Active campaign

`active_campaign.json` is a pointer only. It identifies which numbered campaign is currently active and the path to that campaign's `active_game.json`.

Live gameplay state does **not** belong in `active_campaign.json`. Completed Campaign Turn, completed/pre-game scene name, location, character-creation completion state, completed PC advancement state, save revision, and the latest synchronization note belong in the active campaign's own `active_game.json`. The current unfinished Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

Campaign saves are isolated by folder:

- Campaign 1 saves to `campaign-1/` and uses `campaign-1/active_game.json`.
- Campaign 2 saves to `campaign-2/` and uses `campaign-2/active_game.json`.
- Campaign 3 saves to `campaign-3/` and uses `campaign-3/active_game.json`.
- Continue the same pattern for later campaigns.

Changing campaigns changes the pointer in `active_campaign.json`; it does not move, merge, or copy campaign state.

## Campaign-local identity

Each campaign assigns persistent NPCs stable campaign-local IDs such as `NPC-0001` in its own `NPC-state.md`. NPC IDs are never reused within that campaign, and cross-file references use the stable NPC ID plus the NPC's current name instead of relying on name-derived Markdown headings or anchors.

The two required core PCs are defined through that campaign's `character_sheet.md` and `active_game.json` advancement state under the repository-wide core-party rules. The ChatGPT-controlled core PC is a PC, not an NPC.

Detailed NPC ownership, party-membership reconciliation, vendor state, and cross-file behavior are defined in this directory's `GAME_MASTER_RULES.md`.

## Campaign Turn staging

Each campaign owns its own `turn_save.md`.

A **Campaign Turn** is the campaign persistence/gameplay unit. It may contain any number of Steps, including conversation, exploration, multiple combat rounds, and individual combatant turns. A combatant ending its D&D turn, a combat round ending, or combat itself ending does not automatically finish the Campaign Turn. ChatGPT acting as GM/DM determines when the connected full Campaign Turn has ended under the shared rules.

`active_game.json` represents the campaign's last completed permanent state header. `turn_save.md` stages the current unfinished Campaign Turn and overlays that permanent state until the Turn is intentionally completed.

The complete lifecycle, status meanings, confirmation gates, reconciliation, verification, recovery, reset rules, roll-recording format, and character-creation checkpoint workflow are owned by `GAME_MASTER_RULES.md` here rather than repeated inside every numbered campaign.

## Fresh campaigns

A newly created campaign begins only with facts written into that campaign's current files or established by the player during current play.

Do not import or reconstruct character data, NPCs, items, locations, relationships, quests, story events, secrets, or other campaign canon from another campaign, deleted material, prior chats, or repository history unless the player explicitly requests a specific import.

The detailed fresh-start and append-first preservation rules are owned by `GAME_MASTER_RULES.md`.

## Campaign structure

A normal numbered campaign should contain:

```text
README.md
active_game.json
turn_save.md
character_sheet.md
NPC-state.md
routine_item_prices.md
inventory.md
world_state.md
session_log.md
art/
  art_log.md
```

A numbered campaign may additionally contain:

```text
GAME_MASTER_RULES.md
```

but only when that campaign needs local operating, agency, behavior, or mechanical rules that do not belong in the shared rule layers.

## New campaign setup

When creating a new numbered campaign:

1. create the new sibling folder
2. create fresh state/template files using the shared ownership architecture
3. initialize `active_game.json` with `campaign_turn_number: 0`, `character_created: false`, PC advancement state for both required core PCs, and `save_revision: 0`
4. initialize `turn_save.md` prepared for Campaign Turn 1 with `Status: ready` and `Base save revision: 0`
5. create both required core PCs under the repository-wide core-party rules: one male he/him player-controlled PC and one female she/her ChatGPT-controlled PC / co-protagonist
6. keep the campaign's canon isolated from every existing campaign
7. create a local `GAME_MASTER_RULES.md` only if the campaign actually needs a local operating, agency, behavior, or mechanical override
8. change `active_campaign.json` only when the new campaign should become the active campaign

Do **not** copy the root or `campaigns/` shared rulebooks into the new campaign folder.
