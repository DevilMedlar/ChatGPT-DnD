# Campaign Setup, Activation, and Navigation

## Continuing an existing campaign

Before continuing play:

1. read the applicable reusable rules under `Rule/`
2. read `campaigns/active_campaign.json`
3. follow its pointer to the active numbered campaign
4. read that campaign's `Rules/Campaign-N_Rules.md` so any persistent campaign-specific overrides are applied
5. read that campaign's `active_game.json` and `turn_save.md`
6. use the `turn_save.md` status to recover, resume, review, verify, reset, or begin the next Campaign Turn correctly
7. read the other canonical state files needed for the current scene

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
Rules/
  Campaign-N_Rules.md
art/
  art_log.md
```

The numbered campaign folder owns live campaign state and its own narrowly scoped persistent campaign-specific rules. Reusable repository-wide rules belong in `Rule/`, and reusable blank sheet structure belongs in `New-Sheets/`.

## New campaign setup

When creating a new numbered campaign:

1. create a new sibling folder under `campaigns/`
2. create fresh campaign state from the blank templates in `New-Sheets/`; do not copy another campaign's populated state
3. create `Rules/Campaign-N_Rules.md` for that numbered campaign; begin with no campaign-specific rules unless the player explicitly establishes some
4. copy `New-Sheets/active_game.json` into the new campaign as `active_game.json` and initialize every field for that campaign:
   - set `campaign` to the numbered campaign folder name
   - keep `campaign_turn_number` at `0`
   - use `Character creation` as `current_scene_name` unless another explicit pre-game scene label has already been established
   - leave `current_location` blank until a location is established
   - keep `character_created` as `false`
   - use the chosen `xp_mode`; use `cumulative` by default unless the player chooses another mode
   - keep both core-PC advancement records at Level 1, 0 XP, and the applicable next-level threshold unless an explicit campaign-specific rule establishes different starting advancement
   - `PLAYER_CONTROLLED_PC_NAME` and `CHATGPT_CONTROLLED_PC_NAME` are template-only key placeholders; replace each with that core PC's actual established name as soon as the name is finalized
   - keep `save_revision` at `0`
   - use a compact initialization `last_sync_note` describing the current pre-game state
5. initialize `turn_save.md` for Campaign Turn 1 with `Status: ready`, `Current Step: 0`, `Current Scene: None yet.`, and `Base save revision: 0`
6. create both required core PCs under `CORE_PARTY_AND_CHARACTER_AGENCY.md` and `CHARACTER_CREATION.md`
7. keep the new campaign's canon and campaign-specific rules isolated from every existing campaign under `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`
8. change `campaigns/active_campaign.json` only when the new campaign should become the active campaign

The new campaign begins fresh. Existing characters, NPCs, relationships, items, locations, quests, secrets, story events, campaign-specific rules, and other state are not imported unless the player explicitly requests a permitted import.

## Activating another campaign

Changing the active campaign changes only the selector in `campaigns/active_campaign.json` and its pointer to that campaign's `active_game.json`.

After activation, use the newly active campaign's own `Rules/Campaign-N_Rules.md` and state files. Do not continue applying a prior campaign's local rules merely because they were active in the previous conversation.

Do not move, merge, rewrite, or copy campaign state or campaign-specific rules merely because a different campaign becomes active.
