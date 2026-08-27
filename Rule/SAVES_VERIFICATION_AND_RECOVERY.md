# Saves, Verification, and Recovery

`CAMPAIGN_TURNS_AND_STEPS.md` governs Turn opening, Step recording, time staging, and Turn-end interpretation. This file governs save approval, permanent reconciliation, verification, recovery, reset, and revision numbering.

# Confirmation Gate 1: save approval

Before any permanent Campaign Turn transfer:

1. review every recorded Step
2. verify actions, rolls, resources, scene changes, clock changes, scheduled events, transactions, reproductive events, and consequences
3. resolve every missing, contradictory, uncertain, or unresolved temporary value
4. calculate the proposed Final Turn State
5. calculate the Exact Planned Permanent Transfers by destination file
6. show both to the player
7. ask:

`Confirm Campaign Turn N save? Yes / No / Corrections`

The review must include:

- Start Clock
- proposed End Clock
- total elapsed time
- material time-change reasons
- scheduled events and deadlines reached or crossed
- final scene and location
- all real persistent changes

## No

If the player says **No**:

- remain `ending_review`
- change no permanent files
- preserve the entire ledger

## Corrections

If the player gives **Corrections**:

- correct the temporary Turn record first
- recalculate clock-dependent values, schedules, Final Turn State, and planned transfers
- show the corrected review
- request confirmation again

## Yes

If the player says **Yes**:

- record approval
- set Status to `reconciling`
- begin permanent reconciliation

No permanent Campaign Turn save begins without Gate 1 approval.

# Permanent reconciliation

After approval:

1. transfer only approved new or changed persistent state and required mirrors
2. update supporting state owners before the completed-state marker when writes are sequential
3. synchronize PC Level/XP mirrors with `active_game.json.character_advancement`
4. synchronize NPC master/detail possessions with `inventory.md`
5. reconcile each shop transaction as one connected stock/currency/inventory/snapshot result
6. synchronize routine Base Prices and vendor mirrors
7. reconcile reproductive and family state:
   - core-PC state to `character_sheet.md`
   - NPC, child, egg, hybrid, biological-parent, adoptive-parent, and guardian state to `NPC-state.md`
   - due, laying, hatching, and developmental schedules to `world_state.md`
8. reconcile world, quest, clue, discovery, relationship, inventory, art, and other approved state
9. append one completed Campaign Turn checkpoint to `session_log.md`, including clock range when material
10. prepare `active_game.json` with:
   - completed Campaign Turn number
   - approved final scene
   - completed location
   - approved End Clock
   - authoritative completed PC advancement
   - incremented revision
   - compact synchronization note
11. increment `save_revision` exactly once
12. preserve the complete Turn ledger; do not reset it during the permanent save

Whenever tooling permits an atomic multi-file commit, use one permanent-save commit for the supporting state, `session_log.md`, and `active_game.json`.

If writes must be sequential, update supporting owners first and `active_game.json` last.

# Permanent save verification

After writes land, reread every affected file and compare it against the player-approved review.

Verify at minimum:

## Campaign header and time

- completed Campaign Turn number is correct
- final scene and location are correct
- `active_game.json.campaign_clock` exactly equals the approved End Clock
- clock day rollover and time arithmetic are correct
- `save_revision` advanced exactly once
- `last_sync_note` describes the completed revision

## Character and advancement

- every approved core-PC change landed
- Level/XP mirrors exactly match authoritative advancement
- species/class resources, conditions, relationships, reproductive state, parent state, and offspring links agree

## NPC, child, and family state

- stable IDs remain unique and unchanged
- biological parents, adoptive parents, guardians, children, and co-parents are correctly separated and cross-referenced
- hybrid traits, developmental milestones, fertility, pregnancy, egg, birth, and hatching state match the approved results

## Inventory and transactions

- currency, quantities, charges, equipment, ammunition, consumables, and item snapshots are correct
- vendor stock, buyer currency, acquired item, stack result, and NPC ownership reconcile
- routine Base Price mirrors agree

## World and chronology

- locations, quests, clues, discoveries, schedules, due dates, laying dates, hatching dates, deadlines, and consequences landed
- `session_log.md` contains the completed checkpoint with correct chronology
- every scheduled event crossed by the Turn's time passage was handled

## Completeness

- every approved planned transfer is accounted for
- no unrelated state changed
- no persistent result remains stranded only in `turn_save.md`
- no unchanged fact was duplicated as a new permanent record

