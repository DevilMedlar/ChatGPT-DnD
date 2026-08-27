# State Ownership and Persistence

## Purpose

This file defines which repository file owns each kind of reusable rule, campaign-local rule, completed campaign state, unfinished Campaign Turn state, time state, and historical record.

Read it with `RULE_AUTHORITY_AND_HIERARCHY.md`, `CAMPAIGN_TURNS_AND_STEPS.md`, and `SAVES_VERIFICATION_AND_RECOVERY.md`.

## Active campaign selector

`campaigns/active_campaign.json` selects the campaign currently in play and points to that campaign's `active_game.json`.

It is a pointer, not a duplicate save. Ordinary gameplay, time passage, state changes, or completed Campaign Turns do not rewrite it unless the active campaign or pointer actually changes.

Changing campaigns does not move, merge, copy, or rewrite campaign state.

## Campaign isolation

Every numbered campaign owns its state inside its own folder and its persistent local-rule delta inside:

`campaigns/campaign-N/Rules/Campaign-N_Rules.md`

Never write one campaign's PCs, NPCs, children, relationships, inventory, clock, quests, world state, history, prices, art continuity, reproductive state, or local rules into another campaign unless the player explicitly authorizes a crossover or import.

Fresh-start restrictions are defined in `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`.

## Rule ownership

- `Rule/` owns reusable repository-wide rules.
- `PLAYABLE_CHARACTER_OPTIONS.md` owns global selectable species packages and character-option policy.
- `REPRODUCTION_AND_LINEAGE.md` owns reproduction, conception, pregnancy or egg development, birth or hatching, post-birth trait development, and later-generation rules.
- `campaigns/campaign-N/Rules/Campaign-N_Rules.md` owns only explicit persistent rules or overrides scoped to that campaign.

Do not store ordinary campaign facts in a local rule file. Editing a rule file does not itself create a Campaign Turn Step or increment `save_revision`.

## New-Sheets and copied campaign files

`New-Sheets/` owns the blank copy-ready campaign skeleton and its maintenance guidance.

A copied Markdown campaign file may contain both:

- actual filled-in canonical state
- retained instructions, empty layouts, examples, placeholders, and labeled templates

Only the filled-in state is canonical.

Examples such as `NPC-####`, an empty shop row, `PLAYER_CONTROLLED_PC_NAME`, a Conception Check Template, or a Shop Transaction Template are documentation until replaced or used in an actual record.

If copied guidance conflicts with the current reusable rules, the current reusable rules win.

A later improvement to `New-Sheets/` does not automatically rewrite an existing campaign. Migrate an existing campaign only when explicitly requested or when a required rule change makes the migration necessary, preserving established state.

## Revision-0 character creation

The entire pre-game setup, character creation, and backstory phase uses `save_revision: 0`.

During revision 0:

- finalized facts may be written directly to their proper permanent owners
- no character-creation discussion creates a Campaign Turn Step
- no intermediate choice increments `save_revision`
- no intermediate completed checkpoint is added to `session_log.md`
- `campaign_turn_number` remains `0`
- `character_created` remains `false`
- the initialized campaign clock does not advance for out-of-fiction discussion

Revision 0 ends only through the confirmed transition defined in `CHARACTER_CREATION.md`.

## Completed state and unfinished Turn overlay

`active_game.json` represents the last completed permanent campaign header or the current revision-0 baseline.

`turn_save.md` represents the current unfinished Campaign Turn.

The effective state while a Turn is open is:

`last completed permanent state + turn_save.md overlay`

A live value in `turn_save.md` temporarily supersedes the older completed value without rewriting permanent state before save approval.

# File ownership within a numbered campaign

## `Rules/Campaign-N_Rules.md`

Owns persistent campaign-specific rules, overrides, exceptional premises, and explicit operating instructions scoped to that campaign.

It is not ordinary state.

## `active_game.json`

Owns the last completed campaign header:

- campaign identifier
- completed `campaign_turn_number`
- completed or pre-game `current_scene_name`
- completed or pre-game `current_location`
- completed `campaign_clock`
- character-creation completion state
- `xp_mode`
- authoritative completed PC advancement in `character_advancement`
- `save_revision`
- latest synchronization note

It does not own the live Campaign Turn Step or live unfinished clock.

## `turn_save.md`

Owns the temporary authoritative ledger for the current Campaign Turn:

