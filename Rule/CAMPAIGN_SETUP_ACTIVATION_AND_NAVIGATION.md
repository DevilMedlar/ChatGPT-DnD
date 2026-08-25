Future campaigns use sibling folders such as `campaign-2`, `campaign-3`, and so on. They inherit the root and `campaigns/` rulebooks automatically. A new campaign needs a local `GAME_MASTER_RULES.md` only when it has campaign-specific operating, agency, behavior, or mechanical rules that belong in an overlay.

Before continuing play:

1. read the shared rule hierarchy
2. read `campaigns/active_campaign.json`
3. follow its pointer to the active numbered campaign
4. read that campaign's local rules overlay if one exists
5. read `active_game.json` and `turn_save.md`
6. use the `turn_save.md` status to recover, resume, review, verify, reset, or begin the next Campaign Turn correctly
7. read the other canonical state files needed for the current scene

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