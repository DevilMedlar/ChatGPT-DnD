# ChatGPT-DnD

A persistent, choice-driven adult fantasy tabletop RPG repository designed to be played through ChatGPT.

The repository separates **reusable rules**, **campaign-specific rules**, **blank reusable campaign skeletons**, and **live campaign state** so campaigns can remain persistent while their copied sheets still carry the guidance needed to fill them out correctly.

The intended play style uses D&D-style d20 mechanics, player-rolled dice, persistent characters and NPCs, campaign continuity, relationships, combat, quests, inventory, shops, advancement, and optional generated scene art.

All characters involved in adult content must be adults. Detailed content, consent, gameplay, persistence, and GM behavior requirements live in the categorized files under `Rule/`.

---

## Repository model

The repository has three top-level working areas, with a campaign-local rule layer inside each numbered campaign.

### `Rule/` — reusable game and persistence rules

`Rule/` is the central reusable rule library.

Rules are separated by subject instead of being repeated inside every campaign. ChatGPT should consult the relevant rule files when running or modifying a campaign.

Current rule categories include:

- adult content and consent
- advancement and XP
- campaign setup, activation, and navigation
- Campaign Turns and Steps
- canon, history, and campaign isolation
- character creation
- combat, abilities, and ongoing effects
- core game mechanics
- core-party structure and character agency
- dice rolls and rerolls
- GM behavior and priority
- images, visuals, and reference art
- inventory, equipment, and items
- NPCs and party membership
- relationships and social interactions
- reproduction and lineage
- reproductive species profiles
- rule authority and hierarchy
- saves, verification, and recovery
- session logs and history
- shops, pricing, and transactions
- state ownership and persistence
- world, quests, and continuity

These files are the reusable operating brain of the repository. A numbered campaign should not duplicate unchanged reusable rules as campaign-specific rules merely for convenience.

### `campaigns/campaign-N/Rules/` — persistent campaign-specific rules

Each numbered campaign has its own local rule layer:

```text
campaigns/campaign-N/Rules/Campaign-N_Rules.md
```

This file stores only persistent rules intentionally scoped to that campaign, such as:

- campaign-specific mechanical overrides
- campaign-specific agency or behavior rules
- exceptional campaign premises
- campaign-specific operating rules
- explicit player instructions that should remain rules for that campaign across future sessions

It is a **delta layer**, not another copy of `Rule/`.

Do not store ordinary character, NPC, relationship, inventory, world, quest, shop, session, art, or other campaign facts there. Those facts remain in their assigned state files.

Campaign-specific rules never automatically carry into another numbered campaign.

### `New-Sheets/` — blank reusable campaign skeleton

`New-Sheets/` contains the clean, campaign-neutral **copy-ready folder skeleton** used to create a fresh numbered campaign.

It intentionally mirrors the normal live campaign structure, including the `Rules/` and `art/` subfolders. Its Markdown files contain:

- blank state fields
- reusable headings and tables
- record layouts
- clearly labeled templates for repeated records
- examples
- inline guidance explaining how the campaign's copy should be filled out and maintained
- references to the reusable rules that govern the file

They contain no established character names, populated campaign state, existing NPCs, relationships, story events, or other canon from a prior campaign.

Current skeleton:

```text
New-Sheets/
  active_game.json
  character_sheet.md
  NPC-state.md
  inventory.md
  routine_item_prices.md
  world_state.md
  session_log.md
  turn_save.md
  Rules/
    Campaign-N_Rules.md
  art/
    art_log.md
```

`active_game.json` is the reusable initialization skeleton for the campaign-state header. Its core-PC advancement keys are placeholders that are replaced with actual established PC names during character creation.

`Rules/Campaign-N_Rules.md` is a campaign-local rule template. `N` is replaced with the actual numbered campaign during initialization, and the file begins with no active campaign-specific rules unless the player establishes some.

#### How New-Sheets becomes a campaign

A new campaign copies the complete `New-Sheets/` folder skeleton into its own numbered folder, preserving the `Rules/` and `art/` subfolders, then fills out **its own copies**.

Normal mapping:

```text
New-Sheets/active_game.json                    -> campaigns/campaign-N/active_game.json
New-Sheets/character_sheet.md                  -> campaigns/campaign-N/character_sheet.md
New-Sheets/NPC-state.md                        -> campaigns/campaign-N/NPC-state.md
New-Sheets/inventory.md                        -> campaigns/campaign-N/inventory.md
New-Sheets/routine_item_prices.md              -> campaigns/campaign-N/routine_item_prices.md
New-Sheets/world_state.md                      -> campaigns/campaign-N/world_state.md
New-Sheets/session_log.md                      -> campaigns/campaign-N/session_log.md
New-Sheets/turn_save.md                        -> campaigns/campaign-N/turn_save.md
New-Sheets/Rules/Campaign-N_Rules.md           -> campaigns/campaign-N/Rules/Campaign-N_Rules.md
New-Sheets/art/art_log.md                      -> campaigns/campaign-N/art/art_log.md
```

