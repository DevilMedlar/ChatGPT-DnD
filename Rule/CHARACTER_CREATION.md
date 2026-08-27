# Character Creation

## Purpose and authority

This file owns the workflow for creating, reviewing, and permanently establishing the required core PCs.

- `PLAYABLE_CHARACTER_OPTIONS.md` owns approved species, species mechanics, class policy, background policy, feat policy, and the homebrew-option completion gates.
- `CORE_GAME_MECHANICS.md` owns the general 5.5e mechanics and campaign clock.
- `CORE_PARTY_AND_CHARACTER_AGENCY.md` owns which character the player controls and which character ChatGPT controls.
- `ADULT_CONTENT_AND_CONSENT.md` owns adult-content boundaries.
- `STATE_OWNERSHIP_AND_PERSISTENCE.md` owns where finalized character state is stored.

## Required core PCs

Before Campaign Turn 1 begins, character creation must establish:

1. the player-controlled PC, and
2. the ChatGPT-controlled PC / co-protagonist.

At minimum, establish for each:

- Name
- Age
- Gender / pronouns
- Biological reproductive role when relevant
- Species / ancestry
- Class or approved homebrew class
- Background
- Level and XP
- Ability scores
- Saving throw and skill proficiencies
- Hit Points and Hit Dice
- Armor Class
- Initiative
- Speed
- Proficiency Bonus
- Starting equipment and currency
- Species traits
- Class features, spells, and resources
- Appearance
- Backstory and important relationships
- Current conditions and ongoing effects
- Reproductive state when the player chooses to establish it

All PCs must be at least 18 years old. A PC participating in adult or reproductive content must also be physically and reproductively mature.

Blank required fields remain undecided until explicitly established. Do not recover, guess, or import them from another campaign, deleted material, or chat memory.

## Species / ancestry limitation

`PLAYABLE_CHARACTER_OPTIONS.md` is the global character-creation species authority.

Under the global rules:

- each required core PC must select one of its thirteen standard species packages
- every later replacement, additional, or newly created PC must use the same roster
- the selected package supplies the character's complete species mechanics
- do not stack that package with an older species version, subrace, lineage, monster stat block, or second package
- an official builder or sourcebook does not add an option by implication
- a hybrid is not automatically selectable

An unlisted species or nonstandard form becomes available only when:

1. the player explicitly adds and completes it globally in `PLAYABLE_CHARACTER_OPTIONS.md`, or
2. the active campaign records an explicit local option in `campaigns/campaign-N/Rules/Campaign-N_Rules.md`.

A local option applies only to that campaign.

This limits PC creation, not world population. Unlisted creatures may still exist as NPCs, monsters, wildlife, or historical peoples.

## Class, subclass, background, and feat selection

Use `PLAYABLE_CHARACTER_OPTIONS.md`.

- The twelve listed 5.5e core classes are globally available.
- Every approved species may choose any approved class.
- A current official subclass, background, or feat may be used when its complete mechanics can be verified.
- A homebrew option must pass its completion gate before selection.
- Do not finalize a character around a class, subclass, background, or feat whose required mechanics remain missing.
- Use official 5.5e multiclassing rules unless an explicit homebrew rule replaces them.

## Revision 0 is the complete pre-game phase

`save_revision: 0` covers campaign setup, both required PCs, backstory, initial relationships, starting resources, and every other pre-game fact.

During revision 0:

- `active_game.json.campaign_turn_number` remains `0`
- `active_game.json.character_created` remains `false`
- `active_game.json.save_revision` remains `0`
- `active_game.json.current_scene_name` remains `Character creation` until the final opening frame
- the campaign clock remains at its initialized starting value and does not advance for out-of-fiction design discussion
- `turn_save.md` remains prepared for Campaign Turn 1
- `turn_save.md.Status` remains `ready`
- `turn_save.md.Current Step` remains `0`
- `turn_save.md.Base save revision` remains `0`
- no character-creation discussion creates a Campaign Turn Step
- no intermediate choice creates a completed `session_log.md` checkpoint
- no intermediate choice increments `save_revision`

Explicitly finalized revision-0 facts may be written directly to their proper permanent owners. Those writes are revisions of the same pre-game baseline, not separate saves.

A transcription mistake may be corrected directly during revision 0. A real change to an already established pre-game choice follows the player's newest explicit direction and must be synchronized everywhere it is represented.

## Working procedure

As character creation proceeds:

1. establish choices collaboratively
2. distinguish finalized choices from examples, discussion, rejected options, and undecided possibilities
3. validate the proposed species and its exact package against `PLAYABLE_CHARACTER_OPTIONS.md`
4. validate the class, subclass, background, feat, and any homebrew mechanics
5. calculate all derived values from the finalized mechanics
6. write finalized character details to `character_sheet.md`
7. write starting equipment, currency, ammunition, consumables, and other possessions to `inventory.md`
8. synchronize Level/XP mirrors with `active_game.json.character_advancement`
9. replace the advancement placeholder keys with the PCs' actual names as soon as those names are finalized
10. preserve `save_revision: 0`, `campaign_turn_number: 0`, and `character_created: false`
11. leave genuinely undecided fields blank

## Species-package recording

For each core PC, `character_sheet.md` must record:

- the exact species name from `PLAYABLE_CHARACTER_OPTIONS.md`
- Creature Type
- Size
- Speed and any special movement
- every species trait
- every fixed trait choice, such as Dragonborn Draconic Energy
- each trait's uses, recharge, scaling, and save DC when applicable
- any form limitations or level gates

