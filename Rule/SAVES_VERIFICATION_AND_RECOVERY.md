The complete lifecycle and recovery behavior are owned by `campaigns/GAME_MASTER_RULES.md`.

Detailed save, verification, correction, and recovery rules live in `campaigns/GAME_MASTER_RULES.md`.

### Confirmation Gate 1: save approval

Before any permanent transfer:

1. review every recorded Step and verify the proposed Final Turn State is fully consistent with the recorded actions, rolls, damage, healing, resource use, movement, scene changes, discoveries, and results
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

### Reconciliation after save approval

After Confirmation Gate 1 is approved:

1. transfer only the approved persistent, continuity-relevant, or historically important results to their proper permanent owners
2. synchronize master/detail representations when one fact must exist in multiple bookkeeping locations, including current-party NPC possession changes in both `NPC-state.md` and `inventory.md`
3. when PC advancement changed, synchronize the Level/XP mirrors in `character_sheet.md` with the approved `level`, `xp_current`, and `xp_next_level` values that will be stored authoritatively in `active_game.json.character_advancement`
4. when a shop purchase occurred, reconcile the connected transaction together: update the shop business stock in `NPC-state.md`, decrease the buyer's currency by the approved Final Transaction Price, add the acquired item to the buyer's `inventory.md` record, preserve the acquisition-time mechanics snapshot, apply the approved compatible/separate stack result, and update the buyer's `NPC-state.md` master ownership too when the buyer is a current-party persistent NPC; do not permanently apply only one side of the transaction
5. when a routine/basic recurring Base Price changed, update `routine_item_prices.md` and every currently stocked vendor row that mirrors that item's Base Price in the same completed save
6. append the completed Campaign Turn checkpoint to `session_log.md`
7. prepare `active_game.json` as the completed-state marker using the completed `campaign_turn_number`, the approved final `Current Scene` as `current_scene_name`, the completed location, and the authoritative completed PC advancement state
8. increment `save_revision` exactly once for the completed permanent save
9. do **not** reset the Turn ledger as part of this permanent save

Whenever tooling permits an atomic multi-file commit, commit the supporting permanent-state updates, `session_log.md`, and completed `active_game.json` revision together in one permanent-save commit. The complete temporary ledger remains intact.

If permanent files must be written sequentially, update supporting permanent files first and update `active_game.json` last.

### Permanent save verification

After the permanent writes land, do not assume the save succeeded merely because the writes returned successfully.

Read/check the affected permanent files again and compare them with the player-approved Final Turn State and Exact Planned Permanent Transfers.

Verify at minimum:

- expected character-state changes landed correctly
- when PC advancement changed, every `character_sheet.md` Level/XP mirror exactly matches the authoritative `active_game.json.character_advancement` values
- expected inventory/resource changes landed correctly
- when a shop purchase occurred, vendor quantity, buyer currency, acquired inventory, acquisition snapshot, and stack result all match the approved transaction
- when a routine/basic item is stocked or its recurring Base Price changes, the vendor row's Base Price exactly matches the authoritative current value in `routine_item_prices.md`
- required NPC master/detail records agree when applicable
- when persistent NPCs are created or cross-referenced, stable NPC IDs are unique, unchanged, and agree across every affected file
- required world/clue changes landed correctly
- `session_log.md` contains the completed Campaign Turn checkpoint
- `active_game.json` contains the completed `campaign_turn_number`
- `active_game.json.current_scene_name` matches the approved final `Current Scene`
- `save_revision` advanced exactly once
- every approved planned transfer is accounted for
- no unrelated campaign state was changed
- no unresolved result remains stranded only in the temporary ledger

If verification fails, keep the Turn ledger intact, do not request reset, and reconcile the permanent state until it matches the approved final state.

When verification passes:

1. set `Status` to `saved_awaiting_reset`
2. preserve the full completed Turn ledger as a safety copy
3. send the player a compact save-completion report confirming the completed Campaign Turn, save revision, important final state, and successful verification
4. explicitly state that `turn_save.md` has **not** been reset
5. ask: `Confirm reset for Campaign Turn N+1? Yes / No`

A checkpoint commit that only records the verified `saved_awaiting_reset` ledger state does not increment `save_revision`.

### Confirmation Gate 2: reset approval

The successful permanent save does **not** automatically erase its temporary source ledger.

If the player says **No**:

- remain `saved_awaiting_reset`
- keep the completed Turn events, Final Turn State, planned transfers, and verification information intact
- do not replay or resave the completed Campaign Turn

If the player says **Yes**:

1. reset the temporary ledger
2. clear the completed Turn events and Current In-Turn State, reset `Pending Shop Transactions` to `None yet.` while preserving its template, clear pending transfers, final review, save verification, and prior reset approval
3. prepare the next Campaign Turn number
4. set `Status` to `ready`
5. set `Current Step` to `0`
6. set `Current Scene` to `None yet.`
7. set `Base save revision` to the newly completed `save_revision`

The reset is a cleanup/checkpoint operation. It does **not** increment `save_revision` because the permanent Campaign Turn save already completed.

### Campaign Turn recovery by status

Before beginning or continuing gameplay, read `turn_save.md` and use its status to determine recovery:

- `ready` — no unfinished Campaign Turn exists; the next Campaign Turn may begin.
- `in_progress` — resume the active Campaign Turn from the last completed permanent state plus the temporary overlay. `Current Step` and `Current Scene` in `turn_save.md` are the live gameplay position. Never start another Campaign Turn first.
- `ending_review` — the full Campaign Turn end was interpreted and the ledger is frozen. No permanent Campaign Turn write is authorized until the player confirms the final review.
- `reconciling` — the player approved the final state and the permanent save may be partially or fully written. Check `active_game.json`, the affected permanent files, and the approved Final Turn State before taking any action. Never replay the Campaign Turn automatically.
- `saved_awaiting_reset` — the permanent Campaign Turn save is complete and verified. Do not replay or resave it. Only the player's reset confirmation remains.

Also compare `Base save revision` with `active_game.json.save_revision` in context with the status:

- `in_progress` normally overlays the same base revision currently recorded in `active_game.json`.
- `reconciling` may temporarily coexist with a newer `active_game.json.save_revision` if the permanent save has already landed and is awaiting verification.
- `saved_awaiting_reset` intentionally references the older base revision while `active_game.json` already contains the newly completed revision.
- a base revision greater than the completed `active_game.json.save_revision` is inconsistent and must be reconciled before play continues.

Never silently discard an unfinished, frozen, reconciling, or saved-awaiting-reset Campaign Turn ledger.