The campaign's copied Markdown files keep useful instructions, examples, blank layouts, and clearly labeled record templates so future ChatGPT sessions can see how to fill out and maintain that campaign's records.

Those retained helper sections are **not canonical state**. A labeled `NPC Record Template` is not an NPC, a labeled `Shop Transaction Template` is not a pending transaction, and placeholder names/IDs or example rows are not established campaign facts.

When copying the skeleton into its live destination, adjust campaign identifiers, placeholder character names, the `Campaign-N_Rules.md` filename/heading, starting values, and any destination-relative repository references as needed. This is initialization of the copy, not campaign canon.

If copied guidance conflicts with the current files under `Rule/`, the current reusable rule library wins. The copied guidance explains how to fill the file; it is not a separate rule authority.

Later changes to `New-Sheets/` do not automatically rewrite existing campaigns.

### `campaigns/` — live isolated campaign state

Each numbered campaign owns its own canonical state inside its own folder.

`campaigns/active_campaign.json` is the campaign selector. It identifies the campaign currently in play and points to that campaign's `active_game.json`.

Campaigns are isolated. Character data, NPCs, relationships, inventory, quests, world state, story history, secrets, campaign-specific rules, and other canon do not automatically carry from one numbered campaign into another.

---

## Current repository layout

```text
README.md
LICENSE

Rule/
  ADULT_CONTENT_AND_CONSENT.md
  ADVANCEMENT_AND_XP.md
  CAMPAIGN_SETUP_ACTIVATION_AND_NAVIGATION.md
  CAMPAIGN_TURNS_AND_STEPS.md
  CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md
  CHARACTER_CREATION.md
  COMBAT_ABILITIES_AND_EFFECTS.md
  CORE_GAME_MECHANICS.md
  CORE_PARTY_AND_CHARACTER_AGENCY.md
  DICE_ROLLS_AND_REROLLS.md
  GM_BEHAVIOR_AND_PRIORITY.md
  IMAGES_VISUALS_AND_REFERENCE_ART.md
  INVENTORY_EQUIPMENT_AND_ITEMS.md
  NPCS_AND_PARTY_MEMBERSHIP.md
  RELATIONSHIPS_AND_SOCIAL_INTERACTIONS.md
  REPRODUCTION_AND_LINEAGE.md
  REPRODUCTIVE_SPECIES_PROFILES.md
  RULE_AUTHORITY_AND_HIERARCHY.md
  SAVES_VERIFICATION_AND_RECOVERY.md
  SESSION_LOG_AND_HISTORY.md
  SHOPS_PRICING_AND_TRANSACTIONS.md
  STATE_OWNERSHIP_AND_PERSISTENCE.md
  WORLD_QUESTS_AND_CONTINUITY.md

New-Sheets/
  active_game.json
  character_sheet.md
  NPC-state.md
  inventory.md
  routine_item_prices.md
  world_state.md
  session_log.md
  turn_save.md
  Rules/
    Campaign-N_Rules.md
  art/
    art_log.md

campaigns/
  active_campaign.json
  campaign-1/
    active_game.json
    character_sheet.md
    NPC-state.md
    inventory.md
    routine_item_prices.md
    world_state.md
    session_log.md
    turn_save.md
    Rules/
      Campaign-1_Rules.md
    art/
      art_log.md
```

Additional numbered campaigns follow the same campaign-folder pattern, including their own `Rules/Campaign-N_Rules.md`.

---

## Source of truth

When playing or editing a campaign, use the repository's current branch as the source of truth.

In general:

- `Rule/` owns reusable repository-wide rules and operating behavior.
- `campaigns/campaign-N/Rules/Campaign-N_Rules.md` owns persistent rules and overrides intentionally scoped to that campaign.
- `New-Sheets/` owns the reusable blank copy-ready campaign folder skeleton and its fill-out guidance.
- `campaigns/active_campaign.json` selects the active campaign.
- the selected campaign folder owns that campaign's actual canon and mutable state.
- copied instructions, examples, placeholders, and explicitly labeled templates inside campaign files are guidance, not canon.
- `active_game.json` owns the last completed campaign state header and advancement summary defined by the rules.
- `turn_save.md` owns temporary state for the unfinished Campaign Turn.
- `character_sheet.md` owns the core PCs' persistent character state and relationship continuity.
- `NPC-state.md` owns persistent NPC master state.
- `inventory.md` owns detailed current party inventory bookkeeping.
- `routine_item_prices.md` owns recurring routine-item Base Price state.
- `world_state.md` owns persistent world, location, faction, quest, clue, discovery, and consequence state.
- `session_log.md` owns chronological completed-save history.
- `art/art_log.md` owns verified visual-reference metadata while textual appearance canon remains in the appropriate state file.

