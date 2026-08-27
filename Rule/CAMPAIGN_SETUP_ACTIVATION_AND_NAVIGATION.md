# Campaign Setup, Activation, and Navigation

## Continuing an existing campaign

Before continuing play:

1. read the applicable reusable rules under `Rule/`
2. read `campaigns/active_campaign.json`
3. follow its pointer to the active numbered campaign
4. read the campaign's `Rules/Campaign-N_Rules.md`
5. read `active_game.json` and `turn_save.md`
6. compare revision and campaign-clock state
7. recover, resume, review, reconcile, verify, reset, or begin according to ledger Status
8. read every other state owner required for the current scene

Do not rely on chat memory when the repository can answer the question.

## Numbered campaign structure

A normal campaign folder contains:

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

Reusable rules belong in `Rule/`. The blank copy-ready skeleton belongs in `New-Sheets/`.

## New-Sheets copy contract

Copy the complete `New-Sheets/` structure into a new numbered campaign while preserving subfolders and retained guidance.

Normal mapping:

```text
New-Sheets/active_game.json                    -> campaigns/campaign-N/active_game.json
New-Sheets/turn_save.md                        -> campaigns/campaign-N/turn_save.md
New-Sheets/character_sheet.md                  -> campaigns/campaign-N/character_sheet.md
New-Sheets/NPC-state.md                        -> campaigns/campaign-N/NPC-state.md
New-Sheets/routine_item_prices.md              -> campaigns/campaign-N/routine_item_prices.md
New-Sheets/inventory.md                        -> campaigns/campaign-N/inventory.md
New-Sheets/world_state.md                      -> campaigns/campaign-N/world_state.md
New-Sheets/session_log.md                      -> campaigns/campaign-N/session_log.md
New-Sheets/Rules/Campaign-N_Rules.md           -> campaigns/campaign-N/Rules/Campaign-N_Rules.md
New-Sheets/art/art_log.md                       -> campaigns/campaign-N/art/art_log.md
```

`Campaign-N_Rules.md` is a filename template. Replace `N` with the actual campaign number.

## Guidance is not state

Copied headings, empty tables, examples, placeholders, and labeled templates remain documentation until actual state is filled in.

Examples include:

- `NPC-####`
- empty shop rows
- Conception Check Template
- Shop Transaction Template
- `PLAYER_CONTROLLED_PC_NAME`
- `CHATGPT_CONTROLLED_PC_NAME`

If copied guidance conflicts with the current reusable rules, the current rules win.

A later template improvement does not automatically rewrite an existing campaign. Migrate it only when explicitly requested or when a required rule change makes migration necessary, preserving established state.

## Destination-reference adjustment

Adjust relative references, campaign-number placeholders, names, and headings for the copied destination without changing the folder structure or inventing canon.

This is initialization, not gameplay state.

# Revision 0: pre-game setup

Revision 0 covers the entire pre-game setup, character creation, backstory, starting relationships, equipment, and other starting facts.

During revision 0:

- `campaign_turn_number` remains `0`
- `character_created` remains `false`
- `save_revision` remains `0`
- `current_scene_name` remains `Character creation`
- `current_location` may remain blank
- the campaign clock remains at its initialized value unless an explicit pre-game canon correction changes the planned opening value
- out-of-fiction design discussion does not advance time
- `turn_save.md` remains ready for Campaign Turn 1
- no gameplay Step or intermediate session-log checkpoint is created

Finalized facts may be written directly to proper state owners under `CHARACTER_CREATION.md`.

# Creating a new numbered campaign

1. Create the next sibling folder under `campaigns/`.
2. Copy the complete `New-Sheets/` skeleton.
3. Preserve its `Rules/` and `art/` subfolders.
4. Adjust identifiers, paths, headings, and placeholders.
5. Initialize the copied local-rule file with no active campaign-specific rules unless the player establishes some.
6. Initialize `active_game.json`:

