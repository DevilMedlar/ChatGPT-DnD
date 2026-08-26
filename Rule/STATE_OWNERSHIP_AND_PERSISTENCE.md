# State Ownership and Persistence

## Active campaign selector

`campaigns/active_campaign.json` selects the campaign currently in play. It is a pointer, not a duplicate live save.

It identifies the active numbered campaign and the path to that campaign's `active_game.json`.

Live gameplay state does **not** belong in `active_campaign.json`. Do not rewrite it after ordinary Campaign Turns unless the active campaign selection, campaign path, or `active_game.json` pointer actually changes.

Changing campaigns changes the selector only. It does not move, merge, copy, or rewrite campaign state.

## Campaign isolation

Each numbered campaign owns its state inside its own folder and owns its persistent campaign-specific rule layer under that folder's `Rules/` directory.

Never write one campaign's character, NPC, relationship, inventory, world, quest, session, pricing, turn-save, advancement, art-continuity state, or campaign-specific rules into another campaign folder unless the player explicitly requests a crossover or import.

Fresh-start canon restrictions are defined in `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`.

## Campaign-specific rule ownership

Each numbered campaign stores persistent campaign-specific rules in:

`Rules/Campaign-N_Rules.md`

That file is **not gameplay state**. It owns only persistent rules, overrides, exceptional premises, and other explicit player instructions intentionally scoped to that campaign.

Do not store ordinary character, NPC, relationship, inventory, world, quest, shop, advancement, session, or art facts there. Those remain in their assigned state owners below.

Editing the campaign-specific rule file does not by itself create a Campaign Turn Step or increment `save_revision`. If a rule change also requires persistent campaign state to change, apply those state changes through the applicable persistence workflow.

Rule priority and campaign-specific scope are defined in `RULE_AUTHORITY_AND_HIERARCHY.md`.

## New-Sheets and copied campaign files

`New-Sheets/` owns the reusable **blank copy-ready skeletons/outlines** for new campaigns.

A new numbered campaign normally begins by copying those files into the campaign's own folder and then filling out that campaign's copies.

Copied Markdown campaign files may therefore contain both:

- the campaign's actual canonical state
- retained inline guidance, examples, blank layouts, and clearly labeled reusable templates that explain how to maintain that state file

These roles must not be confused.

### Canonical state versus retained guidance

Actual filled-in state that belongs to the campaign is canonical according to the ownership rules below.

Retained instructions, examples, placeholder values, and sections explicitly labeled as templates are documentation only. They do not become campaign facts merely because they exist inside a live campaign file.

For example:

- a labeled `NPC Record Template` is not itself an NPC
- `NPC-####` is not an assigned stable ID until replaced by a real ID in an actual NPC record
- a labeled `Shop Transaction Template` is not a pending purchase
- an empty example row is not inventory, shop stock, or a price
- `PLAYER_CONTROLLED_PC_NAME` and `CHATGPT_CONTROLLED_PC_NAME` are placeholders until replaced by established character names

If retained copied guidance conflicts with the current reusable rules under `Rule/`, the current reusable rules control. The copied guidance helps ChatGPT fill out the campaign's file but is not an independent rule layer.

The exact copy procedure, destination mapping, and reference-adjustment behavior are defined in `CAMPAIGN_SETUP_ACTIVATION_AND_NAVIGATION.md`.

### Existing campaign copies

A later change to `New-Sheets/` does not automatically rewrite an already-created campaign's files. The campaign's copies remain its working records.

Apply a later template improvement to an existing campaign only when explicitly requested or when a required rule change makes the migration necessary, preserving established state.

## Character-creation state and revision 0

The entire pre-game character-creation and backstory phase belongs to `save_revision: 0`.

During revision 0, explicitly established character-creation facts may be written directly to their proper permanent state owners as part of the same evolving pre-game baseline. These writes do not create Campaign Turn Steps and do not increment `save_revision`.

Revision 0 continues until character creation is fully complete and the player confirms the final transition defined in `CHARACTER_CREATION.md`.

That transition establishes `save_revision: 1` as the permanent starting baseline for Campaign Turn 1, while `campaign_turn_number` remains `0` and `turn_save.md` remains `ready` with `Base save revision: 1`.

## Completed state and live Turn state

Each campaign's `active_game.json` is authoritative for that campaign's **last completed campaign state header**.

Before gameplay begins, revision 1 is the completed pre-game starting baseline for Campaign Turn 1.

