# MOCK Game Master Rules

> **MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file shows the proposed file-ownership and save workflow relevant to the NPC system. It is not the real Campaign 1 rules file.

# Game Master Rules — Mock Campaign

## Source of Truth

Use the `MOCK_*` files only to understand structure.

Nothing here is real campaign canon.

## File Ownership

### `MOCK_active_game.json`

Owns the last completed live campaign state:

- session number
- completed turn number
- next turn number
- scene
- current completed party location
- character levels
- XP
- save revision
- latest synchronization note

### `MOCK_turn_save.md`

Owns the current unfinished gameplay turn:

- chronological turn steps
- movement / positions
- HP changes
- resource changes
- item use
- ammunition
- spell slots
- charges
- conditions
- temporary effects
- current effective in-turn values
- pending end-turn transfers

While `Status: in_progress`, its state overlays the last completed permanent files.

### `MOCK_character_sheet.md`

Owns DevilMedlar and Senpai:

- identity
- level
- stats
- HP at last completed save
- abilities
- features
- conditions at last completed save
- appearance
- personal/relationship continuity

### `MOCK_NPC-state.md`

Owns persistent NPCs:

- identity
- appearance
- level / CR
- stats
- HP at last completed save
- abilities
- conditions
- personality
- motivations
- relationships
- knowledge
- secrets
- party membership
- location when not with party
- master personal possessions
- NPC-specific quest involvement
- shop/services
- shop stock/prices
- NPC continuity history

When an NPC joins the party, the NPC remains fully owned here. Do not copy the NPC's full stats into `character_sheet.md`.

### `MOCK_inventory.md`

Owns detailed item bookkeeping for:

- DevilMedlar
- Senpai
- current party NPCs

For current party NPCs:

- `MOCK_NPC-state.md` owns **what the NPC owns**.
- `MOCK_inventory.md` owns **expanded current mechanical item state** such as quantity, charges, durability, equipped status, ammunition, special effects, and carried/stored detail.

Before a party NPC leaves, reconcile the final detailed inventory back into the NPC's master ownership list.

### `MOCK_world_state.md`

Owns:

- locations
- factions
- quests
- clues
- discoveries
- world consequences
- world-facing NPC references

It should point to `MOCK_NPC-state.md` rather than duplicating NPC dossiers.

### `MOCK_session_log.md`

Owns chronological completed-turn history.

It should not duplicate every granular `turn_save` step.

### `MOCK_art_log.md`

Owns visual continuity and reference-art notes.

## NPC Location Rule

If an NPC is **not in the party**, `MOCK_NPC-state.md` stores where the NPC can currently or normally be found.

If an NPC **is in the party**, `MOCK_NPC-state.md` says `Current known location: With party`.

The completed party location belongs in `MOCK_active_game.json`.

Temporary movement and combat positions during an unfinished turn belong in `MOCK_turn_save.md`.

## Shop NPC Rule

A shopkeeper's NPC record may contain:

- business identity
- business location
- hours
- services
- current shop stock
- item prices
- quantities
- item descriptions
- known mechanics
- detailed mechanics for complex items
- discounts / markups
- restock behavior
- buy-back policy
- hidden/unidentified item properties when needed for GM continuity

### Shop stock vs personal possessions

Shop stock is business inventory and is separate from the NPC's personal possessions.

A blacksmith may personally own a longsword while also having three longswords for sale.

Do not treat all shop stock as personally carried by the NPC.

## Item Detail Rule

Item descriptions may include full mechanics when known, such as:

- attack bonus
- damage dice
- damage type
- armor bonus
- defense bonus
- Dexterity/Agility penalty
- proc/effect chance
- bleed/burn/poison effects
- duration
- saving throws
- charges
- cooldown/recharge
- uses
- attunement
- durability
- requirements
- granted abilities
- ability descriptions
- passive effects
- hidden/unidentified properties

Player-facing information must not reveal hidden properties before they are legitimately learned.

## Turn Save Workflow

A gameplay turn may contain multiple resolved steps.

After each step:

1. append the actor/action/result to `MOCK_turn_save.md`
2. update `Current In-Turn State`
3. update `Pending End-Turn Transfers`
4. optionally create a Git checkpoint commit
5. do **not** increment `save_revision`

## End Turn Workflow

At end turn:

1. freeze the turn save
2. review all turn events
3. determine persistent/continuity-relevant changes
4. prepare updates to the correct permanent files
5. append the completed-turn checkpoint to `MOCK_session_log.md`
6. prepare `MOCK_active_game.json` last
7. increment `save_revision` exactly 1
8. verify all required transfers
9. reset the turn save for the next turn
10. whenever tooling allows, commit the completed save as one atomic Git commit

## Recovery Rule

If `MOCK_turn_save.md` is `in_progress`, do not start a new gameplay turn.

Resume from:

`last completed permanent state + turn-save overlay`.

Never silently discard an unfinished turn.