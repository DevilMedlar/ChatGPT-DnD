# Campaign Setup, Activation, and Navigation

## Continuing an existing campaign

Before continuing play:

1. read the applicable rules under `Rule/`
2. read `campaigns/active_campaign.json`
3. follow its pointer to the active numbered campaign
4. read that campaign's `active_game.json` and `turn_save.md`
5. use the `turn_save.md` status to recover, resume, review, verify, reset, or begin the next Campaign Turn correctly
6. read the other canonical state files needed for the current scene

Do not rely on chat memory when the current repository state can answer the question.

## Numbered campaign structure

Each numbered campaign is a sibling folder such as `campaign-1/`, `campaign-2/`, `campaign-3/`, and so on.

A normal numbered campaign contains:

```text
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

The numbered campaign folder owns live campaign state. Reusable rules belong in `Rule/`, and reusable blank sheet structure belongs in `New-Sheets/`.

## New campaign setup

When creating a new numbered campaign:

1. create a new sibling folder under `campaigns/`
2. create fresh campaign state from the blank templates in `New-Sheets/`; do not copy another campaign's populated state
3. initialize `active_game.json` with `campaign_turn_number: 0`, `character_created: false`, the chosen `xp_mode`, completed advancement state for both required core PCs, and `save_revision: 0`
4. initialize `turn_save.md` for Campaign Turn 1 with `Status: ready`, `Current Step: 0`, `Current Scene: None yet.`, and `Base save revision: 0`
5. create both required core PCs under `CORE_PARTY_AND_CHARACTER_AGENCY.md` and `CHARACTER_CREATION.md`
6. keep the new campaign's canon isolated from every existing campaign under `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`
7. change `campaigns/active_campaign.json` only when the new campaign should become the active campaign

The new campaign begins fresh. Existing characters, NPCs, relationships, items, locations, quests, secrets, story events, and other state are not imported unless the player explicitly requests a permitted import.

## Activating another campaign

Changing the active campaign changes only the selector in `campaigns/active_campaign.json` and its pointer to that campaign's `active_game.json`.

Do not move, merge, rewrite, or copy campaign state merely because a different campaign becomes active.