```json
{
  "campaign": "campaign-N",
  "campaign_turn_number": 0,
  "current_scene_name": "Character creation",
  "current_location": "",
  "campaign_clock": {
    "calendar": "Campaign Day",
    "day": 1,
    "time": "08:00:00"
  },
  "character_created": false,
  "xp_mode": "cumulative",
  "character_advancement": {
    "PLAYER_CONTROLLED_PC_NAME": {
      "level": 1,
      "xp_current": 0,
      "xp_next_level": 300
    },
    "CHATGPT_CONTROLLED_PC_NAME": {
      "level": 1,
      "xp_current": 0,
      "xp_next_level": 300
    }
  },
  "save_revision": 0,
  "last_sync_note": "Campaign initialized. Character creation is in progress."
}
```

7. Replace the advancement placeholder keys with actual PC names as soon as those names become canonical.
8. Use cumulative XP by default unless the player establishes another mode.
9. Initialize `turn_save.md`:

```text
Campaign Turn: 1
Status: ready
Current Step: 0
Current Scene: None yet.
Base save revision: 0
Start Clock: Campaign Day 1, 08:00:00
Current In-Turn Clock: Campaign Day 1, 08:00:00
Total Elapsed This Turn: 0 seconds
```

10. Keep actual Turn Events, reproductive events, shop transactions, time changes, and transfers empty while preserving labeled templates.
11. Initialize `world_state.md` with no named calendar, season, schedule, quest, or world facts beyond the neutral Campaign Day bookkeeping baseline.
12. Complete the two required core PCs under `CHARACTER_CREATION.md` and `PLAYABLE_CHARACTER_OPTIONS.md`.
13. Keep all campaign canon and local rules isolated.
14. Change `campaigns/active_campaign.json` only when this campaign should become active.

The player is not required to invent a scene title, opening location, or predetermined path. ChatGPT creates GM-controlled world framing under `GM_BEHAVIOR_AND_PRIORITY.md` while preserving player agency.

# Character-creation completion and revision 1

After both core PCs are complete and the player confirms the final review:

1. synchronize character, advancement, inventory, relationship, and other starting state
2. create the GM-authored opening frame
3. establish a concise descriptive scene label
4. establish the actual opening location
5. establish the actual opening campaign day and time
6. set `active_game.json.campaign_clock` to that opening value
7. record calendar context or scheduled opening events in `world_state.md` when applicable
8. set `character_created` to `true`
9. keep `campaign_turn_number` at `0`
10. set `save_revision` to `1`
11. append one revision-1 baseline entry to `session_log.md`, including opening clock
12. keep `turn_save.md.Campaign Turn` at `1`
13. keep Status `ready` and Current Step `0`
14. set Current Scene to the opening scene label
15. set Base save revision to `1`
16. set Start Clock and Current In-Turn Clock to the opening clock
17. keep Total Elapsed This Turn at zero
18. do not create a gameplay Step merely from the transition

Whenever possible, commit the revision-1 baseline atomically. If writes are sequential, update supporting files first and `active_game.json` last, then verify.

# Campaign Turn 1 baseline

Immediately before Campaign Turn 1:

```text
active_game.json.campaign_turn_number = 0
active_game.json.character_created = true
active_game.json.save_revision = 1
active_game.json.current_scene_name = opening scene
active_game.json.current_location = opening location
active_game.json.campaign_clock = opening clock
turn_save.md.Campaign Turn = 1
turn_save.md.Status = ready
turn_save.md.Current Step = 0
turn_save.md.Current Scene = opening scene
turn_save.md.Base save revision = 1
turn_save.md.Start Clock = opening clock
turn_save.md.Current In-Turn Clock = opening clock
turn_save.md.Total Elapsed This Turn = 0 seconds
```

Campaign Turn 1 begins from revision 1. Its completed save later becomes revision 2.

# Activating another campaign

Changing active campaigns changes only `campaigns/active_campaign.json` and its pointer.

After activation, use the new campaign's own local rules, completed clock, open Turn overlay, and state. Do not continue applying another campaign's rules or clock merely because they appeared in a previous conversation.