If verification fails:

- preserve the full ledger
- do not request reset
- reconcile until permanent state matches the approved review

When verification passes:

1. set Status to `saved_awaiting_reset`
2. preserve the completed ledger as a safety copy
3. record the completed revision and verified completed clock
4. send the player a compact save-completion report
5. explicitly state that the ledger has not been reset
6. ask:

`Confirm reset for Campaign Turn N+1? Yes / No`

Moving the verified ledger to `saved_awaiting_reset` does not increment `save_revision`.

# Confirmation Gate 2: reset approval

A completed save does not automatically erase its temporary source ledger.

## No

If the player says **No**:

- remain `saved_awaiting_reset`
- preserve events, clocks, Final Turn State, transfers, and verification
- do not replay or resave the completed Turn

## Yes

If the player says **Yes**:

1. clear completed Turn events and live in-turn state
2. clear actual reproductive-event and shop-transaction records while preserving labeled templates and guidance
3. clear pending transfers, Final Review, verification, and prior reset approval
4. prepare the next Campaign Turn number
5. set Status to `ready`
6. set Current Step to `0`
7. set Current Scene to `None yet.`
8. set Base save revision to the completed revision
9. set Start Clock and Current In-Turn Clock to the completed `active_game.json.campaign_clock`
10. set Total Elapsed This Turn to zero
11. clear actual time-change records

Reset is a cleanup checkpoint and does not increment `save_revision`.

# Recovery by ledger status

Before play, read `turn_save.md` and recover by Status.

## `ready`

No unfinished Turn exists. The next Turn may begin after revision and clock checks.

## `in_progress`

Resume from permanent state plus the temporary overlay. Current Step, Current Scene, and Current In-Turn Clock are authoritative. Never start another Turn first.

## `ending_review`

The ledger is frozen. No permanent write is authorized until Gate 1 approval.

## `reconciling`

The player approved the save and permanent writes may be partial. Read the approved review, `active_game.json`, and every affected owner. Never replay the Turn automatically.

## `saved_awaiting_reset`

The permanent save is complete and verified. Do not replay or resave it. Only Gate 2 remains.

Never silently discard an unfinished, frozen, reconciling, or saved-awaiting-reset ledger.

# Base revision and clock checks

Interpret Base save revision with Status:

- a revision-1 ready ledger before Campaign Turn 1 uses Base save revision `1`
- an in-progress ledger normally overlays the same revision currently in `active_game.json`
- a reconciling ledger may coexist temporarily with a newer completed revision
- a saved-awaiting-reset ledger intentionally references the older base revision until reset
- a base revision greater than `active_game.json.save_revision` is inconsistent

Clock checks:

- a ready ledger's Start Clock and Current In-Turn Clock must match `active_game.json.campaign_clock`
- an in-progress ledger's Start Clock must match the completed clock at Turn opening
- Current In-Turn Clock must equal Start Clock plus recorded time changes
- a reconciling or saved-awaiting-reset ledger may show an older Start Clock while `active_game.json` already stores the approved End Clock
- clock inconsistencies must be reconciled before play continues

# Save revision rule

`active_game.json.save_revision` is the single save-revision counter.

## Revision 0

Revision 0 is the entire pre-game character-creation and backstory phase.

Finalized pre-game facts may be persisted without intermediate revision increments or session-log checkpoints.

## Revision 1

Revision 1 is established exactly once after confirmed character creation and the GM-authored opening frame.

At that transition:

- `character_created` becomes `true`
- `campaign_turn_number` remains `0`
- scene, location, and opening clock become established
- `save_revision` becomes `1`
- `turn_save.md` remains ready for Campaign Turn 1 with matching scene, base revision, and clock
- one completion entry is appended to `session_log.md`

Revision 1 does not itself begin Campaign Turn 1.

## Completed Campaign Turns

Starting a Turn does not increment the revision.

Each approved completed Campaign Turn increments it exactly once:

- character creation: revision `0`
- Campaign Turn 1 baseline: revision `1`
- completed Campaign Turn 1: revision `2`
- completed Campaign Turn 2: revision `3`
- and so on

Step checkpoints, review checkpoints, verification checkpoints, saved-awaiting-reset checkpoints, and reset operations do not increment it.

A file does not need fictional changes merely to prove it was checked. Preserve files with no substantive change.
