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

The numbered campaign folder owns live campaign state and its own narrowly scoped persistent campaign-specific rules. Reusable repository-wide rules belong in `Rule/`, and reusable blank campaign skeletons belong in `New-Sheets/`.

## New-Sheets copy contract

`New-Sheets/` contains the **blank copy-ready skeletons/outlines for new campaigns**.

When creating a numbered campaign, copy each applicable `New-Sheets/` file into the corresponding location in the new campaign folder, then initialize and fill out that campaign's own copy.

The copied Markdown files intentionally retain:

- headings and state fields
- blank tables and record layouts
- clearly labeled templates for repeatable records
- inline instructions explaining how that campaign should use or fill out the file
- examples that demonstrate format or expected content
- references to the reusable rules that govern the file

The purpose of this retained guidance is to let a future ChatGPT open the campaign's own files and understand how to maintain them without having to reconstruct the sheet layout from memory.

### Guidance is not campaign state

Retained instructions, examples, placeholder values, and sections explicitly labeled `Template` are **documentation inside the campaign's copy**, not canonical campaign facts.

They do not become true merely because the file was copied.

Examples include placeholder values such as:

- `NPC-####`
- `NPC Name`
- `Item Name`
- `Service Name`
- empty example shop rows
- a labeled `Shop Transaction Template`
- other obviously instructional placeholder content

A real entity, item, shop, transaction, relationship, quest, or other campaign fact must be entered separately as actual state before it is canonical.

If copied guidance ever conflicts with the current reusable rules under `Rule/`, the current rule files control. Copied guidance is a convenience for filling out the campaign file, not an independent rule authority.

### Filling out a copied campaign sheet

For a new campaign's copied sheets:

1. preserve the useful outline, blank fields, tables, instructions, examples, and labeled reusable record templates
2. replace campaign title placeholders or generic headings with the numbered campaign's identifier where appropriate
3. replace role/name placeholders with actual established names when those names become canonical
4. fill blank state fields only when the corresponding fact is explicitly established
5. leave undecided fields blank rather than inventing values
6. add concrete repeated records using the retained labeled template as the format guide
7. never mistake the retained example/template block itself for an actual state record
8. update or remove obsolete guidance in that campaign's copy only when necessary to keep the file understandable and consistent with the current rules

### Destination-reference adjustment

Because `New-Sheets/` and `campaigns/campaign-N/` are at different directory depths, relative repository references may need to be adjusted in the copied file so they still point to the intended target from the live destination.

For example:

- a root-level campaign sheet copied from `New-Sheets/` should reference the reusable rule library from its new location under `campaigns/campaign-N/`
- `New-Sheets/art_log.md` is copied to `campaigns/campaign-N/art/art_log.md`, so its rule references must resolve correctly from the deeper `art/` directory
- state-file references inside `art/art_log.md` should resolve to the campaign's own `character_sheet.md`, `NPC-state.md`, `world_state.md`, and `inventory.md`

Adjusting a path reference for the destination is initialization of the copied skeleton, not a change to campaign canon.

### Copy map

Use this normal mapping:

```text
New-Sheets/active_game.json          -> campaigns/campaign-N/active_game.json
New-Sheets/character_sheet.md        -> campaigns/campaign-N/character_sheet.md
New-Sheets/NPC-state.md              -> campaigns/campaign-N/NPC-state.md
New-Sheets/inventory.md              -> campaigns/campaign-N/inventory.md
New-Sheets/routine_item_prices.md    -> campaigns/campaign-N/routine_item_prices.md
New-Sheets/world_state.md            -> campaigns/campaign-N/world_state.md
New-Sheets/session_log.md            -> campaigns/campaign-N/session_log.md
New-Sheets/turn_save.md              -> campaigns/campaign-N/turn_save.md
New-Sheets/art_log.md                -> campaigns/campaign-N/art/art_log.md
```

A later change to `New-Sheets/` does not automatically rewrite an existing campaign's copy. Existing campaign files remain their campaign's working records. Apply later template improvements to an existing campaign only when explicitly requested or when a required rule change makes the migration necessary, while preserving all established state.

## Revision 0: campaign setup, character creation, and backstory

`active_game.json.save_revision: 0` covers the entire pre-game setup and character-creation phase.

