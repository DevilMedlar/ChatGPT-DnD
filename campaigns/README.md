# Campaigns

Each numbered campaign lives in its own folder and keeps its own **canon and mutable state**. Shared numbered-campaign operating rules live here in `GAME_MASTER_RULES.md` so future campaigns do not need another full copy of the persistence architecture.

Repository-wide gameplay rules live one level above in `../GAME_MASTER_RULES.md`.

## Shared rule inheritance

Every numbered campaign inherits:

1. `../GAME_MASTER_RULES.md` — repository-wide gameplay rules
2. `GAME_MASTER_RULES.md` — shared numbered-campaign persistence and ownership rules
3. an optional local `campaign-N/GAME_MASTER_RULES.md` — campaign-specific canon, exceptions, or overrides only

A local campaign rule file must not duplicate the shared rulebooks merely for convenience.

## Active campaign

`active_campaign.json` is a pointer only. It identifies which numbered campaign is currently active and the path to that campaign's `active_game.json`.

Live gameplay state does **not** belong in `active_campaign.json`. Campaign phase, session, completed Campaign Turn, completed/pre-game scene name, location, character-creation status, completed PC advancement state, save revision, and the latest synchronization note belong in the active campaign's own `active_game.json`. The current unfinished Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

Campaign saves are isolated by folder:

- Campaign 1 saves to `campaign-1/` and uses `campaign-1/active_game.json`.
- Campaign 2 saves to `campaign-2/` and uses `campaign-2/active_game.json`.
- Campaign 3 saves to `campaign-3/` and uses `campaign-3/active_game.json`.
- Continue the same pattern for later campaigns.

Changing campaigns changes the pointer in `active_campaign.json`; it does not move, merge, or copy campaign state.

## Campaign-local identity

Each campaign assigns persistent NPCs stable campaign-local IDs such as `NPC-0001` in its own `NPC-state.md`. NPC IDs are never reused within that campaign, and cross-file references use the stable NPC ID plus the NPC's current name instead of relying on name-derived Markdown headings or anchors.

Detailed NPC ownership, party-membership reconciliation, vendor state, and cross-file behavior are defined in this directory's `GAME_MASTER_RULES.md`.

## Campaign Turn staging

Each campaign owns its own `turn_save.md`.

A **Campaign Turn** is the campaign persistence/gameplay unit. It may contain any number of Steps, including conversation, exploration, multiple combat rounds, and individual combatant turns. A combatant ending its D&D turn, a combat round ending, or combat itself ending does not automatically finish the Campaign Turn.

`active_game.json` owns the campaign's broad lifecycle phase and represents the campaign's last completed save. `turn_save.md` stages the current unfinished Campaign Turn and overlays that permanent state until the Turn is intentionally completed.

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

but only when that campaign needs local canon, exceptions, or overrides that do not belong in the shared rule layers.

## New campaign setup

When creating a new numbered campaign:

1. create the new sibling folder
2. create fresh state/template files using the shared ownership architecture
3. initialize `active_game.json` and `turn_save.md` for that campaign
4. keep its canon isolated from every existing campaign
5. create a local `GAME_MASTER_RULES.md` only if the campaign actually needs a local rule or campaign-specific canon overlay
6. change `active_campaign.json` only when the new campaign should become the active campaign

Do **not** copy the root or `campaigns/` shared rulebooks into the new campaign folder.
