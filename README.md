# ChatGPT-DnD

A persistent, choice-driven adult fantasy tabletop RPG designed to be played through ChatGPT.

The repository separates reusable rules, campaign-specific rules, blank reusable campaign sheets, and live campaign state so play can continue from verified files rather than chat memory.

The ordinary mechanics baseline is D&D 5.5e / SRD 5.2.1. Explicit repository homebrew overrides that baseline for the subjects it governs, including player-owned dice, Campaign Turns, playable species, cross-species reproduction, persistence, relationships, and pricing.

All characters involved in adult content must satisfy `Rule/ADULT_CONTENT_AND_CONSENT.md`.

# Repository model

## `Rule/`

The reusable repository-wide rule library.

Key authorities include:

- `CORE_GAME_MECHANICS.md` for the 5.5e baseline and canonical campaign clock
- `CHARACTER_CREATION.md` for the revision-0 character-creation workflow
- `PLAYABLE_CHARACTER_OPTIONS.md` for approved PC species, their complete mechanics, core-class policy, backgrounds, feats, and homebrew completion gates
- `REPRODUCTION_AND_LINEAGE.md` for compatibility, fertility, conception, pregnancy or egg development, offspring, inheritance, birth or hatching, growth, and later generations
- `CAMPAIGN_TURNS_AND_STEPS.md` for unfinished-Turn staging
- `SAVES_VERIFICATION_AND_RECOVERY.md` for confirmation, permanent reconciliation, verification, recovery, and reset
- `STATE_OWNERSHIP_AND_PERSISTENCE.md` for file ownership
- `RULE_AUTHORITY_AND_HIERARCHY.md` for conflicts

A numbered campaign does not duplicate unchanged global rules merely for convenience.

## `campaigns/campaign-N/Rules/`

Each campaign has one persistent local-rule delta:

```text
campaigns/campaign-N/Rules/Campaign-N_Rules.md
```

It stores only explicit rules or overrides scoped to that campaign. Ordinary character, NPC, family, inventory, clock, world, quest, shop, session, and art facts remain in their assigned state owners.

A local rule never silently carries into another campaign.

## `New-Sheets/`

The blank copy-ready campaign skeleton.

Its Markdown files intentionally retain headings, empty tables, examples, instructions, and labeled templates. Those helpers are documentation, not campaign facts.

A new numbered campaign copies the complete skeleton and preserves its `Rules/` and `art/` subfolders.

## `campaigns/`

The isolated live campaign folders.

`campaigns/active_campaign.json` selects the current campaign and points to its `active_game.json`. It is not a duplicate save.

# Current rule layout

```text
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
  PLAYABLE_CHARACTER_OPTIONS.md
  RELATIONSHIPS_AND_SOCIAL_INTERACTIONS.md
  REPRODUCTION_AND_LINEAGE.md
  RULE_AUTHORITY_AND_HIERARCHY.md
  SAVES_VERIFICATION_AND_RECOVERY.md
  SESSION_LOG_AND_HISTORY.md
  SHOPS_PRICING_AND_TRANSACTIONS.md
  STATE_OWNERSHIP_AND_PERSISTENCE.md
  WORLD_QUESTS_AND_CONTINUITY.md
```

The character/reproduction system is intentionally consolidated into:

```text
PLAYABLE_CHARACTER_OPTIONS.md
REPRODUCTION_AND_LINEAGE.md
```

There is no separate candidate catalog, reproductive profile index, numbered profile batch, or duplicate completed-profile authority.

# Campaign skeleton

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

