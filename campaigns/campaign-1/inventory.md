# Inventory — Campaign 1

DevilMedlar's, Senpai's, and current party NPCs' carried equipment and resources are tracked below.

This file owns detailed mechanical bookkeeping for party-carried possessions: quantities, equipped/carried/stored state, charges, ammunition, durability, attunement, active item effects, currencies, consumables, and similar active inventory state.

For NPCs, `NPC-state.md` remains the **master ownership list**. This file expands mechanically relevant possessions only while that NPC is currently traveling with the party.

Shop stock does **not** belong here. Shop stock belongs in the relevant NPC's `NPC-state.md` record until a party member actually acquires an item.

## DevilMedlar

### Equipped

### Carried / Stored

### Currency

### Consumables / Charges

### Important / Quest Items

### Expenditures

## Senpai

### Equipped

### Carried / Stored

### Currency

### Consumables / Charges

### Important / Quest Items

### Expenditures

## Current Party NPC Inventories

None established.

Party membership itself is authoritative in `NPC-state.md`.

Only NPCs currently traveling with the party should receive expanded active inventory records here. Their full identity, stats, relationships, conditions, off-party location, and master ownership lists remain in `NPC-state.md`.

### Current Party NPC Inventory Template

#### NPC Name

See master NPC record in `NPC-state.md`.

##### Equipped

###### Item Name

- **Quantity:**
- **Equipped:** Yes / No
- **Damage / armor / defense:**
- **Attack modifier:**
- **Damage modifier / type:**
- **Stat bonuses / penalties:**
- **Condition / durability:**
- **Charges / uses:**
- **Recharge:**
- **Attunement / bonding:**
- **Special effects:**
- **Hidden / unidentified properties:** Preserve without revealing unless legitimately learned
- **Notes:**

##### Carried

###### Item Name

- **Quantity:**
- **Current state:**
- **Mechanical effect:**
- **Charges / uses:**
- **Durability / condition:**
- **Notes:**

##### Consumables / Ammunition / Charges

###### Resource Name

- **Quantity / current uses:**
- **Maximum uses:**
- **Effect:**
- **Consumed on use:** Yes / No
- **Recharge / refill rule:**

##### Currency

- **Platinum:**
- **Gold:**
- **Electrum:**
- **Silver:**
- **Copper:**
- **Other currency:**

##### Tools / Utility

###### Tool Name

- **Quantity:**
- **Condition:**
- **Mechanical use:**

##### Important / Quest Items

###### Item Name

- **Quantity:**
- **Known purpose:**
- **Mechanical effect:**
- **Current state:**

##### Expenditures / Resource History

Record important expenditures when useful for continuity or reconciliation.

## NPC Join / Leave Reconciliation

If an NPC joins or leaves during an active Campaign Turn, do not change this permanent inventory immediately. Stage the membership transition and the NPC's effective carried items/resources in `turn_save.md`. Apply the permanent steps below only after Confirmation Gate 1 during approved Campaign Turn reconciliation.

### When an NPC joins the party

1. Update `NPC-state.md` to `In party: Yes` as part of the same approved reconciliation.
2. Keep the NPC's master ownership list in `NPC-state.md`.
3. Create or expand that NPC's section here with the carried items and resources that need active mechanical bookkeeping.
4. Reconcile any staged item, resource, charge, ammunition, currency, equipment, or condition changes from `turn_save.md`.
5. Do not copy unrelated stored possessions into active party inventory merely because the NPC owns them.

### During an unfinished Campaign Turn

Do not repeatedly rewrite this file after every small in-turn resource change.

Stage item use, charges, ammunition, consumables, damage to equipment, transfers, currency spending, NPC joins/leaves, and similar Campaign Turn Step changes in `turn_save.md`. The effective current state is the last completed inventory state plus the unfinished Campaign Turn overlay.

### When an NPC leaves the party

1. Reconcile the NPC's final quantities, equipment, currency, charges, acquired items, lost items, and other relevant possessions into the master ownership list in `NPC-state.md`.
2. Confirm the transfer is complete and any staged Campaign Turn state has been reconciled.
3. Update the NPC's party status and off-party location in `NPC-state.md` when known.
4. Only then remove or collapse the NPC's expanded section here.

An NPC leaving the party must not cause owned items to vanish from campaign continuity.

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

## Continuity Rule

Add items when they are actually acquired or established during this campaign. Preserve quantities, equipped/stored state, charges, durability, attunement, special effects, curses, and identified/unknown properties when relevant.

During an active Campaign Turn, newly acquired, spent, consumed, lost, transferred, or changed inventory remains staged in `turn_save.md` until approved Campaign Turn reconciliation.

`NPC-state.md` owns the master list of what each persistent NPC owns. This file owns detailed active bookkeeping for possessions of current party NPCs.

Do not import inventory from deleted files, repository history, previous chats, memory, or another campaign unless the player explicitly requests a specific import.
