# Campaign Turns and Steps

## Campaign Turn

A **Campaign Turn** is the repository's connected gameplay and persistence unit. It begins from one completed permanent save state and remains open until the whole connected gameplay unit is intentionally completed, reviewed, approved, reconciled, verified, and later reset.

A Campaign Turn may contain any number of numbered Steps, including:

- narration, dialogue, decisions, exploration, and movement
- time passage and scheduled events
- requested player rolls and their results
- initiative, Combat Rounds, and individual Combat Turns
- attacks, damage, healing, conditions, spells, resources, ammunition, and item use
- relationships, reproductive checks, pregnancy or egg milestones, birth, hatching, and development
- shops, transactions, inventory, clues, quests, travel, rests, and consequences

A creature's Combat Turn, a Combat Round, a combat encounter, a conversation, a rest, or a scene ending does not automatically end the Campaign Turn.

During combat, an unqualified `end turn` ends the current creature's Combat Turn, not the Campaign Turn.

## Combat Turn and Combat Round

A **Combat Turn** is one creature's activation in initiative order.

A **Combat Round** is one complete initiative cycle and consumes 6 seconds of campaign time regardless of the number of combatants.

Combat Turns and Combat Rounds exist inside a Campaign Turn and never reset `turn_save.md` merely because they end.

# Live-state authority

`active_game.json` stores the last completed campaign header, including completed scene, location, clock, advancement, and revision.

`turn_save.md` stores the unfinished Campaign Turn overlay, including:

- current Turn number and status
- Current Step and Current Scene
- Base save revision
- Start Clock and Current In-Turn Clock
- time changes and elapsed time
- events, rolls, compact live state, transactions, reproductive events, and pending transfers

The effective state is:

`last completed permanent state + turn_save.md overlay`

While a Turn is open, its Current Scene and Current In-Turn Clock are the authoritative live values.

A scene label describes the fiction. It never requires the player-controlled PC to remain there, follow a hook, or make a predetermined choice.

# Revision-1 baseline for Campaign Turn 1

Character creation occurs at `save_revision: 0` under `CHARACTER_CREATION.md`.

After the player confirms completion, revision 1 becomes the permanent starting baseline for Campaign Turn 1.

Immediately before Campaign Turn 1 begins:

- `active_game.json.campaign_turn_number` is `0`
- `character_created` is `true`
- `save_revision` is `1`
- `current_scene_name` is the GM-authored opening scene label
- `current_location` is the actual opening location
- `campaign_clock` is the GM-established opening clock
- `turn_save.md.Campaign Turn` is `1`
- `turn_save.md.Status` is `ready`
- `turn_save.md.Current Step` is `0`
- `turn_save.md.Current Scene` matches the opening scene
- `turn_save.md.Base save revision` is `1`
- Start Clock and Current In-Turn Clock match `active_game.json.campaign_clock`

The opening frame does not choose the player's first action and does not itself create a gameplay Step.

# Starting a Campaign Turn

Before starting:

1. read the current rules and required permanent state
2. confirm `turn_save.md` is `ready`
3. recover any older unfinished, frozen, reconciling, or saved-awaiting-reset Turn instead of starting another
4. confirm Base save revision matches `active_game.json.save_revision`
5. confirm the ready ledger's clock matches `active_game.json.campaign_clock`
6. set the next Campaign Turn number
7. set Status to `in_progress`
8. set Current Step to `0`
9. initialize Current Scene from the completed scene unless opening fiction changes it
10. set Start Clock and Current In-Turn Clock to the completed clock
11. set Total Elapsed This Turn to zero

Starting a Turn does not increment `save_revision`.

# Recording Steps

After each resolved Step:

1. increment and record the Step number
2. append the relevant action or event
3. record every required player roll, calculation, and result
4. update Current Scene when the situation changes
5. update Current In-Turn State with compact effective values needed for continuation or recovery
6. stage every gameplay-caused persistent change in Pending Permanent Transfers
7. stage connected shop transactions together
8. stage reproductive checks and lifecycle events with exact clock, rolls, results, dates, and destinations
9. do not rewrite permanent campaign state for ordinary in-Turn changes
10. do not increment `save_revision`

Whenever repository writing is available, checkpoint `turn_save.md` after a resolved Step containing a roll, mechanical change, time change, scene/location change, discovery, relationship change, transaction, reproductive event, or other continuity-relevant result before the next player decision point.

A purely narrative Step with no recovery value may wait until the next meaningful checkpoint.

# Recording time

`CORE_GAME_MECHANICS.md` owns time arithmetic and common durations.

For every material time change:

1. identify the Step and activity
2. state the duration
3. record Start Clock, End Clock, and elapsed duration
4. update Current In-Turn Clock and Total Elapsed This Turn
5. check `world_state.md` for every scheduled event or deadline reached or crossed
6. resolve crossed events chronologically
7. update Current In-Turn State and pending transfers as needed

Do not advance time for out-of-fiction discussion.

Do not silently skip a scheduled event, effect expiration, rest completion, conception-limit boundary, due date, laying date, hatching date, or developmental milestone.

## Combat time

- One Combat Round consumes 6 seconds.
- Do not add 6 seconds for each combatant.
- If combat ends partway through a round and exact timing matters, use the completed-round count plus an explicitly justified approximation rather than pretending each initiative turn is a separate 6 seconds.

# Compact roll recording

Keep calculations reconstructable and compact.

General pattern:

`**Actor rolls Roll Name:** dice/results + bonuses - penalties = **final total**`

Attack pattern:

`**Attack — Name:** dice/results + modifiers = **total** vs target = **Hit/Miss**`

Damage or healing pattern:

`**Damage/Healing — Source:** dice/results + modifiers and effects = **final amount**`

Percentile pattern:

`**Percentile — Purpose:** tens d10 result, ones d10 result = **combined result** vs target = **outcome**`

Preserve individual dice for multiple dice, Advantage/Disadvantage, critical hits, rerolls, resistance, vulnerability, and any result needed for later verification.

# Ending a Campaign Turn

A quiet moment alone does not automatically end a Campaign Turn.

When the full connected gameplay unit has ended:

1. set Status to `ending_review`
2. freeze the ledger
3. stop adding new gameplay actions
4. do not write permanent state yet
5. do not reset the ledger
6. prepare the proposed Final Turn State
7. calculate the Exact Planned Permanent Transfers

The Final Turn Review must include:

- Campaign Turn Start Clock
- proposed End Clock
- total elapsed time
- material time-change reasons
- scheduled events and deadlines reached or crossed
- final scene and effective state
- every real persistent transfer grouped by destination

Unchanged permanent context is not a new transfer.

Save approval, reconciliation, verification, recovery, and reset are governed by `SAVES_VERIFICATION_AND_RECOVERY.md`.