If rules conflict, use `Rule/RULE_AUTHORITY_AND_HIERARCHY.md`. If state ownership is unclear, use `Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md` rather than guessing.

---

## Continuing an existing campaign

When the player asks to continue play, ChatGPT should first resolve the active campaign from `campaigns/active_campaign.json`.

Then read the applicable reusable rules under `Rule/`, the active campaign's `Rules/Campaign-N_Rules.md`, and the current state required for the scene, including `active_game.json` and `turn_save.md` plus any relevant character, NPC, inventory, world, history, pricing, or visual-reference files.

When reading a copied campaign sheet, distinguish its retained instructions/templates from its actual filled-in campaign state.

If `turn_save.md` contains an unfinished Campaign Turn, recover and continue that Turn according to the Campaign Turn, save, verification, and recovery rules rather than starting a new one or silently discarding staged state.

Do not reconstruct missing campaign canon or local rules from another campaign, previous chats, deleted material, or repository history unless the player explicitly requests a specific import permitted by the rules.

---

## Starting a new campaign

A new numbered campaign should be a fresh sibling folder under `campaigns/`, for example:

```text
campaigns/campaign-2/
```

Copy the complete blank folder skeleton from `New-Sheets/` into the new campaign, preserving its `Rules/` and `art/` subfolders. Keep the useful fill-out guidance, examples, tables, and clearly labeled record templates in the new campaign's copies.

Then initialize campaign identifiers, placeholder character names, starting values, destination-relative references, and the copied campaign-local rules filename/heading according to `Rule/CAMPAIGN_SETUP_ACTIVATION_AND_NAVIGATION.md`.

Do not copy another campaign's populated files.

The copied local-rule template becomes, for example:

```text
campaigns/campaign-2/Rules/Campaign-2_Rules.md
```

Begin that file with no active campaign-specific rules unless the player explicitly establishes some. Do not copy another campaign's local rules into it.

Do not import existing characters, NPCs, relationships, items, locations, quests, secrets, story events, campaign-specific rules, or other campaign material merely because it exists in another numbered campaign.

Change `campaigns/active_campaign.json` only when the new campaign should become the active campaign.

---

## Core play loop

ChatGPT serves as GM/DM and also controls the required ChatGPT-controlled core PC / co-protagonist defined by the rules. The player controls the player-controlled core PC.

The player physically rolls the dice after ChatGPT establishes that a roll is required and states what should be rolled. ChatGPT resolves the supplied result using the applicable mechanics and campaign state.

Gameplay is persisted through **Campaign Turns**. A Campaign Turn may include multiple scenes, decisions, rolls, conversations, combat rounds, individual combatant turns, transactions, discoveries, and consequences. Ending a normal D&D combat turn or combat round does not by itself finish the Campaign Turn.

The exact Step recording, review, confirmation, permanent reconciliation, verification, and reset workflow is defined under `Rule/CAMPAIGN_TURNS_AND_STEPS.md` and `Rule/SAVES_VERIFICATION_AND_RECOVERY.md`.

---

## Images and reference art

Scene images are optional and should follow the image-generation rules in `Rule/IMAGES_VISUALS_AND_REFERENCE_ART.md`.

Generated image files themselves are player-managed. The repository may store verified paths and visual-reference metadata in the active campaign's `art/art_log.md`, while textual appearance canon remains in the state file that owns the character, NPC, location, or item.

---

## Design principle

This repository intentionally separates reusable authority, campaign-local authority, reusable skeletons, and campaign state:

> `Rule/` explains how every campaign works by default.  
> `campaigns/campaign-N/Rules/` records only the persistent rule differences for that campaign.  
> `New-Sheets/` provides the complete blank copy-ready folder skeleton and guidance used to create each campaign's working files.  
> the copied files under `campaigns/campaign-N/` are filled out as that campaign's records while clearly labeled guidance/templates remain noncanonical helpers.

Keeping those roles distinct makes it possible to improve the reusable game system, preserve special campaign rules without leaking them into other campaigns, create new campaigns from a complete working skeleton, and let ChatGPT resume persistent play from the repository instead of relying on chat memory alone.