Normal copy map:

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
New-Sheets/art/art_log.md                       -> campaigns/campaign-N/art/art_log.md
```

Adjust campaign identifiers, names, headings, and relative references in the copied destination without inventing campaign canon.

# Source of truth and state ownership

Use the current branch as the source of truth.

Within a numbered campaign:

- `Rules/Campaign-N_Rules.md` owns local rule overrides
- `active_game.json` owns the last completed campaign header, completed clock, completed scene/location, advancement, and save revision
- `turn_save.md` owns the unfinished Campaign Turn overlay, including live clock, Steps, rolls, reproductive events, transactions, and pending transfers
- `character_sheet.md` owns persistent core-PC state, species package, class mechanics, appearance, relationships, reproductive state, and parent state
- `NPC-state.md` owns persistent NPC and child master records, stable IDs, family links, reproductive state, hybrid traits, possessions, shops, and continuity
- `inventory.md` owns detailed active possession bookkeeping
- `routine_item_prices.md` owns recurring routine Base Prices
- `world_state.md` owns calendar lore, schedules, deadlines, due dates, laying dates, hatching dates, locations, factions, quests, clues, discoveries, and consequences
- `session_log.md` owns completed chronological checkpoints
- `art/art_log.md` owns verified visual-reference metadata

Retained templates, placeholder IDs, and empty example rows are not canon.

# Playable characters

`Rule/PLAYABLE_CHARACTER_OPTIONS.md` currently provides thirteen standard species packages:

1. Human
2. Elf
3. Dwarf
4. Gnome
5. Dragonborn
6. Dragonkin
7. True Dragon
8. Kitsune
9. Neko
10. Usagi
11. Inu
12. Ookami
13. Lizardfolk

It also enables the twelve core 5.5e classes by reference to the current official rules and defines strict completion gates for homebrew classes, backgrounds, subclasses, and feats.

An unlisted species or incomplete homebrew option is not selectable merely because its name or concept was mentioned.

# Reproduction and lineage

`Rule/REPRODUCTION_AND_LINEAGE.md` is the only dedicated reproduction authority.

It establishes:

- all thirteen active species are cross-species compatible in both directions
- the female parent determines live birth versus egg production
- True Dragons can use their innate size/form accommodation for physical access without changing ancestry or development route
- fertility and conception use player-rolled percentile dice from one d10 rolled twice
- one conception check per pair per 24 in-world hours
- offspring count and biological sex are player-rolled
- gestation, egg-production, laying, incubation, and detection schedules
- a four-slot hybrid mechanical inheritance budget
- cosmetic inheritance, delayed trait development, birth/hatching, childhood milestones, adult fertility, and later generations
- biological and adoptive parentage remain distinct

ChatGPT never manufactures reproductive dice results or chooses an outcome to fit the narrative.

# Campaign clock

Every campaign uses one canonical clock:

```json
"campaign_clock": {
  "calendar": "Campaign Day",
  "day": 1,
  "time": "08:00:00"
}
```

- `active_game.json` owns the completed clock.
- `turn_save.md` owns the live unfinished-Turn clock.
- `world_state.md` owns calendar lore and scheduled events.
- substantial time never advances silently.
- one Combat Round consumes 6 seconds, regardless of combatant count.
- crossed deadlines and milestones must be resolved chronologically.

# Character creation and Campaign Turn 1

The full pre-game setup uses `save_revision: 0`.

Character-creation discussion does not advance the in-world clock or create Campaign Turn Steps.

After both core PCs are complete and the player confirms the final review, ChatGPT creates the opening frame and establishes revision 1 with:

- `character_created: true`
- `campaign_turn_number: 0`
- opening scene and location
- opening campaign clock
- synchronized character, inventory, advancement, world, and session state
- `turn_save.md` still ready for Campaign Turn 1

Campaign Turn 1 begins from revision 1. Its later approved completed save becomes revision 2.

# Core play loop

ChatGPT acts as GM/DM and controls the required ChatGPT-controlled PC / co-protagonist. The player controls the player-controlled PC.

The player physically rolls every die after ChatGPT states the exact roll and stakes. ChatGPT resolves only the supplied result.

Gameplay is staged through Campaign Turns. A Campaign Turn may contain many scenes, decisions, Combat Rounds, transactions, reproductive events, discoveries, and clock changes. Ending a Combat Turn or Combat Round does not end the Campaign Turn.

At the full Turn end:

1. freeze and review the ledger
2. show Final Turn State and Exact Planned Permanent Transfers, including clock
3. obtain save confirmation
4. reconcile permanent state
5. verify every affected file
6. preserve the ledger
7. obtain separate reset confirmation

# Images and reference art

Optional generated scene art follows `Rule/IMAGES_VISUALS_AND_REFERENCE_ART.md`.

Generated image files are player-managed. The repository stores verified paths and metadata in the active campaign's `art/art_log.md`; textual appearance canon remains in the character, NPC, world, or item state owner.

# Design principle

> `Rule/` explains how every campaign works by default.  
> Campaign-local `Rules/` stores only deliberate differences.  
> `New-Sheets/` provides the blank working skeleton and guidance.  
> Each numbered campaign owns its isolated state and clock.

That separation lets the game evolve without relying on chat memory, mixing campaigns, duplicating authorities, or losing continuity.
