# Campaigns

Each campaign lives in its own numbered folder and keeps its own rules, character state, world state, inventory, session history, and art continuity.

## Active campaign

`active_campaign.json` points to the campaign currently in play and stores only a compact live pointer such as phase, session, turn, step, and XP summary.

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
saves/
  active_game.json
  character_sheet.md
  inventory.md
  world_state.md
  session_log.md
art/
  art_log.md
```

The campaign's `GAME_MASTER_RULES.md` defines its mechanics, save cadence, image workflow, adult-content boundaries, and continuity behavior.