During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, Current Scene, and staged changes belong in that campaign's `turn_save.md`.

The effective state during an open Campaign Turn is the last completed permanent state plus the temporary `turn_save.md` overlay.

## File ownership

Within each numbered campaign:

- `Rules/Campaign-N_Rules.md` — persistent campaign-specific rules, overrides, exceptional premises, and explicitly scoped operating instructions. It is not ordinary campaign state and should contain only the campaign-specific delta from the reusable `Rule/` library.
- `active_game.json` — authoritative **last completed campaign state header**: completed `campaign_turn_number`, completed/pre-game `current_scene_name`, completed location, character-creation completion state, authoritative completed PC advancement through `xp_mode` and `character_advancement`, `save_revision`, and latest synchronization note. It does not store the live Campaign Turn Step.
- `turn_save.md` — temporary authoritative ledger for the current Campaign Turn: current/next Campaign Turn number, `Current Step`, `Current Scene`, numbered events, compact effective in-turn state, pending shop transactions, pending permanent transfers, final review, permanent-save verification, and reset approval. Its copied instructional/template sections may remain as noncanonical fill-out guidance.
- `character_sheet.md` — core-PC statistics, abilities, textual appearance canon, personal state, established relationship continuity, and synchronized human-readable Level/XP mirrors of `active_game.json`.
- `NPC-state.md` — persistent NPC stable IDs, identity, textual appearance canon, statistics, abilities, conditions, personality, relationships/attractions, knowledge/secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC-specific continuity.
- `routine_item_prices.md` — authoritative campaign-local classification and recurring Base Price reference for routine/basic repeat goods. Vendor rows mirror these Base Prices; this file does not own item mechanics, vendor quantities, merchant modifiers, Final Price, or inventory.
- `inventory.md` — detailed active mechanical bookkeeping for core PCs and possessions carried by current party NPCs, including owned-item mechanics snapshots and relevant owned-item state. For persistent NPCs, `NPC-state.md` remains the master ownership list.
- `world_state.md` — locations, factions, overall quests/missions, clues, discoveries, player-known world secrets, unresolved world threads, world consequences, and lightweight world-context references to persistent NPCs by stable NPC ID and current name.
- `session_log.md` — one character-creation completion / Campaign Turn 1 baseline entry at revision 1, followed by chronological completed Campaign Turn history. It does not accumulate intermediate character-creation save checkpoints.
- `art/art_log.md` — verified visual-reference paths and visual-reference continuity metadata; it does not override textual appearance owners.

Reusable repository-wide rules belong in `Rule/`. Reusable blank campaign skeletons belong in `New-Sheets/`. A campaign's copied sheets may retain guidance from those skeletons, but only actual filled-in campaign state has canonical force.

## Append-first preservation

Campaign-state files may contain both current state and historical records, but those roles must not be confused.

### Chronological and historical sections

Chronological/history sections are append-first.

Add new information instead of rewriting, compressing, summarizing away, reorganizing, or deleting older historical information merely for neatness or brevity.

Preserve an earlier mutable value in `session_log.md`, a continuity-history section, or another appropriate chronological owner only when that earlier value matters to continuity or history.

### Current mutable state

Current mutable state fields must be updated in place during the appropriate approved reconciliation.

Do not preserve stale current values beside the new value merely because append-first preservation exists.

Examples include current HP, currency, quantities, charges, equipped state, current conditions, current location, quest status, party membership, shop stock, current relationship status, and other facts whose purpose is to represent the latest state.

## Corrections and legitimate removal

Rewrite, replace, or delete established material when it is necessary because:

- the material is factually wrong
- it conflicts with a newer explicit player correction
- it is an accidental duplicate or error
- leaving it unchanged would make current mechanics or state incorrect
- it represents legitimately replaced current state
- an item was sold, lost, used, consumed, destroyed, traded, transferred, or otherwise legitimately removed
- the player explicitly requests the change

When correcting historical information, make the smallest practical edit and preserve useful history whenever possible by marking older information corrected or superseded.

If conflicting current facts cannot be resolved from the existing authorities, do not silently choose one. Use `RULE_AUTHORITY_AND_HIERARCHY.md` and obtain the player's direction when necessary.

## Non-gameplay corrections and repository maintenance

A correction or maintenance edit made **outside an active Campaign Turn** is not a Campaign Turn and is not a new campaign save merely because repository files are written.