- active or next Campaign Turn number
- status
- Current Step and Current Scene
- Base save revision
- Campaign Turn Start Clock
- Current In-Turn Clock
- elapsed time and time-change reasons
- numbered events and roll results
- compact effective in-turn state
- pending reproductive events
- staged conception-check and mundane-detection cooldown changes
- pending shop transactions
- pending permanent transfers
- Final Turn Review
- permanent-save verification
- reset approval

Copied templates remain guidance rather than actual staged events.

## `character_sheet.md`

Owns persistent core-PC state:

- identity, age, species package, class, subclass, background, and advancement mirrors
- ability scores, statistics, features, spells, resources, and conditions
- stable textual appearance canon
- personal and relationship continuity
- reproductive maturity, fertility, pregnancy or egg-production state, co-parent, conception clock, due or laying date, hatching date, and aggregate offspring or fertilized-egg count
- current pair-specific conception-check cooldowns until their next eligible clocks pass
- the current mundane-detection cooldown when the PC is the reproductive-state target
- children and parent state after live birth or hatching

The two core PCs share all learned information under `CORE_PARTY_AND_CHARACTER_AGENCY.md`; do not create separate secret-knowledge owners for them.

Authoritative detailed inventory remains in `inventory.md`.

## `NPC-state.md`

Owns persistent NPC and post-birth child master state:

- stable IDs
- identity, age, birth or hatching clock, species, appearance, personality, location, and status
- relationships, attractions, revealed information, known beliefs, known contradictions, and known unanswered questions
- party membership
- mechanics and conditions
- master personal possessions
- reproductive maturity, fertility, pregnancy or egg-production state, co-parent, dates, and aggregate offspring or fertilized-egg count
- current pair-specific conception-check cooldowns until their next eligible clocks pass
- the current mundane-detection cooldown when the NPC is the reproductive-state target
- biological parents, adoptive parents, guardians, and children as separate relationships
- after live birth or hatching: biological sex, visible traits, delayed or potential traits, later resolved mechanical traits, developmental milestones, and adult fertility
- NPC-specific quests, shops, stock, services, and continuity revealed to the core PCs

Do not create an individual child NPC record before live birth or hatching. Before then, the female parent's state owns the aggregate pregnancy or clutch.

Do not store an untold hidden answer or unrevealed secret. When the core PCs know only that a question exists, store the known question rather than its answer.

For a current party NPC, `inventory.md` expands active item bookkeeping while `NPC-state.md` remains the master ownership list.

## `routine_item_prices.md`

Owns campaign-local recurring Base Prices and routine/basic classification.

It does not own item mechanics, vendor quantities, Final Unit Price, Final Transaction Price, or inventory.

## `inventory.md`

Owns detailed active mechanical bookkeeping for core-PC possessions and the carried possessions of current party NPCs, including currency, quantities, ammunition, consumables, charges, equipment state, and acquired-item mechanics snapshots.

## `world_state.md`

Owns persistent world context:

- calendar name, seasons, named-date mapping, and planar/time-zone context
- scheduled events, appointments, deadlines, restocks, due dates, laying dates, hatching dates, and established developmental milestones
- locations, factions, quests, clues, discoveries, unresolved questions known to the core PCs, and world consequences
- lightweight references to persistent NPCs by stable ID

It does not own the authoritative current clock. That belongs in `active_game.json` plus the live `turn_save.md` overlay.

It does not store untold answers, hidden GM solutions, secret perpetrators, or undiscovered facts. Unknown matters are stored only as questions after the core PCs become aware that the question exists.

## `session_log.md`

Owns append-first chronological completed history:

- the single revision-1 character-creation completion / Campaign Turn 1 baseline entry
- one checkpoint per completed Campaign Turn
- start clock, end clock, elapsed time, and chronology-critical events when applicable

It does not accumulate intermediate revision-0 checkpoints or unfinished Turn events.

An unsuccessful conception or detection check normally needs no permanent historical entry, but its active 24-hour cooldown remains in current character or NPC state until it expires.

## `art/art_log.md`

Owns verified visual-reference paths and visual-reference metadata. It never overrides the textual appearance owner.

# Campaign-clock ownership

The canonical completed clock is `active_game.json.campaign_clock`.

During an unfinished Campaign Turn:

- `turn_save.md.Start Clock` equals the completed clock at Turn opening
- `turn_save.md.Current In-Turn Clock` is the effective live clock
- time changes remain staged until save approval
- `world_state.md` supplies scheduled timestamps that must be checked whenever time advances

