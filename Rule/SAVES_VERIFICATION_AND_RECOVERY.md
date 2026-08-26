# Saves, Verification, and Recovery

Campaign Turn opening, Step recording, and end interpretation are defined in `CAMPAIGN_TURNS_AND_STEPS.md`. This file governs approval, permanent reconciliation, verification, reset, recovery, and save revisions.

## Confirmation Gate 1: save approval

Before any permanent Campaign Turn transfer:

1. review every recorded Step and verify the proposed Final Turn State is fully consistent with the recorded actions, rolls, damage, healing, resource use, movement, scene changes, discoveries, transactions, and results
2. resolve any missing, contradictory, uncertain, or unresolved state in the temporary ledger first
3. determine the **Exact Planned Permanent Transfers** to the owning files
4. show the player both the Final Turn State and Exact Planned Permanent Transfers
5. ask: `Confirm Campaign Turn N save? Yes / No / Corrections`

If the player says **No**:

- remain `ending_review`
- change no permanent campaign files
- do not reset the ledger

If the player gives **Corrections**:

- correct the temporary Turn record first
- recalculate the Final Turn State and planned transfers
- show the revised review again
- ask for save confirmation again

If the player says **Yes**:

- record the approval
- set `Status` to `reconciling`
- begin permanent reconciliation

No permanent Campaign Turn save may begin without this confirmation.

## Reconciliation after save approval

After Confirmation Gate 1 is approved:

1. transfer only the approved persistent, continuity-relevant, or historically important results to their proper permanent owners
2. synchronize master/detail representations when one fact must exist in multiple bookkeeping locations, including current-party NPC possession changes in both `NPC-state.md` and `inventory.md`
3. when PC advancement changed, synchronize the Level/XP mirrors in `character_sheet.md` with the approved `level`, `xp_current`, and `xp_next_level` values stored authoritatively in `active_game.json.character_advancement`
4. when a shop purchase occurred, reconcile the connected transaction together: shop business stock, buyer currency, acquired inventory, acquisition snapshot, stack result, and any required NPC master-ownership update
5. when a routine/basic recurring Base Price changed, update `routine_item_prices.md` and every currently stocked vendor row that mirrors that item's Base Price in the same completed save
6. append the completed Campaign Turn checkpoint to `session_log.md`
7. prepare `active_game.json` as the completed-state marker using the completed `campaign_turn_number`, approved final `Current Scene` as `current_scene_name`, completed location, and authoritative completed PC advancement state
8. increment `save_revision` exactly once for the completed permanent save
9. do **not** reset the Turn ledger as part of the permanent save

Whenever tooling permits an atomic multi-file commit, commit the supporting permanent-state updates, `session_log.md`, and completed `active_game.json` revision together in one permanent-save commit. The complete temporary ledger remains intact.

If permanent files must be written sequentially, update supporting permanent files first and update `active_game.json` last.

## Permanent save verification

After permanent writes land, do not assume the save succeeded merely because the writes returned successfully.

Read the affected permanent files again and compare them with the player-approved Final Turn State and Exact Planned Permanent Transfers.

Verify at minimum:

- expected character-state changes landed correctly
- when PC advancement changed, every `character_sheet.md` Level/XP mirror exactly matches the authoritative `active_game.json.character_advancement` values
- expected inventory and resource changes landed correctly
- when a shop purchase occurred, vendor quantity, buyer currency, acquired inventory, acquisition snapshot, and stack result all match the approved transaction
- when a routine/basic item is stocked or its recurring Base Price changes, the vendor row's Base Price exactly matches the authoritative current value in `routine_item_prices.md`
- required NPC master/detail records agree when applicable
- persistent NPC stable IDs are unique, unchanged, and agree across affected files
- required world, quest, clue, discovery, and consequence changes landed correctly
- `session_log.md` contains the completed Campaign Turn checkpoint
- `active_game.json` contains the completed `campaign_turn_number`
- `active_game.json.current_scene_name` matches the approved final `Current Scene`
- `save_revision` advanced exactly once
- every approved planned transfer is accounted for
- no unrelated campaign state changed
- no unresolved result remains stranded only in the temporary ledger

If verification fails, keep the Turn ledger intact, do not request reset, and reconcile the permanent state until it matches the approved final state.

When verification passes:

1. set `Status` to `saved_awaiting_reset`
2. preserve the full completed Turn ledger as a safety copy
3. send the player a compact save-completion report confirming the completed Campaign Turn, save revision, important final state, and successful verification
4. explicitly state that `turn_save.md` has **not** been reset
5. ask: `Confirm reset for Campaign Turn N+1? Yes / No`

A checkpoint commit that only records the verified `saved_awaiting_reset` ledger state does not increment `save_revision`.

## Confirmation Gate 2: reset approval

A successful permanent save does **not** automatically erase its temporary source ledger.

If the player says **No**:

- remain `saved_awaiting_reset`
- keep the completed Turn events, Final Turn State, planned transfers, and verification information intact
- do not replay or resave the completed Campaign Turn

If the player says **Yes**:

1. reset the temporary ledger
2. clear the completed Turn events and Current In-Turn State
3. reset `Pending Shop Transactions` to `None yet.`; do not copy or preserve the reusable Shop Transaction Template inside the live ledger
4. clear pending transfers, final review, save verification, and prior reset approval
5. prepare the next Campaign Turn number
6. set `Status` to `ready`
7. set `Current Step` to `0`
8. set `Current Scene` to `None yet.`
9. set `Base save revision` to the newly completed `save_revision`

The reusable shop-transaction schema remains in `New-Sheets/turn_save.md`. Instantiate a concrete transaction record in the live ledger only when an actual shop transaction occurs.

The reset is a cleanup/checkpoint operation. It does **not** increment `save_revision` because the permanent Campaign Turn save already completed.

## Campaign Turn recovery by status

Before beginning or continuing gameplay, read `turn_save.md` and use its status to determine recovery:

- `ready` — no unfinished Campaign Turn exists; the next Campaign Turn may begin.
- `in_progress` — resume the active Campaign Turn from the last completed permanent state plus the temporary overlay. `Current Step` and `Current Scene` in `turn_save.md` are the live gameplay position. Never start another Campaign Turn first.
- `ending_review` — the full Campaign Turn end was interpreted and the ledger is frozen. No permanent Campaign Turn write is authorized until the player confirms the final review.
- `reconciling` — the player approved the final state and the permanent save may be partially or fully written. Check `active_game.json`, affected permanent files, and the approved Final Turn State before taking action. Never replay the Campaign Turn automatically.
- `saved_awaiting_reset` — the permanent Campaign Turn save is complete and verified. Do not replay or resave it. Only the player's reset confirmation remains.

Never silently discard an unfinished, frozen, reconciling, or saved-awaiting-reset Campaign Turn ledger.

## Base save revision checks

Compare `Base save revision` with `active_game.json.save_revision` in context with the ledger status:

- `in_progress` normally overlays the same base revision currently recorded in `active_game.json`
- `reconciling` may temporarily coexist with a newer `active_game.json.save_revision` if the permanent save has already landed and is awaiting verification
- `saved_awaiting_reset` intentionally references the older base revision while `active_game.json` already contains the newly completed revision
- a base revision greater than the completed `active_game.json.save_revision` is inconsistent and must be reconciled before play continues

## Save revision rule

`active_game.json.save_revision` is the campaign's single save-revision counter. No separate campaign phase or chat-session counter is used.

### Revision 0

`save_revision: 0` is a special **initialization baseline**, not a completed persistent save revision.

It may contain canonical bootstrap facts explicitly established by the player as part of creating the campaign, together with required initialization defaults. Those facts are canonical even though no character-creation checkpoint or Campaign Turn save has completed yet.

Revision 0 does not require a corresponding completed checkpoint entry in `session_log.md`. Do not retroactively invent revision 1 merely to account for legitimate bootstrap canon already present at initialization.

Revision 0 must not be used to bypass later save approval. Once initialization is complete, newly finalized persistent character-creation choices use the character-creation checkpoint workflow, and the first completed persistent checkpoint advances `save_revision` from `0` to `1`.

The detailed scope of bootstrap canon is defined in `CAMPAIGN_SETUP_ACTIVATION_AND_NAVIGATION.md` and `CHARACTER_CREATION.md`.

### Completed revisions

For a completed Campaign Turn or other completed persistent save revision after the initialization baseline:

1. determine all permanent campaign files that need real changes
2. prepare the canonical state and history updates
3. prepare `active_game.json` with the new completed authoritative state
4. increment `save_revision` by exactly `1` only for the completed permanent save
5. set `last_sync_note` to a compact description of what that completed revision represents
6. if a required permanent-state update fails or remains unresolved, do not pretend the save completed and do not finalize the revision until the permanent state is reconciled

Individual Campaign Turn Steps, status checkpoints, final-review checkpoints, `saved_awaiting_reset` checkpoints, Campaign Turn opening, and the later temporary-ledger reset do **not** increment `save_revision`.

Whenever atomic Git tooling is available, one completed persistent save revision should correspond to one permanent-state Git commit containing the synchronized supporting permanent files, `session_log.md` when applicable, and `active_game.json`. The temporary ledger is deliberately **not reset** in that commit.

If the environment cannot make one atomic multi-file permanent save and must write files sequentially, update supporting permanent files first and `active_game.json` last. Then verify the completed state before moving the temporary ledger to `saved_awaiting_reset`.

The later player-approved reset of `turn_save.md` is a separate cleanup/checkpoint operation and does not create another campaign save revision.

A file does not need fictional changes merely to prove it was checked. If nothing substantive changed, preserve it.

General state ownership, corrections, and legitimate removal are defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`.
