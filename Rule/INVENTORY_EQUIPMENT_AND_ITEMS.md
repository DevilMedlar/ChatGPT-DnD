# Inventory, Equipment, and Items

## Inventory ownership

`inventory.md` owns detailed active mechanical bookkeeping for possessions carried by the core PCs and current party NPCs, including quantities, equipped/carried/stored state, charges, ammunition, durability, attunement, active item effects, currencies, consumables, and similar state.

For persistent NPCs, `NPC-state.md` remains the **master ownership list** whether the NPC is in the party or not. `inventory.md` expands mechanically relevant possessions only while that NPC is currently traveling with the party.

Shop stock is business inventory and belongs in the relevant shop NPC's `NPC-state.md` record until a party member actually acquires an item.

## Equipment and special-effect continuity

Meaningful items may track established and revealed facts such as:

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
- granted abilities and descriptions
- triggered effects and proc chances
- durations, saves, resistances, immunities, and stacking rules
- whether the item is identified or still unidentified

Owned inventory must preserve enough **known** mechanical detail to resolve meaningful item effects correctly.

Do not forget an item's established special effect merely because several scenes pass. Check `inventory.md`, `character_sheet.md`, `NPC-state.md`, and `world_state.md` as relevant before resolving an item-dependent effect.

Do not store an untold hidden property, unknown curse, undiscovered command word, secret effect, or other unrevealed answer. If the core PCs know only that an item is unidentified, record `Unidentified` and leave the unknown mechanics unstated until they are revealed through play.

The two core PCs share all item information either of them learns.

## NPC party inventory

Party membership itself is authoritative in `NPC-state.md`.

Only NPCs currently traveling with the party should receive expanded active inventory records in `inventory.md`. Their full identity, stats, relationships, conditions, off-party location, and master ownership lists remain in `NPC-state.md`.

If an NPC joins or leaves during an active Campaign Turn, stage the membership and possession changes in `turn_save.md` rather than rewriting permanent files immediately.

Create or expand a current-party NPC inventory section only through the completed-save workflow. When an NPC leaves, reconcile final quantities, currency, equipment, charges, acquired items, lost items, and other relevant possession changes back to the master ownership list in `NPC-state.md` before removing or collapsing the expanded inventory section.

Detailed party-membership behavior is defined in `NPCS_AND_PARTY_MEMBERSHIP.md`.

## Acquired official item snapshots

When a party member acquires a standard official item from a shop, preserve the mechanically relevant facts that have been established or revealed and are needed to continue using that **owned campaign item** correctly. The acquired item's known mechanics snapshot belongs in campaign inventory rather than remaining dependent on a live external webpage.

Depending on the item, preserve the relevant known combination of:

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
- granted abilities, triggered effects, durations, saves, resistances, requirements, limitations, or other revealed mechanics needed to use the item
- identified or unidentified status
- the official acquisition reference when useful for provenance

Preserve useful known mechanics, not a word-for-word copy of the entire external published page.

If the item is unidentified, do not snapshot mechanics the core PCs have not learned. Add those mechanics only when play reveals them.

Once known mechanics are established in campaign inventory, later changes to an external official reference do **not** silently rewrite the already-owned item. The owned item's recorded known mechanics remain authoritative until the campaign explicitly changes or updates that item through play or an approved rules change.

If an external reference has moved or become inaccessible before the known acquisition snapshot can be resolved, establish the required revealed mechanics from an approved source or already-established campaign state before finalizing the owned-item snapshot.

During an active Campaign Turn, the acquisition and its snapshot remain staged in `turn_save.md` until approved reconciliation. If the buyer is a current-party persistent NPC, reconcile the NPC's master ownership list in `NPC-state.md` as part of the same completed save.

## Stack compatibility

A newly acquired copy may merge with an existing inventory quantity or stack only when the existing owned item and the new item have compatible established mechanics **and** compatible relevant instance state.

Sharing the same item name is not enough. Same-name items with different known mechanical snapshots, charges, condition, attunement, modifications, identification state, or another meaningful state difference must remain separate entries unless the campaign explicitly reconciles them to the same compatible state.

Compatible copies may merge normally when no mechanically meaningful known difference requires separate tracking.

## Travel resources

Track meaningful shared travel resources when established, such as food, water, ammunition, mounts, fuel, camping supplies, or other party-consumed resources.

Shop sourcing and transaction rules are defined in `SHOPS_PRICING_AND_TRANSACTIONS.md`. General ownership and persistence rules are defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`.