At approved reconciliation, the Final Turn End Clock transfers to `active_game.json.campaign_clock`. It must not also be stored as a competing current-clock field elsewhere.

# Append-first history and current mutable state

## Chronological sections

History sections are append-first. Add later entries instead of compressing, reorganizing, or deleting useful earlier history merely for neatness.

Preserve an earlier mutable value in history only when it matters to continuity.

## Current mutable state

Update current-state fields in place during approved reconciliation. Do not leave stale current values beside new values.

Examples include HP, current clock, location, currency, item quantity, conditions, relationship state, pregnancy or egg state, due dates, quest status, party membership, shop stock, conception cooldowns, and detection cooldowns.

An expired reproductive cooldown may be removed once the campaign clock has passed its next eligible clock.

# Turn staging and duplicate prevention

`turn_save.md` may temporarily restate permanent facts for recovery context. Restatement does not make an unchanged fact a new permanent transfer.

During Final Turn Review:

1. compare every proposed result with its current authoritative owner
2. separate real changes from unchanged context
3. remove unchanged existing facts from Exact Planned Permanent Transfers
4. do not create duplicate permanent records merely because a fact appeared in the Turn ledger
5. transfer a fact to multiple files only when an established master/detail or required mirror relationship exists
6. organize real changes by destination file
7. include the approved End Clock as one transfer to `active_game.json`
8. include current reproductive cooldowns when they remain active after the End Clock

# Corrections and legitimate removal

Established state constrains narration and calculations. Read the authoritative owner and live Turn overlay before resolving a continuity-sensitive fact.

A correction is permitted when material is actually wrong, conflicts with the player's newest explicit correction, contains an accidental duplicate, or creates a verified inconsistency.

During an active Turn or Final Review:

- correct the temporary record or proposed transfer first
- recalculate dependent state, clock, schedules, and planned transfers
- show the corrected review again when confirmation is required
- reconcile only after approval

Do not invent a retcon for convenience.

Current state may legitimately be removed when play establishes loss, sale, use, consumption, destruction, transfer, death, completed pregnancy, laid eggs, hatched eggs, resolved conditions, expired effects, an expired cooldown, or another real state transition.

If conflicting current facts cannot be resolved from existing authority, use `RULE_AUTHORITY_AND_HIERARCHY.md` and obtain the player's direction.

# Permanent transfer destinations

Typical approved destinations include:

- `character_sheet.md` for core-PC mechanics, appearance, relationships, reproductive state, active reproductive cooldowns, and parent state
- `NPC-state.md` for NPC and post-birth child master state, family links, mechanics, possessions, shops, reproductive state, active reproductive cooldowns, and later development
- `inventory.md` for active item and currency bookkeeping
- `routine_item_prices.md` for recurring Base Prices
- `world_state.md` for calendar context, schedules, quests, locations, clues, unresolved questions, and consequences
- `session_log.md` for completed chronology
- `art/art_log.md` for verified visual references
- `active_game.json` for completed Turn number, scene, location, clock, advancement, revision, and sync note

An unsuccessful conception or detection check normally needs no historical transfer, but any still-active 24-hour cooldown must transfer to the current state owner.

# Master/detail synchronization

When one fact legitimately has a master and a detailed active representation, synchronize both in the same completed save.

Examples:

- current party NPC possessions: `NPC-state.md` and `inventory.md`
- PC Level/XP: `active_game.json.character_advancement` and human-readable mirrors in `character_sheet.md`
- routine item Base Price: `routine_item_prices.md` and every current vendor mirror
- a shop transaction: vendor stock, buyer currency, acquired inventory, item snapshot, stack result, and NPC ownership when applicable
- a conception check: both participants' still-active pair cooldown records
- a failed mundane detection check: the target's still-active detection cooldown
- a scheduled birth or hatching: parent state and the corresponding `world_state.md` scheduled milestone
- after birth or hatching: each child's `NPC-state.md` record and the parents' child references

# Persistence discipline

During revision 0, finalized pre-game facts may be written directly without opening a Campaign Turn or incrementing the revision.

After gameplay begins:

- stage ordinary changes in `turn_save.md`
- do not rewrite permanent state before save approval
- reconcile only approved results
- verify every affected owner afterward
- preserve the full ledger until the player approves reset

A file does not need fictional changes merely to prove it was checked. If nothing substantive changed, preserve it.
