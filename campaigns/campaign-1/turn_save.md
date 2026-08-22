# Turn Save — Campaign 1

This file is the temporary authoritative ledger for the current unfinished gameplay turn.

It stages step-by-step actions and in-turn state changes before those results are transferred into the permanent campaign files at end turn.

## Turn-Save Rules

Preserve this rules section when resetting the file for a new turn.

### Completed state vs. in-turn state

- `active_game.json` and the permanent campaign files represent the **last completed save revision**.
- While this file is marked `in_progress`, the state recorded here overlays that completed state for the current unfinished turn.
- Do not repeatedly rewrite the permanent campaign files during ordinary steps inside a turn just because HP, position, charges, resources, conditions, or similar temporary/current values changed.
- Record those changes here first.

### Starting a gameplay turn

When a new gameplay turn begins:

1. Confirm this file is `ready` and that no older unfinished turn needs recovery.
2. Set `Turn` to the gameplay turn being started.
3. Set `Status` to `in_progress`.
4. Set `Step` to `0` before the first resolved step.
5. Set `Base save revision` to the current `save_revision` in `active_game.json`.
6. Begin appending resolved steps under `Turn Events`.

### Recording turn steps

A turn may contain multiple steps.

After each resolved step, append enough information to reconstruct what happened and update the `Current In-Turn State` and `Pending End-Turn Transfers` sections when relevant.

A step should normally record:

- actor or source
- action or event
- roll/result when relevant
- immediate outcome
- state changes such as HP, position, resources, spell slots, charges, ammunition, item quantities, conditions, temporary effects, discoveries, or other relevant changes

Example pattern:

```text
### Step 3
Actor: Example Character
Action: Used a healing item.
Result:
- HP: 13 -> 16 (+3 HP)
- Healing item: 2 -> 1 (-1 item)
```

Whenever Git repository writing is available, a completed turn step may be checkpointed with a small Git commit so an interrupted turn can be recovered. A step checkpoint **does not** increment `save_revision`; it is not a completed campaign save.

### Current in-turn state

`Current In-Turn State` should contain the latest effective values needed to continue the unfinished turn without replaying every earlier line.

Examples include:

- current HP
- current positions
- remaining charges or consumables
- current spell slots or class resources
- active conditions and temporary effects
- initiative/combat status when relevant
- any other value that changed during the unfinished turn and is needed to continue correctly

The chronological `Turn Events` remains the explanation of how those values were reached.

### Pending end-turn transfers

`Pending End-Turn Transfers` is a checklist of persistent or continuity-relevant results that will need to be transferred to their proper permanent files at end turn.

Do not copy trivial temporary details into permanent files merely because they appeared during a turn. Transfer only information that belongs in the permanent campaign state or history.

Typical destinations include:

- `character_sheet.md` — DevilMedlar/Senpai HP, conditions, abilities, character resources, advancement, lasting personal state
- `NPC-state.md` — NPC HP, conditions, abilities, relationships, party status, and other persistent NPC state
- `inventory.md` — item quantities, charges, currency, ammunition, consumables, equipment changes, evidence, or other possessions
- `world_state.md` — persistent locations, quests, factions, discoveries, clues, and world consequences
- `session_log.md` — chronological completed-turn summary and continuity-critical events
- `art/art_log.md` — newly established visual continuity when relevant
- `active_game.json` — completed session/turn/scene/step/location/levels/XP/save revision/latest sync state

### End-turn reconciliation

When the gameplay turn ends:

1. Freeze this file. Do not add new gameplay actions while the end-turn save is being prepared.
2. Review all `Turn Events`, `Current In-Turn State`, and `Pending End-Turn Transfers`.
3. Determine which changes are persistent, continuity-relevant, or historically important.
4. Prepare the necessary updates to the correct permanent campaign files.
5. Add the completed-turn checkpoint to `session_log.md`.
6. Prepare the new completed state in `active_game.json` and increment `save_revision` by exactly 1.
7. Verify that every required transfer is represented in the prepared permanent state.
8. Reset this file for the next turn only as part of the successfully completed end-turn save.

Whenever Git tooling permits an atomic multi-file commit, the permanent file updates, completed `active_game.json` revision, session-log checkpoint, and reset of this file should be committed together in **one Git commit**.

One completed save revision should correspond to one completed Git commit whenever that atomic workflow is available.

If the environment cannot make one atomic multi-file commit and must write files sequentially:

1. update the supporting permanent files first
2. update `active_game.json` last with the new `save_revision`
3. reset this file only after the completed revision has successfully landed

Do not increment `save_revision` for individual turn steps.

### Recovery after interruption

Before starting a new gameplay turn, compare this file with `active_game.json`.

- If `Status` is `in_progress` and `Base save revision` equals the current `save_revision`, resume the unfinished turn. The state here overlays the last completed permanent state.
- If `Status` is `in_progress` but `Base save revision` is lower than the current `save_revision`, the file may be stale residue from a turn that already completed. Verify the permanent files and `session_log.md`; do **not** replay the turn automatically. Reset this file only after confirming the completed save already contains its results.
- If `Base save revision` is somehow greater than the current `save_revision`, treat the save state as inconsistent and reconcile it before continuing gameplay.
- Never silently discard an unfinished turn.

### Character creation

Character creation occurs before the first gameplay turn.

Each finalized character-creation step may update the appropriate permanent files and complete a normal save revision directly. Those finalized creation saves do not require an `in_progress` turn here unless actual gameplay has begun.

## Active Turn Data

- **Turn:** 1
- **Status:** ready
- **Step:** 0
- **Base save revision:** 0

## Turn Events

None yet.

## Current In-Turn State

None yet.

## Pending End-Turn Transfers

None yet.

## End-Turn Verification

- **Status:** not_started
- **Notes:** None.
