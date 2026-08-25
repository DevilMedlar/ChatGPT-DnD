# State Ownership and Persistence

## Active campaign selector

`campaigns/active_campaign.json` selects the campaign currently in play. It is a pointer, not a duplicate live save.

It identifies the active numbered campaign and the path to that campaign's `active_game.json`.

Live gameplay state does **not** belong in `active_campaign.json`. Do not rewrite it after ordinary Campaign Turns unless the active campaign selection, campaign path, or `active_game.json` pointer actually changes.

Changing campaigns changes the selector only. It does not move, merge, copy, or rewrite campaign state.

## Campaign isolation

Each numbered campaign owns its state inside its own folder.

Never write one campaign's character, NPC, relationship, inventory, world, quest, session, pricing, turn-save, advancement, or art-continuity state into another campaign folder unless the player explicitly requests a crossover or import.

Fresh-start canon restrictions are defined in `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`.

## Completed state and live Turn state

Each campaign's `active_game.json` is authoritative for that campaign's **last completed campaign state header**.

During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, Current Scene, and staged changes belong in that campaign's `turn_save.md`.

The effective state during an open Campaign Turn is the last completed permanent state plus the temporary `turn_save.md` overlay.

## File ownership

Within each numbered campaign:

- `active_game.json` — authoritative **last completed campaign state header**: completed `campaign_turn_number`, completed/pre-game `current_scene_name`, completed location, character-creation completion state, authoritative completed PC advancement through `xp_mode` and `character_advancement`, `save_revision`, and latest synchronization note. It does not store the live Campaign Turn Step.
- `turn_save.md` — temporary authoritative ledger for the current Campaign Turn: current/next Campaign Turn number, `Current Step`, `Current Scene`, numbered events, compact effective in-turn state, pending shop transactions, pending permanent transfers, final review, permanent-save verification, and reset approval.
- `character_sheet.md` — core-PC statistics, abilities, textual appearance canon, personal state, established relationship continuity, and synchronized human-readable Level/XP mirrors of `active_game.json`.
- `NPC-state.md` — persistent NPC stable IDs, identity, textual appearance canon, statistics, abilities, conditions, personality, relationships/attractions, knowledge/secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC-specific continuity.
- `routine_item_prices.md` — authoritative campaign-local classification and recurring Base Price reference for routine/basic repeat goods. Vendor rows mirror these Base Prices; this file does not own item mechanics, vendor quantities, merchant modifiers, Final Price, or inventory.
- `inventory.md` — detailed active mechanical bookkeeping for core PCs and possessions carried by current party NPCs, including owned-item mechanics snapshots and relevant owned-item state. For persistent NPCs, `NPC-state.md` remains the master ownership list.
- `world_state.md` — locations, factions, overall quests/missions, clues, discoveries, player-known world secrets, unresolved world threads, world consequences, and lightweight world-context references to persistent NPCs by stable NPC ID and current name.
- `session_log.md` — chronological completed character-creation checkpoint saves and completed Campaign Turn history.
- `art/art_log.md` — verified visual-reference paths and visual-reference continuity metadata; it does not override textual appearance owners.

Reusable rules belong in `Rule/`. Reusable blank sheet structure belongs in `New-Sheets/`. Neither should be used as duplicate live campaign state.

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

## Permanent transfer destinations

At approved reconciliation, transfer only persistent, continuity-relevant, or historically important results to their correct owners.

Typical destinations include:

- `character_sheet.md` — core-PC HP, conditions, abilities, character resources, textual appearance changes, synchronized Level/XP mirrors, and lasting personal/relationship state
- `NPC-state.md` — NPC HP, conditions, abilities, relationships, party status, textual appearance changes, master personal-possession ownership/quantities, shop stock/services changes, and other persistent NPC state
- `routine_item_prices.md` — explicit routine/basic classification changes and recurring Base Price additions or revisions, together with required vendor Base Price mirror updates
- `inventory.md` — detailed active item quantities, charges, currency, ammunition, consumables, equipment changes, evidence, owned-item snapshots/state, and other possessions for core PCs and current party NPCs
- `world_state.md` — persistent locations, quests, factions, discoveries, clues, unresolved threads, and world consequences
- `session_log.md` — chronological character-creation checkpoints or completed Campaign Turn summaries and continuity-critical events
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

Do not rewrite permanent campaign files for ordinary gameplay changes while a Campaign Turn is still open. Stage those changes in `turn_save.md` and transfer them only through the approved save workflow.

A file does not need fictional changes merely to prove it was checked. If nothing substantive changed, preserve it.

Campaign Turn staging is defined in `CAMPAIGN_TURNS_AND_STEPS.md`. Save approval, verification, and recovery are defined in `SAVES_VERIFICATION_AND_RECOVERY.md`.