Revision 0 begins when the campaign is instantiated and continues while the player and ChatGPT establish the required core PCs, their identities, mechanics, appearance, backstory, relationship and family history, starting equipment and resources, and other pre-game campaign facts.

Explicitly established facts may be written to their proper state owners throughout this phase while the revision remains `0`.

Revision 0 is not a sequence of hidden or unnumbered checkpoints. It is one evolving pre-game baseline.

During revision 0:

- `campaign_turn_number` remains `0`
- `character_created` remains `false`
- `save_revision` remains `0`
- the live `turn_save.md` remains prepared for Campaign Turn 1
- `turn_save.md.Base save revision` remains `0`
- no character-creation activity creates Campaign Turn Steps
- no intermediate character-creation choice creates a completed `session_log.md` checkpoint
- no intermediate character-creation choice increments `save_revision`

Revision 0 does not authorize invention, filler, cross-campaign imports, or reconstruction from chat memory. Only explicitly established campaign facts and required initialization defaults belong there.

The detailed character-creation workflow and the final transition out of revision 0 are defined in `CHARACTER_CREATION.md`.

## New campaign setup

When creating a new numbered campaign:

1. create a new sibling folder under `campaigns/`
2. copy the blank skeleton files from `New-Sheets/` into their corresponding destinations under the new campaign using the Copy map above; retain their useful inline fill-out guidance, examples, and labeled record templates
3. adjust campaign identifiers, headings, placeholder names, and destination-relative repository references as required for the new campaign, without inventing campaign facts
4. create `Rules/Campaign-N_Rules.md` for that numbered campaign; begin with no campaign-specific rules unless the player explicitly establishes some
5. initialize the copied `active_game.json` for that campaign:
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
6. write player-established setup, character-creation, and backstory canon to its proper state owners as it becomes finalized while keeping `save_revision` at `0`
7. initialize the copied `turn_save.md` for Campaign Turn 1 with:
   - `Campaign Turn: 1`
   - `Status: ready`
   - `Current Step: 0`
   - `Current Scene: None yet.`
   - `Base save revision: 0`
   - no actual Turn Events yet
   - no actual Current In-Turn State yet
   - no actual Pending Shop Transactions yet while retaining the labeled Shop Transaction Template as fill-out guidance
   - no actual Pending Permanent Transfers yet
   - Final Turn Review `Status: not_started`, no Final Turn State or planned transfers, and `Player save confirmation: not_requested`
   - Permanent Save Verification `Status: not_started`, no completed save revision, and no verification notes
   - Reset Approval `Status: not_requested` and `Player reset confirmation: not_requested`
8. complete both required core PCs under `CORE_PARTY_AND_CHARACTER_AGENCY.md` and `CHARACTER_CREATION.md`
9. when character creation is fully complete and the player confirms the final review, establish the Campaign Turn 1 starting baseline by setting `save_revision` to `1`, `character_created` to `true`, and `turn_save.md.Base save revision` to `1`, while keeping `campaign_turn_number: 0` and `turn_save.md.Status: ready`
10. keep the new campaign's canon and campaign-specific rules isolated from every existing campaign under `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`
11. change `campaigns/active_campaign.json` only when the new campaign should become the active campaign

The new campaign begins fresh. Existing characters, NPCs, relationships, items, locations, quests, secrets, story events, campaign-specific rules, and other state are not imported unless the player explicitly requests a permitted import.

## Campaign Turn 1 baseline

The normal state immediately before Campaign Turn 1 begins is:

```text
active_game.json.campaign_turn_number = 0
active_game.json.character_created = true
active_game.json.save_revision = 1
turn_save.md.Campaign Turn = 1
turn_save.md.Status = ready
turn_save.md.Current Step = 0
turn_save.md.Base save revision = 1
```

Campaign Turn 1 begins from revision 1. The completed permanent save for Campaign Turn 1 later becomes revision 2.

## Activating another campaign

Changing the active campaign changes only the selector in `campaigns/active_campaign.json` and its pointer to that campaign's `active_game.json`.

After activation, use the newly active campaign's own `Rules/Campaign-N_Rules.md` and state files. Do not continue applying a prior campaign's local rules merely because they were active in the previous conversation.

Do not move, merge, rewrite, or copy campaign state or campaign-specific rules merely because a different campaign becomes active.
