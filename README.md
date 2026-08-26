# ChatGPT-DnD

A persistent, choice-driven adult fantasy tabletop RPG repository designed to be played through ChatGPT.

The repository separates **rules**, **blank reusable campaign sheets**, and **live campaign state** so that campaigns can remain persistent without mixing reusable instructions into the save files themselves.

The intended play style uses D&D-style d20 mechanics, player-rolled dice, persistent characters and NPCs, campaign continuity, relationships, combat, quests, inventory, shops, advancement, and optional generated scene art.

All characters involved in adult content must be adults. Detailed content, consent, gameplay, persistence, and GM behavior requirements live in the categorized files under `Rule/`.

---

## Repository model

The repository has three main layers:

### `Rule/` — reusable game and persistence rules

`Rule/` is the central rule library.

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
- rule authority and hierarchy
- saves, verification, and recovery
- session logs and history
- shops, pricing, and transactions
- state ownership and persistence
- world, quests, and continuity

The rule files are the reusable operating brain of the repository. Campaign state files should not duplicate those rules merely for convenience.

### `New-Sheets/` — blank reusable campaign templates

`New-Sheets/` contains clean, campaign-neutral templates used when creating a fresh campaign.

These files contain blank fields, reusable structure, examples, and sheet-specific guidance, but no existing character names, campaign numbers, established relationships, story facts, or live campaign state.

Current templates are:

```text
New-Sheets/
  character_sheet.md
  NPC-state.md
  inventory.md
  routine_item_prices.md
  world_state.md
  session_log.md
  turn_save.md
  art_log.md
```

A new campaign should begin from fresh copies of these templates rather than copying another campaign's live state.

### `campaigns/` — live isolated campaign state

Each numbered campaign owns its own canonical state inside its own folder.

`campaigns/active_campaign.json` is the campaign selector. It identifies the campaign currently in play and points to that campaign's `active_game.json`.

Campaigns are isolated. Character data, NPCs, relationships, inventory, quests, world state, story history, secrets, and other canon do not automatically carry from one numbered campaign into another.

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
  RULE_AUTHORITY_AND_HIERARCHY.md
  SAVES_VERIFICATION_AND_RECOVERY.md
  SESSION_LOG_AND_HISTORY.md
  SHOPS_PRICING_AND_TRANSACTIONS.md
  STATE_OWNERSHIP_AND_PERSISTENCE.md
  WORLD_QUESTS_AND_CONTINUITY.md

New-Sheets/
  character_sheet.md
  NPC-state.md
  inventory.md
  routine_item_prices.md
  world_state.md
  session_log.md
  turn_save.md
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
      champaign-1_Rules.md
    art/
      art_log.md
```

Additional numbered campaigns follow the same campaign-folder pattern.

---

## Source of truth

When playing or editing a campaign, use the repository's current branch as the source of truth.

In general:

- `Rule/` owns reusable rules and operating behavior.
- `New-Sheets/` owns reusable blank sheet structure.
- `campaigns/active_campaign.json` selects the active campaign.
- the selected campaign folder owns that campaign's actual canon and mutable state.
- `active_game.json` owns the last completed campaign state header and advancement summary defined by the rules.
- `turn_save.md` owns temporary state for the unfinished Campaign Turn.
- `character_sheet.md` owns the core PCs' persistent character state and relationship continuity.
- `NPC-state.md` owns persistent NPC master state.
- `inventory.md` owns detailed current party inventory bookkeeping.
- `routine_item_prices.md` owns recurring routine-item Base Price state.
- `world_state.md` owns persistent world, location, faction, quest, clue, discovery, and consequence state.
- `session_log.md` owns chronological completed-save history.
- `art/art_log.md` owns verified visual-reference metadata while textual appearance canon remains in the appropriate state file.

If two instructions or state records appear to conflict, use the authority rules in `Rule/RULE_AUTHORITY_AND_HIERARCHY.md` and the ownership rules in `Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md` rather than guessing.

---

## Continuing an existing campaign

When the player asks to continue play, ChatGPT should first resolve the active campaign from `campaigns/active_campaign.json`.

Then read the active campaign's current state required for the scene, including `active_game.json` and `turn_save.md`, plus any relevant character, NPC, inventory, world, history, pricing, or visual-reference files.

If `turn_save.md` contains an unfinished Campaign Turn, recover and continue that Turn according to the Campaign Turn, save, verification, and recovery rules rather than starting a new one or silently discarding staged state.

Do not reconstruct missing campaign canon from another campaign, previous chats, deleted material, or repository history unless the player explicitly requests a specific import permitted by the rules.

---

## Starting a new campaign

A new numbered campaign should be a fresh sibling folder under `campaigns/`, for example:

```text
campaigns/campaign-2/
```

Create its campaign state from the blank templates in `New-Sheets/`, not from another campaign's populated files.

The new campaign also needs its own `active_game.json` initialized according to the campaign setup, character creation, advancement, save-revision, and Campaign Turn rules.

Do not import existing characters, NPCs, relationships, items, locations, quests, secrets, or story events merely because they exist in another numbered campaign.

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

This repository intentionally separates **instructions from state**:

> `Rule/` explains how the game works.  
> `New-Sheets/` defines what fresh campaign records look like.  
> `campaigns/` records what has actually happened.

Keeping those layers separate makes it possible to improve the game system without rewriting campaign history, create new campaigns without importing old canon, and let ChatGPT resume persistent play from the repository instead of relying on chat memory alone.
