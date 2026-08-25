## Active campaign

`campaigns/active_campaign.json` selects the campaign currently in play. It is a pointer, not a duplicate live save.

Each campaign's own `active_game.json` is authoritative for that campaign's **last completed campaign state header**. During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

The two required core PCs are stored as PC-format character state through `character_sheet.md`, `active_game.json`, and `inventory.md`. Each campaign also owns its own routine-item Base Price reference, world state, chronological session history, temporary Campaign Turn ledger, and visual-reference log.

Update current mutable state in place when it changes through the approved persistence workflow.

## Active campaign

`active_campaign.json` is a pointer only. It identifies which numbered campaign is currently active and the path to that campaign's `active_game.json`.

Live gameplay state does **not** belong in `active_campaign.json`. Completed Campaign Turn, completed/pre-game scene name, location, character-creation completion state, completed PC advancement state, save revision, and the latest synchronization note belong in the active campaign's own `active_game.json`. The current unfinished Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

Campaign saves are isolated by folder:

- Campaign 1 saves to `campaign-1/` and uses `campaign-1/active_game.json`.
- Campaign 2 saves to `campaign-2/` and uses `campaign-2/active_game.json`.
- Campaign 3 saves to `campaign-3/` and uses `campaign-3/active_game.json`.
- Continue the same pattern for later campaigns.

Changing campaigns changes the pointer in `active_campaign.json`; it does not move, merge, or copy campaign state.

## Append-first preservation

Campaign-state files may contain both current state and historical records, but those roles must not be confused.

- **Chronological/history sections** are append-first. Add new Campaign Turn information instead of rewriting, compressing, summarizing away, reorganizing, or deleting older historical information merely for neatness or brevity.
- **Current mutable state fields** must be updated in place during the appropriate approved reconciliation. Do not preserve stale current values beside the new value merely because append-first preservation exists. Examples include current HP, currency, quantities, charges, equipped state, current conditions, current location, quest status, party membership, shop stock, current relationship status, and other facts whose purpose is to represent the latest state.
- Preserve an earlier mutable value in `session_log.md`, a continuity-history section, or another appropriate chronological owner only when that earlier value matters to continuity or history.
- Rewrite or delete established material when it is factually wrong, contradicts a newer explicit player choice, is an accidental duplicate/error, makes current mechanics incorrect, represents legitimately replaced current state, or the player explicitly requests the change.
- When a correction is needed, make the smallest practical edit and preserve useful history whenever possible by marking old historical information as corrected or superseded.
- Static documentation and shared rule files may be updated when the rules themselves change.

## Campaign save routing and file ownership

`active_campaign.json` in this `campaigns/` directory is a **campaign selector only**. It identifies the active numbered campaign and points to that campaign's `active_game.json`.

It is not the authoritative place for Campaign Turn state, character level, XP, location, character-creation state, save revision, or other changing gameplay state. Do not rewrite `active_campaign.json` after ordinary Campaign Turns unless the active campaign selection, campaign path, or `active_game.json` pointer actually changes.

Campaign saves are isolated:

- Campaign 1 saves only to `campaign-1/`.
- Campaign 2 saves only to `campaign-2/`.
- Campaign 3 saves only to `campaign-3/`.
- Continue the same rule for later campaigns.
- Never write one campaign's state into another campaign folder unless the player explicitly requests a crossover or import.

Within each numbered campaign, file ownership is:

- `active_game.json` — authoritative **last completed campaign state header**: completed `campaign_turn_number`, completed/pre-game `current_scene_name`, completed location, character-creation completion state, authoritative completed PC advancement through `xp_mode` and `character_advancement`, `save_revision`, and latest synchronization note. It does not store the live Campaign Turn Step.
- `turn_save.md` — temporary authoritative ledger for the current Campaign Turn: current/next Campaign Turn number, `Current Step`, `Current Scene`, numbered events, compact effective in-turn state, `Pending Shop Transactions`, pending transfers, final review, permanent-save verification, and reset approval.
- `character_sheet.md` — core-PC statistics, abilities, textual appearance canon, personal state, established relationship continuity, and synchronized human-readable Level/XP mirrors of `active_game.json`.
- `NPC-state.md` — persistent NPC stable IDs, identity, textual appearance canon, statistics, abilities, condition, personality, relationships/attractions, knowledge/secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC-specific continuity. It owns the stable cross-file identity key for each persistent NPC.
- `routine_item_prices.md` — authoritative campaign-local classification and recurring Base Price reference for routine/basic repeat goods. Vendor rows mirror these Base Prices; this file does not own item mechanics, vendor quantities, merchant modifiers, Final Price, or inventory.
- `inventory.md` — detailed active mechanical bookkeeping for core PCs and possessions carried by current party NPCs, including owned-item mechanics snapshots and relevant owned-item state. For NPCs, `NPC-state.md` remains the master ownership list.
- `world_state.md` — locations, factions, overall quests/missions, clues, discoveries, player-known world secrets, unresolved threads, world consequences, and lightweight world-context references to persistent NPCs by stable NPC ID and current name.
- `session_log.md` — chronological completed character-creation checkpoint saves and completed Campaign Turn history.
- `art/art_log.md` — verified visual-reference paths and visual-reference continuity metadata; it does not override textual appearance owners.
- `README.md` — static campaign documentation; do not use it as a duplicate live save.
- a local `GAME_MASTER_RULES.md`, when present — campaign-specific operating rules, agency rules, behavior rules, mechanical overrides, or exceptional premises that are not already owned by the shared rulebooks. Ordinary character/NPC/world facts belong in state files.

