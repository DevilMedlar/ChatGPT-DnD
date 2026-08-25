# Campaign Turns and Steps

## Campaign Turn

A **Campaign Turn** is the campaign's persistence/gameplay unit. It begins from one completed permanent save state and remains open until the whole connected gameplay unit is intentionally completed.

A Campaign Turn may contain any number of numbered Steps, including:

- scene setup and narration
- dialogue and decisions
- exploration and movement
- requested rolls and their results
- initiative setup
- multiple combat rounds
- every creature's individual combat turn
- attacks, damage, healing, conditions, item use, charges, ammunition, spell slots, class resources, and other changing state
- combat ending
- post-combat searching, dialogue, loot, clues, discoveries, movement, transactions, and other directly connected actions

Ending a creature's normal D&D combat turn does **not** end the Campaign Turn. Ending a combat round does **not** end the Campaign Turn. Combat itself does **not automatically** end the Campaign Turn if the connected gameplay sequence continues.

During active combat, an unqualified phrase such as `end turn` means the current creature's **Combat Turn** ends. It does not trigger Campaign Turn reconciliation.

ChatGPT, acting as GM/DM, determines when the connected gameplay unit has reached the end of the full Campaign Turn unless the player's newest explicit instruction clearly ends it sooner or later.

## Combat Turn and Combat Round

A **Combat Turn** is one creature's activation within initiative order.

A **Combat Round** is one initiative cycle through the active combatants.

Combat Turns and Combat Rounds exist inside a Campaign Turn and never cause `turn_save.md` to reset merely because they end.

## Live-state authority

Each campaign owns its own `turn_save.md`.

`active_game.json` represents the campaign's last completed permanent state header. `turn_save.md` stages the current unfinished Campaign Turn and overlays that completed state until the Turn is intentionally completed and saved.

- `active_game.json.campaign_turn_number` is the last completed Campaign Turn number, not the active unfinished Turn number.
- `active_game.json.current_scene_name` is the scene-name label at the last completed save. Before Campaign Turn 1, it may also describe the current pre-game character-creation context.
- `active_game.json` does **not** store a live Campaign Turn Step.
- `turn_save.md` owns the current/next Campaign Turn number, `Current Step`, and `Current Scene` for the unfinished Turn.
- While a Campaign Turn is `in_progress`, its `Current Scene` and `Current Step` are the authoritative live gameplay position and temporarily overlay the completed scene label in `active_game.json`.
- `current_scene_name` is a compact scene label, not a duplicate scene record; detailed location and world facts remain in their owning files.

The effective state while a Campaign Turn is open is:

`last completed permanent state + turn_save.md overlay`

## Starting a Campaign Turn

If this is Campaign Turn 1, `active_game.json.character_created` must be `true` and `active_game.json.campaign_turn_number` must still be `0`. Later Campaign Turns begin only after the prior Campaign Turn's completed permanent save and any required ledger reset have finished.

Before starting a Campaign Turn:

1. read the current completed canonical campaign files required for the scene
2. confirm `turn_save.md` is `ready` and no older Campaign Turn requires recovery, review, verification, or reset
3. use the current permanent files as the starting state rather than copying every starting value into `turn_save.md`
4. set `Campaign Turn` to the next Campaign Turn number
5. set `Status` to `in_progress`
6. set `Current Step` to `0`
7. set `Current Scene` to the completed `active_game.json.current_scene_name` unless the opening gameplay explicitly establishes a different scene before Step 0 is recorded
8. set `Base save revision` to the current `save_revision` in `active_game.json`

## Recording Steps

A Campaign Turn may contain as many numbered Steps as needed.

After each resolved Step:

1. append the relevant action/event, roll calculation when applicable, immediate result, and state deltas to `Turn Events`
2. update `Current Scene` whenever the effective scene changes
3. update `Current In-Turn State` with the compact latest effective values needed to continue or recover the Campaign Turn
4. update `Pending Permanent Transfers` when a result may need persistent reconciliation
5. when a shop transaction occurs, update `Pending Shop Transactions` with the connected vendor-stock, currency, inventory, pricing, and acquisition-snapshot state needed for reconciliation
6. do not repeatedly rewrite permanent campaign files for ordinary changing state inside the Campaign Turn
7. do not increment `save_revision`
8. stage every gameplay-caused persistent change in `turn_save.md` until save approval, including NPC party joins/leaves, permanent possession or shop changes, routine-item Base Price changes, and visual-continuity changes

`Current In-Turn State` is a maintained recovery snapshot, not a full copy of every permanent file and not a full state block repeated after every Step.

Whenever repository writing is available, persist `turn_save.md` after every resolved Step that contains a roll result, mechanical or resource-state change, scene/location change, discovery, relationship change, shop event, inventory change, combat-state change, or other continuity-relevant result before proceeding beyond the next player decision point.

A purely narrative Step with no meaningful state or recovery value may be left uncommitted until the next continuity-relevant Step. Step checkpoint commits do **not** increment `save_revision` and are not completed campaign saves.

## Compact roll recording

When recording rolls in `turn_save.md`, keep the calculation on one line whenever practical while preserving enough information to reconstruct it.

General pattern:

`**Actor rolls Roll Name:** dice/results + bonuses - penalties ×/÷ other effects = **final total**`

Attack pattern:

`**Attack — Attack Name:** dice/results + modifiers = **total** vs AC/target = **Hit/Miss**`

Damage/healing pattern:

`**Damage/Healing — Source:** dice/results + modifiers ×/÷ effects = **final amount**`

Preserve the dice expression and individual die results when useful, especially for multiple dice, advantage/disadvantage, critical hits, resistance, vulnerability, rerolls, or other effects. Initiative order should record each combatant's final initiative total beside the name.

## Ending a Campaign Turn

A creature's Combat Turn, a Combat Round, a combat encounter ending, a conversation ending, a rest beginning, or a scene becoming quiet is not enough by itself to end a Campaign Turn.

When ChatGPT determines that the full Campaign Turn has ended:

1. set `Status` to `ending_review`
2. freeze the Turn ledger
3. stop adding new gameplay actions
4. do **not** write permanent campaign files yet
5. do **not** reset `turn_save.md`

At this point `Current In-Turn State`, together with the final `Current Scene`, becomes the proposed **Final Turn State** for review.

Save approval, reconciliation, verification, recovery, and reset behavior are defined in `SAVES_VERIFICATION_AND_RECOVERY.md`.