Do not record only the species name while leaving the actual mechanics implicit.

## Class-package recording

For each core PC, record enough class information to run play without guessing:

- class and subclass
- Hit Die
- proficiencies and armor training
- class resources
- all current-level features
- spellcasting ability, cantrips, prepared/known spells, slots, and focus when applicable
- Weapon Mastery choices when applicable
- current uses, charges, or resource totals
- future feature choices only when they become available

Do not copy the full level 1–20 official class text into the character sheet. Record the character's current mechanical state and reference the current rules for future levels.

## Reproductive state during character creation

Reproductive details are optional unless the campaign premise requires them.

When established, record only explicit facts such as:

- biological reproductive role
- reproductive maturity
- fertility status and modifier
- pregnancy, egg-production, or contraception state
- established reproductive effects or treatments

The healthy mature default in `REPRODUCTION_AND_LINEAGE.md` may be recorded as `Fertile +0`. Never invent hidden infertility, pregnancy, conception history, or modifiers.

## Final character-creation review

Before revision 0 may end, verify both required PCs.

### Identity and approval

- every required identity field is established
- each PC is at least 18
- each species exactly matches an approved standard package or applicable campaign override
- no unapproved subrace, alternate lineage, hybrid package, monster stat block, or second species package was added
- each class, subclass, background, feat, and homebrew option is complete and approved

### Mechanical consistency

- ability scores and modifiers are correct
- HP, Hit Dice, AC, Initiative, Speed, Proficiency Bonus, saving throws, skills, attacks, spell DCs, and resource totals are correct
- every selected species trait is fully recorded
- every current class feature is fully recorded
- Level/XP in `character_sheet.md` exactly matches `active_game.json.character_advancement`
- starting equipment and currency exactly match `inventory.md`
- no rejected or undecided option became canonical

### Continuity and state

- finalized backstory and relationships are in their correct owners
- appearance is sufficiently established for continuity
- campaign-specific rules are in the campaign's local rule file
- `campaign_turn_number` is `0`
- `save_revision` is `0`
- `character_created` is `false`
- the clock has a valid initialized value
- `turn_save.md` is still ready for Campaign Turn 1 and has no gameplay Steps

Then show the completed character-creation state and any exact corrections required, and ask:

`Confirm character creation complete and establish the Campaign Turn 1 baseline? Yes / No / Corrections`

If the player says **No**, keep revision 0 open.

If the player provides **Corrections**, apply them, repeat the review, and ask again.

## GM-authored opening frame

After the player confirms character creation:

- ChatGPT creates the opening situation, location, time, atmosphere, nearby NPCs, hooks, and complications consistent with established canon
- ChatGPT chooses a concise descriptive scene label
- ChatGPT establishes the actual opening campaign clock
- the player is not required to invent a scene title or predetermined first action
- the opening frame does not choose the player-controlled PC's dialogue or action

The scene name describes the fiction. It never constrains where the player may go or what the player may choose.

## Transition from revision 0 to revision 1

After a **Yes** confirmation:

1. write every final character-creation fact to its proper owner
2. synchronize all mirrors and inventories
3. create and persist the GM-authored opening frame
4. replace `current_scene_name: Character creation` with the opening scene label
5. set `current_location` to the actual opening location
6. set `active_game.json.campaign_clock` to the opening day and time
7. persist continuity-relevant opening world facts and scheduled events
8. set `character_created` to `true`
9. keep `campaign_turn_number` at `0`
10. set `save_revision` from `0` to `1`
11. set a compact `last_sync_note`
12. append one revision-1 character-creation completion entry to `session_log.md`, including the opening clock
13. keep `turn_save.md.Campaign Turn` at `1`
14. keep `turn_save.md.Status` as `ready`
15. keep `turn_save.md.Current Step` at `0`
16. set `turn_save.md.Current Scene` to the opening scene label
17. set `turn_save.md.Base save revision` to `1`
18. set the Turn's start and current clock to match `active_game.json.campaign_clock`
19. do not create a gameplay Step merely because character creation completed

Whenever possible, commit the synchronized revision-1 baseline atomically. If writes must be sequential, update supporting files first and `active_game.json` last, then verify the complete baseline.

## Campaign Turn 1 starting condition

Immediately before Campaign Turn 1 begins:

```text
active_game.json.campaign_turn_number = 0
active_game.json.character_created = true
active_game.json.save_revision = 1
active_game.json.current_scene_name = opening scene label
active_game.json.current_location = opening location
active_game.json.campaign_clock = opening completed clock
turn_save.md.Campaign Turn = 1
turn_save.md.Status = ready
turn_save.md.Current Step = 0
turn_save.md.Current Scene = opening scene label
turn_save.md.Base save revision = 1
turn_save.md.Start Clock = active_game.json.campaign_clock
turn_save.md.Current In-Turn Clock = active_game.json.campaign_clock
```

Starting Campaign Turn 1 changes the Turn ledger to `in_progress` but does not increment `save_revision`. The completed save for Campaign Turn 1 later advances revision `1` to revision `2`.

Advancement is governed by `ADVANCEMENT_AND_XP.md`. Campaign Turn staging is governed by `CAMPAIGN_TURNS_AND_STEPS.md`. Save confirmation and verification are governed by `SAVES_VERIFICATION_AND_RECOVERY.md`.