## Persistence

The detailed Campaign Turn workflow is defined above. The persistence rules below govern how that workflow writes permanent state.

### Permanent transfer destinations

At approved Campaign Turn reconciliation, transfer only persistent, continuity-relevant, or historically important results to their correct owners.

Typical destinations include:

- `character_sheet.md` — core-PC HP, conditions, abilities, character resources, textual appearance changes, synchronized human-readable Level/XP mirrors, and lasting personal/relationship state
- `NPC-state.md` — NPC HP, conditions, abilities, relationships, party status, textual appearance changes, master personal-possession ownership/quantities, shop stock/services changes, and other persistent NPC state
- `routine_item_prices.md` — explicit routine/basic classification changes and recurring Base Price additions or revisions, together with any required vendor Base Price mirror updates
- `inventory.md` — detailed active item quantities, charges, currency, ammunition, consumables, equipment changes, evidence, owned-item snapshots/state, and other possessions for core PCs and current party NPCs
- `world_state.md` — persistent locations, quests, factions, discoveries, clues, unresolved threads, and world consequences
- `session_log.md` — chronological character-creation checkpoint or completed Campaign Turn summary and continuity-critical events
- `art/art_log.md` — newly established visual-reference paths or reference metadata when relevant
- `active_game.json` — completed Campaign Turn/`current_scene_name`/location, character-creation completion state, authoritative `xp_mode` and `character_advancement`, `save_revision`, and latest sync state

For a **current party NPC**, an ownership-changing item event may require both `NPC-state.md` and `inventory.md` to be updated in the same completed save:

- update `NPC-state.md` so the NPC's master ownership list remains correct
- update `inventory.md` so the NPC's expanded active mechanical bookkeeping remains correct

Examples include consuming or gaining an item, spending or receiving currency, losing ammunition, transferring equipment, changing quantities, or permanently changing charges/uses.

For a **shop purchase**, reconcile the connected transaction rather than updating isolated pieces: update the shop NPC's business stock in `NPC-state.md`, decrease the buyer's currency by the approved Final Transaction Price, add the acquired item and acquisition snapshot to the appropriate `inventory.md` record, apply the compatible/separate stack result, and update the buyer's `NPC-state.md` master ownership too when the buyer is a current-party persistent NPC. For a routine/basic repeat good, verify that the shop row's Base Price matches `routine_item_prices.md`. Shop stock must not be treated as the shopkeeper's personal carried possessions.

Do not leave a master record stale merely because the same possession also has a more detailed active representation in `inventory.md`.

## Current-state routing

This README is static documentation and does not duplicate live campaign state.

- `active_game.json` owns the authoritative last completed Campaign 1 state header.
- `turn_save.md` owns the current unfinished Campaign Turn ledger and recovery status.
- `character_sheet.md` owns DevilMedlar and Senpai's established character and relationship facts.

## Canonical Campaign 1 files

- `GAME_MASTER_RULES.md` — Campaign 1-only core-PC mapping, agency, relationship-informed behavior rules, and any future Campaign 1-specific operating/mechanical overrides.
- `active_game.json` — authoritative last completed Campaign 1 state header, including completed Campaign Turn, completed/pre-game `current_scene_name`, location, character-creation completion state, completed PC Level/XP advancement state, and save revision.
- `turn_save.md` — temporary authoritative ledger for the current unfinished Campaign Turn: Campaign Turn number, Current Step, Current Scene, numbered events, current in-turn state, pending shop transactions, pending transfers, final review, permanent-save verification, and reset approval.
- `character_sheet.md` — DevilMedlar and Senpai statistics, abilities, traits, textual appearance canon, synchronized human-readable Level/XP mirrors, personal state, and established relationship continuity.
- `NPC-state.md` — persistent NPC master state and the Campaign 1 NPC record schema, including stable IDs, NPC mechanics/relationships, possessions, vendor/business state, and shop stock.
- `routine_item_prices.md` — authoritative Campaign 1 classification and recurring Base Price reference for routine/basic repeat goods.
- `inventory.md` — detailed active mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by current party NPCs, including owned-item mechanics snapshots and stack handling.
- `world_state.md` — Campaign 1 locations, factions, overall quests/missions, clues, discoveries, world consequences, player-known world secrets, unresolved threads, and lightweight NPC references.
- `session_log.md` — Campaign 1's chronological completed-save checkpoint history.
- `art/art_log.md` — Campaign 1 verified visual-reference paths and visual-reference continuity metadata. Textual appearance canon remains in the owning state files.

Shared ownership, Campaign Turn, NPC reconciliation, vendor/shop, save, recovery, fresh-start, and visual-reference staging rules are defined outside this folder in the inherited shared rulebooks.