Examples include:

- correcting a transcription, data-entry, formatting, path, or synchronization error
- applying the player's explicit correction to assistant-created canon
- repairing a duplicated or stale mirror so it matches its authoritative owner
- correcting a historical entry while preserving useful correction context
- adding or correcting non-gameplay metadata such as a verified reference-art path
- maintaining copied guidance, templates, relative links, or campaign-local rule text without inventing an in-world event

For such work:

1. determine the authoritative owner of the affected fact or metadata
2. make the smallest practical correction in that owner
3. update every required mirror or dependent reference so the repository remains internally consistent
4. preserve useful historical context when correcting a chronological record
5. verify the affected files after writing
6. do **not** create a Campaign Turn Step
7. do **not** change `campaign_turn_number`
8. do **not** increment `save_revision`
9. do **not** append a normal completed-Campaign-Turn entry to `session_log.md`

A repository commit made for this maintenance is an implementation/history record, not a numbered campaign save revision.

If the player explicitly changes a campaign fact between Turns as a correction, clarification, or retcon rather than as an in-fiction action, handle it under this non-gameplay correction rule. If the change is meant to happen **in the fiction as gameplay**, it belongs in a Campaign Turn instead.

If a Campaign Turn is already `in_progress`, do not silently alter its completed base state underneath the ledger. Correct the active Turn record when the error belongs to the Turn itself; otherwise reconcile or defer a permanent-base correction as needed so the ledger and completed state cannot silently diverge.

## Permanent transfer destinations

At approved Campaign Turn reconciliation, transfer only persistent, continuity-relevant, or historically important results to their correct owners.

Typical destinations include:

- `character_sheet.md` — core-PC HP, conditions, abilities, character resources, textual appearance changes, synchronized Level/XP mirrors, and lasting personal/relationship state
- `NPC-state.md` — NPC HP, conditions, abilities, relationships, party status, textual appearance changes, master personal-possession ownership/quantities, shop stock/services changes, and other persistent NPC state
- `routine_item_prices.md` — explicit routine/basic classification changes and recurring Base Price additions or revisions, together with required vendor Base Price mirror updates
- `inventory.md` — detailed active item quantities, charges, currency, ammunition, consumables, equipment changes, evidence, owned-item snapshots/state, and other possessions for core PCs and current party NPCs
- `world_state.md` — persistent locations, quests, factions, discoveries, clues, unresolved threads, and world consequences
- `session_log.md` — the revision-1 character-creation completion entry or completed Campaign Turn summaries and continuity-critical events
- `art/art_log.md` — newly established visual-reference paths or reference metadata when relevant
- `active_game.json` — completed Campaign Turn, `current_scene_name`, completed location, character-creation completion state, authoritative `xp_mode` and `character_advancement`, `save_revision`, and latest sync state

## Master/detail synchronization

When one fact legitimately has both a master record and a detailed active representation, keep them synchronized through the same completed-save reconciliation.

For a current party NPC, an ownership-changing item event may require both:

- `NPC-state.md` so the NPC's master ownership list remains correct
- `inventory.md` so the NPC's expanded active mechanical bookkeeping remains correct

Do not leave a master record stale merely because the same possession has a more detailed active representation elsewhere.

For a shop purchase, reconcile the connected transaction rather than updating isolated pieces: vendor business stock, buyer currency, acquired inventory, acquisition snapshot, stack result, and any required NPC master-ownership update must agree.

Detailed shop behavior is defined in `SHOPS_PRICING_AND_TRANSACTIONS.md`.

## Persistence discipline

During revision-0 character creation, finalized pre-game facts may be written directly to their state owners without opening the Campaign Turn ledger and without incrementing the revision.

After Campaign Turn 1 begins, do not rewrite permanent campaign files for ordinary gameplay changes while a Campaign Turn is still open. Stage those changes in `turn_save.md` and transfer them only through the approved save workflow.

Non-gameplay corrections and repository maintenance outside an active Campaign Turn follow the dedicated rule above and do not increment `save_revision`.

A file does not need fictional changes merely to prove it was checked. If nothing substantive changed, preserve it.

Character-creation persistence is defined in `CHARACTER_CREATION.md`. Campaign Turn staging is defined in `CAMPAIGN_TURNS_AND_STEPS.md`. Save approval, verification, and recovery are defined in `SAVES_VERIFICATION_AND_RECOVERY.md`.
