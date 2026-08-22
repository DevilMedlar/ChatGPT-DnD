# Campaigns

Each campaign lives in its own numbered folder and keeps its own rules, character state, NPC state, world state, inventory, session history, and art continuity.

## Active campaign

`active_campaign.json` is a pointer only. It identifies which numbered campaign is currently active and the path to that campaign's `active_game.json`.

Live gameplay state does **not** belong in `active_campaign.json`. Session, turn, scene, step, location, character-creation status, character levels, XP, save revision, and the latest synchronization note belong in the active campaign's own `active_game.json`.

Campaign saves are isolated by folder:

- Campaign 1 saves to `campaign-1/` and uses `campaign-1/active_game.json`.
- Campaign 2 saves to `campaign-2/` and uses `campaign-2/active_game.json`.
- Campaign 3 saves to `campaign-3/` and uses `campaign-3/active_game.json`.
- Continue the same pattern for later campaigns.

Changing campaigns changes the pointer in `active_campaign.json`; it does not move, merge, or copy campaign state.

## Folder convention

```text
campaign-1/
campaign-2/
campaign-3/
...
```

Campaigns do not share canon unless the player explicitly imports or connects something between them.

## Fresh-campaign rule

A newly created campaign begins only with facts written into that campaign's current files or established by the player during current play.

Do not import or reconstruct character data, NPCs, items, locations, relationships, quests, story events, secrets, or other campaign canon from another campaign, deleted material, prior chats, or repository history.

Repository history may be used only for reusable framework, mechanics, file structure, or operating instructions when the player explicitly requests that use. Framework recovery never makes historical campaign content canon.

## Campaign structure

Each campaign should contain:

```text
README.md
GAME_MASTER_RULES.md
active_game.json
character_sheet.md
NPC-state.md
inventory.md
world_state.md
session_log.md
art/
  art_log.md
```

The campaign's `GAME_MASTER_RULES.md` defines its mechanics, save cadence, image workflow, adult-content boundaries, file ownership, and continuity behavior.
