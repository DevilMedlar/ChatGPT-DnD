## Equipment and special effects

Meaningful items may track quantity, equipped/carried/stored state, damage or armor values, charges, durability, attunement or bonding, magical effects, curses, and hidden or unidentified properties.

Owned inventory must preserve enough established mechanical detail to resolve meaningful item effects correctly. Hidden or unidentified properties must not be revealed merely because they are stored for continuity.

Persistent file ownership, NPC possession mirroring, shop-stock ownership, and acquisition-snapshot rules live in `campaigns/GAME_MASTER_RULES.md`.

## Equipment ownership and special-effect continuity

Do not forget an item's established special effect simply because several scenes pass. Check `inventory.md`, `character_sheet.md`, `NPC-state.md`, and `world_state.md` as relevant before resolving an item-dependent effect.

For persistent NPCs, `NPC-state.md` owns the master list of what the NPC owns. `inventory.md` expands mechanically relevant possessions only while that NPC is currently traveling with the party. Shop stock belongs in the shop NPC's `NPC-state.md` record as business inventory until a party member actually acquires an item.

Standard official items that are still vendor stock use the compact linked storefront architecture below rather than duplicating full official mechanics into the shop record.

DevilMedlar's, Senpai's, and current party NPCs' carried equipment and resources are tracked below.

This file owns detailed mechanical bookkeeping for party-carried possessions: quantities, equipped/carried/stored state, charges, ammunition, durability, attunement, active item effects, currencies, consumables, and similar active inventory state.

For NPCs, `NPC-state.md` remains the **master ownership list**. This file expands mechanically relevant possessions only while that NPC is currently traveling with the party.

Shop stock does **not** belong here. Shop stock belongs in the relevant NPC's `NPC-state.md` record until a party member actually acquires an item.

Shared inventory ownership, NPC join/leave reconciliation, Campaign Turn staging, and persistence behavior are owned by `../GAME_MASTER_RULES.md`.

Party membership itself is authoritative in `NPC-state.md`.

Only NPCs currently traveling with the party should receive expanded active inventory records here. Their full identity, stats, relationships, conditions, off-party location, and master ownership lists remain in `NPC-state.md`.

## NPC Join / Leave Reconciliation

The shared NPC party-membership and possession-reconciliation procedure is owned by `../GAME_MASTER_RULES.md`.

This file must not be rewritten mid-Turn merely because an NPC joins, leaves, spends, gains, loses, or changes possessions. Use `turn_save.md` during an unfinished Campaign Turn. Create or expand a current-party NPC section here only through the shared completed-save workflow, and remove or collapse it only after that NPC's final active possessions have been reconciled back to the master ownership list in `NPC-state.md`.

## Item Detail Rule

For meaningful items, preserve enough information to resolve their mechanics correctly when relevant, including:

- item name and type
- quantity
- equipped / carried / stored state
- attack bonus or penalty
- damage dice and damage type
- armor / defense bonuses or penalties
- ability-score or movement modifiers
- charges / uses / ammunition
- recharge or refill rules
- durability / condition
- attunement / bonding
- granted abilities and their descriptions
- triggered effects and proc chances
- durations, saves, resistances, immunities, and stacking rules
- curses or hidden properties
- identified vs unidentified information

Do not expose a hidden or unidentified property merely because it is recorded for continuity.

## Acquired Official Item Snapshot Rule

When a party member acquires a standard official item from a shop, preserve the mechanically relevant facts needed to continue using that **owned campaign item** correctly. The snapshot belongs here rather than remaining dependent on a live external webpage.

Depending on the item, preserve the relevant combination of:

- item name and type
- quantity
- equipped / carried / stored state
- damage / armor / defense information
- attack or damage modifiers and damage type
- weapon properties or mastery
- ability-score, movement, or other stat effects
- charges / uses / ammunition
- recharge or refill rules
- durability / condition
- attunement / bonding
- granted abilities, triggered effects, durations, saves, resistances, requirements, limitations, or other mechanics needed to use the item
- the official acquisition reference when useful for provenance

Preserve the useful mechanics, not a word-for-word copy of the entire external published page.

Once those mechanics are established in Campaign 1 inventory, later changes to D&D Beyond or another external official reference do **not** silently rewrite the already-owned item. The owned item's recorded mechanics remain authoritative until Campaign 1 explicitly changes or updates that item through play or an approved rules change.

If an external item reference has moved or become inaccessible before the acquisition snapshot can be resolved, handle that item case by case and establish the required mechanics from an approved source or already-established campaign state before finalizing the owned-item snapshot.

During an active Campaign Turn, the acquisition and its snapshot remain staged in `turn_save.md` until approved reconciliation. If the buyer is a current-party persistent NPC, reconcile the NPC's master ownership list in `NPC-state.md` as part of the same completed save.

## Inventory Stack Compatibility

A newly acquired copy may merge with an existing inventory quantity/stack only when the existing owned item and the new item have compatible established mechanics **and** compatible relevant instance state.

Sharing the same item name is not enough. Same-name items with different mechanical snapshots, charges, condition, attunement, modifications, or another meaningful state difference must remain separate entries unless Campaign 1 explicitly reconciles them to the same compatible state.

Compatible copies may merge normally when no mechanically meaningful difference requires separate tracking.

## Travel Resource Use

Track meaningful shared travel resources here when established, such as food, water, ammunition, mounts, fuel, camping supplies, or other party-consumed resources.

## Local Continuity Note

This file contains only Campaign 1 inventory state and inventory-specific mechanics/schema. Fresh-campaign isolation, append-first preservation, Campaign Turn staging, and completed-save transfer rules are inherited from `../GAME_MASTER_RULES.md`.

`NPC-state.md` remains the master ownership list for each persistent NPC; this file remains the detailed active bookkeeping owner for possessions carried by the current party.
