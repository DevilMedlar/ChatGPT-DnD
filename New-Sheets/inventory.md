# Inventory

The player-controlled PC's, ChatGPT-controlled PC / co-protagonist's, and current party NPCs' carried equipment and resources are tracked below.

This file owns detailed mechanical bookkeeping for party-carried possessions: quantities, equipped/carried/stored state, charges, ammunition, durability, attunement, active known item effects, currencies, consumables, and similar active inventory state.

For NPCs, `NPC-state.md` remains the **master ownership list**. This file expands mechanically relevant possessions only while that NPC is currently traveling with the party.

Shop stock does **not** belong here. Shop stock belongs in the relevant NPC's `NPC-state.md` record until a party member actually acquires an item.

Inventory ownership and item mechanics are defined in `../Rule/INVENTORY_EQUIPMENT_AND_ITEMS.md`. NPC join/leave reconciliation is defined in `../Rule/NPCS_AND_PARTY_MEMBERSHIP.md`. Campaign Turn staging and persistence follow `../Rule/CAMPAIGN_TURNS_AND_STEPS.md`, `../Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md`, and `../Rule/SAVES_VERIFICATION_AND_RECOVERY.md`.

The two core PCs share all item information either of them learns. Do not store untold hidden item properties. If an item is unidentified, record that status without recording its unknown mechanics.

## Player-Controlled PC

### Equipped

### Carried / Stored

### Currency

### Consumables / Charges

### Important / Quest Items

### Expenditures

## ChatGPT-Controlled PC / Co-Protagonist

### Equipped

### Carried / Stored

### Currency

### Consumables / Charges

### Important / Quest Items

### Expenditures

## Current Party NPC Inventories

Party membership itself is authoritative in `NPC-state.md`.

Only NPCs currently traveling with the party should receive expanded active inventory records here. Their full identity, stats, relationships, conditions, off-party location, and master ownership lists remain in `NPC-state.md`.

### Current Party NPC Inventory Template

`NPC-####` is a template placeholder only. Replace it with the NPC's actual stable ID from `NPC-state.md` when creating the active inventory section.

#### NPC-#### — NPC Name

See the matching stable NPC ID in `NPC-state.md` for the master NPC record.

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
- **Identification state:** Identified / Unidentified
- **Known special effects:**
- **Notes:**

If the item is unidentified, leave unknown properties unstated until revealed.

##### Carried

###### Item Name

- **Quantity:**
- **Current state:**
- **Identification state:** Identified / Unidentified
- **Known mechanical effect:**
- **Charges / uses:**
- **Durability / condition:**
- **Notes:**

##### Consumables / Ammunition / Charges

###### Resource Name

- **Quantity / current uses:**
- **Maximum uses:**
- **Known effect:**
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
- **Known mechanical use:**

##### Important / Quest Items

###### Item Name

- **Quantity:**
- **Known purpose:**
- **Known mechanical effect:**
- **Identification state:** Identified / Unidentified
- **Current state:**

##### Expenditures / Resource History

Record important expenditures when useful for continuity or reconciliation.

## NPC Join / Leave Reconciliation

The NPC party-membership and possession-reconciliation procedure is defined in `../Rule/NPCS_AND_PARTY_MEMBERSHIP.md`.

This file must not be rewritten mid-Turn merely because an NPC joins, leaves, spends, gains, loses, or changes possessions. Use `turn_save.md` during an unfinished Campaign Turn. Create or expand a current-party NPC section here only through the shared completed-save workflow, and remove or collapse it only after that NPC's final active possessions have been reconciled back to the master ownership list in `NPC-state.md`.

## Item Detail Rule

For meaningful items, preserve enough **revealed** information to resolve their mechanics correctly when relevant, including:

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
- known granted abilities and descriptions
- known triggered effects and proc chances
- known durations, saves, resistances, immunities, and stacking rules
- identified or unidentified status

Do not store an unrevealed curse, unknown effect, hidden property, undiscovered command word, or other untold answer. Record only `Unidentified` until play reveals the mechanic.

## Acquired Official Item Snapshot Rule

When a party member acquires a standard official item from a shop, preserve the mechanically relevant facts the core PCs have learned and need to continue using that **owned campaign item** correctly. The known snapshot belongs here rather than remaining dependent on a live external webpage.

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
- known abilities, triggered effects, durations, saves, resistances, requirements, limitations, or other mechanics needed to use the item
- identification state
- the official acquisition reference when useful for provenance

Preserve useful known mechanics, not a word-for-word copy of the entire external published page.

If the item is unidentified, do not copy unknown mechanics into campaign state. Add mechanics only as they are revealed.

Once known mechanics are established in campaign inventory, later changes to D&D Beyond or another external official reference do **not** silently rewrite the already-owned item. The owned item's recorded known mechanics remain authoritative until the campaign explicitly changes or updates that item through play or an approved rules change.

If an external item reference has moved or become inaccessible before the known acquisition snapshot can be resolved, handle that item case by case and establish the required revealed mechanics from an approved source or already-established campaign state before finalizing the owned-item snapshot.

During an active Campaign Turn, the acquisition and its snapshot remain staged in `turn_save.md` until approved reconciliation. If the buyer is a current-party persistent NPC, reconcile the NPC's master ownership list in `NPC-state.md` as part of the same completed save.

## Inventory Stack Compatibility

A newly acquired copy may merge with an existing inventory quantity/stack only when the existing owned item and the new item have compatible established known mechanics **and** compatible relevant instance state.

Sharing the same item name is not enough. Same-name items with different known mechanical snapshots, charges, condition, attunement, modifications, identification state, or another meaningful state difference must remain separate entries unless the campaign explicitly reconciles them to the same compatible state.

Compatible copies may merge normally when no mechanically meaningful known difference requires separate tracking.

## Travel Resource Use

Track meaningful shared travel resources here when established, such as food, water, ammunition, mounts, fuel, camping supplies, or other party-consumed resources.

## Local Continuity Note

This file contains only campaign-local inventory state and inventory-specific mechanics/schema. Fresh-campaign isolation is defined in `../Rule/CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`. Append-first preservation and completed-save transfer rules are defined in `../Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md`. Campaign Turn staging and save approval are defined in `../Rule/CAMPAIGN_TURNS_AND_STEPS.md` and `../Rule/SAVES_VERIFICATION_AND_RECOVERY.md`.

`NPC-state.md` remains the master ownership list for each persistent NPC; this file remains the detailed active bookkeeping owner for possessions carried by the current party.
