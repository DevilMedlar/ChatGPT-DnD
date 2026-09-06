# Inventory

The player-controlled PC's, ChatGPT-controlled PC / co-protagonist's, and current party NPCs' carried equipment and resources are tracked below.

This file owns detailed mechanical bookkeeping for party-carried possessions: quantities, equipped/carried/stored state, charges, ammunition, durability, attunement, active known item effects, currencies, consumables, and similar active inventory state.

For NPCs, `NPC-state.md` remains the **master ownership list**. This file expands mechanically relevant possessions only while that NPC is currently traveling with the party.

Shop stock does **not** belong here. Shop stock belongs in the relevant NPC's `NPC-state.md` record until a party member actually acquires an item.

Inventory ownership and item mechanics are defined in `../../Rule/INVENTORY_EQUIPMENT_AND_ITEMS.md`. NPC join/leave reconciliation is defined in `../../Rule/NPCS_AND_PARTY_MEMBERSHIP.md`. Campaign Turn staging and persistence follow `../../Rule/CAMPAIGN_TURNS_AND_STEPS.md`, `../../Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md`, and `../../Rule/SAVES_VERIFICATION_AND_RECOVERY.md`.

The two core PCs share all item information either of them learns. Do not store untold hidden item properties. If an item is unidentified, record that status without recording its unknown mechanics.

## Player-Controlled PC

**Owner:** Cutlor Ashvale. The player approved loadout B, Foxguard, during revision-0 character creation. Items are identified and serviceable. Only the Potion of Healing is magical; no attunement, curse, or additional hidden property is established.

### Acquisition and Reconciliation

Starting funds use the gold alternatives instead of both preset equipment packages: Barbarian option B, 75 GP, plus Soldier option B, 50 GP, for 125 GP total. Do not also grant their option-A equipment or currency. The following accepted starting prices are acquisition facts, not merchant stock or new recurring Base Prices.

| Purchase | Quantity | Unit price | Total paid |
|---|---:|---:|---:|
| Ironknuckle Gauntlets, approved G2 | 1 pair | 15 GP per pair | 15 GP |
| [Shield, styled as Watchman's Round Shield](https://www.dndbeyond.com/equipment/8-shield) | 1 | 10 GP | 10 GP |
| [Javelin](https://www.dndbeyond.com/equipment/8-javelin) | 4 | 5 SP | 2 GP |
| [Explorer's Pack](https://www.dndbeyond.com/equipment/522-explorers-pack) | 1 bundle | 10 GP | 10 GP |
| [Traveler's Clothes](https://www.dndbeyond.com/equipment/541-travelers-clothes) | 1 set | 2 GP | 2 GP |
| [Pouch](https://www.dndbeyond.com/equipment/403-pouch) | 1 | 5 SP | 5 SP |
| [Dice Set](https://www.dndbeyond.com/equipment/449-dice) | 1 | 1 SP | 1 SP |
| [Healer's Kit](https://www.dndbeyond.com/equipment/515-healers-kit) | 1 | 5 GP | 5 GP |
| [Potion of Healing](https://www.dndbeyond.com/magic-items/8960641-potion-of-healing) | 1 | 50 GP | 50 GP |
| **Total spent** | | | **94 GP 6 SP** |

Copper reconciliation: 12,500 CP starting funds - 9,460 CP purchases = 3,040 CP remaining, recorded as 30 GP and 4 SP. No discounts, markups, quantity adjustments, debt, wages, or transfers from Seren. No named vendor or gameplay transaction is invented.

### Equipped

This is the selected starting loadout, not a narrated in-world action. Gauntlets and clothing are worn, the pouch is at the belt, and the shield is wielded in one hand; handedness remains unspecified.

| Item | Quantity / weight | State | Known mechanics / description |
|---|---|---|---|
| Ironknuckle Gauntlets | 1 pair / 2 lb. total | Worn; only an unoccupied hand can strike | Approved nonmagical Simple Melee weapon. Reach 5 feet; Strength attack +6; 1d6 + 4 Bludgeoning, or 1d6 + 6 with applicable Rage. Open fingers leave natural claws usable. Not armor; no AC bonus. No Light property or free extra attack. Sap requires a separate mastery selection, not yet made. Full local mechanics in `Rules/Campaign-1_Rules.md`. |
| Watchman's Round Shield | 1 / 6 lb. | Wielded; occupies one hand | Standard Shield, wood faced with iron, not a custom defensive power. +2 AC with Barbarian shield training: 19 with Unarmored Defense, 17 without the shield. Don or doff using a Utilize action. It does not automatically protect Seren or allow its occupied hand to make claw/gauntlet attacks. |
| Traveler's Clothes | 1 set / 4 lb. | Worn | Ordinary durable clothing fitted around existing Dragonkin anatomy. No armor bonus. Detailed colors, ornament, and styling remain open. |
| Belt Pouch | 1 / 1 lb. empty | Worn; holds currency and dice | Holds up to 6 lb. within one-fifth of a cubic foot. Mundane, not extradimensional. |

Natural claws are part of Cutlor's species, not purchased items. On each attack choose the applicable claw, gauntlet, or other weapon profile; do not add those profiles together. A hand holding the shield or a javelin cannot simultaneously make a gauntlet strike.

### Carried / Stored

No off-party storage is established. Explorer's Pack contents are itemized exactly once below: the bundle is not another object with duplicate contents or extra weight. The published complete bundle weight is 55 lb.

| Item | Quantity / weight | State / source | Known use |
|---|---|---|---|
| Javelin | 4 / 2 lb. each | Secured to carried gear; none drawn or thrown | Simple Melee weapon, 5-foot melee reach, Thrown range 30/120 feet. Strength attack +6; 1d6 + 4 Piercing, or 1d6 + 6 with applicable Rage, including a Strength-based throw. Beyond 30 feet: Disadvantage; beyond 120 feet: out of range. Slow mastery requires its own selection, not yet made. Track each javelin when thrown, recovered, or lost; not duplicated as ammunition. |
| [Backpack](https://www.dndbeyond.com/equipment/399-backpack) | 1 / 5 lb. empty | Carried, Explorer's Pack | Holds 30 lb. within 1 cubic foot. Pack the 10 ration portions, 2 Oil flasks, Tinderbox, and Healer's Kit inside: 26 lb. of contents; respect volume as well. Oversized gear is carried outside rather than exceeding capacity. |
| [Bedroll](https://www.dndbeyond.com/equipment/420-bedroll) | 1 / 7 lb. | Secured outside pack, Explorer's Pack | Bedding for one Small or Medium creature. While inside, automatic success on saving throws against extreme cold; not universal Cold-damage resistance. |
| [Oil](https://www.dndbeyond.com/equipment/393-oil) | 2 flasks / 1 lb. each | Sealed, Explorer's Pack | Each provides 6 hours of lamp/lantern fuel, 12 hours total. Cutlor owns no lantern in this loadout. Separate dousing/ignition uses follow the item rule; no oil is spent or automatically shared with Seren. |
| Rations | 10 daily portions / 2 lb. each | Packed, Explorer's Pack | Ten person-days of travel food; not ten days for both PCs. |
| [Rope](https://www.dndbeyond.com/equipment/415-rope) | 1 / 5 lb. | Coiled outside pack, Explorer's Pack | Ordinary climbing and securing gear. Use the official item rules for knots, breaking, binding, and escape; no automatic climb or grapple. |
| [Tinderbox](https://www.dndbeyond.com/equipment/434-tinderbox) | 1 / 1 lb. | Packed, Explorer's Pack | Bonus Action to light exposed fuel, such as a torch; 1 minute for another fire. Does not create fuel. |
| [Torch](https://www.dndbeyond.com/equipment/437-torch) | 10 / 1 lb. each | Bundled outside pack, all unlit, Explorer's Pack | Each burns for 1 hour, providing Bright Light for 20 feet and Dim Light for 20 more. Track each used torch. |
| [Waterskin](https://www.dndbeyond.com/equipment/442-waterskin) | 1 / 5 lb. full | Carried outside pack, Explorer's Pack | Full at setup, 4 pints. Track drinking and refills; no purification effect. |
| Dice Set | 1 / negligible weight | In belt pouch | Gaming equipment for Cutlor's Soldier proficiency; applicable Wisdom-based gaming checks +4. No bonus to unrelated dice results. |
| Healer's Kit | 1 / 3 lb. | Packed, accessible | 10 uses. Utilize action and 1 use stabilize an Unconscious creature at 0 HP without a Medicine check. This kit alone restores no HP. |
| Potion of Healing | 1 / 0.5 lb. | Securely carried, unopened | Common magical consumable; no attunement. Bonus Action to drink or administer to a creature within 5 feet. Restores 2d4 + 2 HP up to maximum; player rolls healing dice. Consumed on use. |

Total equipment weight, counting each pack component once: 79.5 lb., before coins. This is carried weight, not the backpack's internal load. No holding bag, mount, grappling hook, maul, spare shield, or alternative gauntlet design was acquired.

### Currency

- **Platinum:** 0 PP
- **Gold:** 30 GP
- **Electrum:** 0 EP
- **Silver:** 4 SP
- **Copper:** 0 CP
- **Other currency:** None
- **Reconciliation:** 125 GP - 94 GP 6 SP = 30 GP 4 SP. Seren's 35 GP is unchanged and separately owned.

### Consumables / Charges

- **Healer's Kit:** 10 / 10 uses
- **Potion of Healing:** 1 / 1 unopened potion
- **Rations:** 10 / 10 daily portions
- **Oil:** 2 / 2 full flasks, 12 potential lamp/lantern hours
- **Torches:** 10 / 10 unused
- **Water:** 4 / 4 pints
- **Thrown weapons:** 4 / 4 Javelins owned and carried; no separate ammunition stock
- **Attunements / rechargeable items:** None
- Class resources are recorded in `character_sheet.md`, not inventory charges. No resource was used during setup.

### Important / Quest Items

None established. Foxguard is the loadout name; the shield and gauntlets have no unlisted power, enchantment, or quest role.

### Expenditures

Revision-0 Foxguard approval: spend 94 GP 6 SP from the chosen 125 GP starting-gold allowance for the exact acquisition table above. Every purchased item and the remaining 30 GP 4 SP are reconciled together. No gameplay Step, elapsed campaign time, merchant stock, or recurring-price entry is created.

### Starting Equipment References

- Barbarian gold option and weapon/shield training: `https://www.dndbeyond.com/sources/dnd/br-2024/character-classes`
- Soldier gold option: `https://www.dndbeyond.com/sources/dnd/br-2024/character-origins`
- Standard equipment mechanics and weights: direct item references above and `https://www.dndbeyond.com/sources/dnd/br-2024/equipment`
- Ironknuckle Gauntlets: approved Campaign-1-only rule in `Rules/Campaign-1_Rules.md`
- Source/license attribution for SRD-derived mechanics remains in the character sheet.

## ChatGPT-Controlled PC / Co-Protagonist

**Owner:** Seren Ashvale. All following possessions are her revision-0 starting equipment. They are mundane, identified, and serviceable unless expressly noted. No item has charges, attunement, a curse, or an additional magical benefit.

### Acquisition and Reconciliation

- **Bard equipment option A:** Leather Armor, 2 Daggers, a Musical Instrument (lute), Entertainer's Pack, and 19 GP.
- **Wayfarer equipment option A:** 2 Daggers, Thieves' Tools, a Gaming Set (dice), a Bedroll, 2 Pouches, Traveler's Clothes, and 16 GP.
- **Reconciled totals:** 4 Daggers, 2 Bedrolls, 2 Pouches, and 35 GP. The duplicate Daggers and Bedrolls are intentional class/background equipment, not duplicated counting of one grant.
- **Pack counting:** Entertainer's Pack is a bundle description, not an additional object with another copy of its contents. Its complete contents are itemized below exactly once.
- **Purchases / sales:** None. No merchant, recurring price, or shop transaction is created by choosing starting equipment.

### Equipped

| Item | Quantity | State | Known mechanics / description |
|---|---:|---|---|
| Leather Armor | 1 | Worn | Light armor; AC 11 + Dexterity modifier, currently 14; no Strength requirement or inherent Stealth Disadvantage. Brown leather, mechanically ordinary. |
| Dagger | 2 | Sheathed at belt; neither drawn by default | Simple Melee weapon; Finesse, Light, Thrown 20/60 feet; +5 attack; 1d4 + 3 Piercing on a normal hit; melee reach 5 feet. Nick is the weapon's mastery property but Seren has no feature enabling it. |
| Traveler's Clothes | 1 set | Worn | Cream blouse, charcoal trousers, sturdy brown boots, and plum hooded cloak with simple leaf stitching. Cosmetic styling of the ordinary set; no bonuses. |
| Pouch | 2 | Worn at belt | Each can hold up to 6 pounds within one-fifth of a cubic foot. One holds currency; the other holds the dice set and small tools as space permits. |
| Lute, Hearthstring | 1 | Slung and carried; must be held when used as a focus | Mundane musical instrument. Seren is proficient; +7 on applicable Charisma instrument checks. Can serve as her Bard spellcasting focus for eligible Material components. No combat or magical bonus beyond ordinary focus use. |

### Carried / Stored

No off-party storage or additional property is established. Bulky bedding and other oversized gear are secured externally rather than assumed to fit without limit inside the Backpack.

| Item | Quantity | State / source | Known use |
|---|---:|---|---|
| Dagger | 2 | Packed spares, Wayfarer | Same known mechanics as the belt daggers. Total owned across both locations: 4. Track each thrown, recovered, lost, or transferred dagger. |
| Thieves' Tools | 1 set | Carried, Wayfarer | Seren has proficiency; +5 on relevant Dexterity tool checks. Ordinary lockpicking and trap disarming commonly use DC 15, but the actual task or item rule controls. Tool proficiency does not double the Proficiency Bonus when a skill also applies. |
| Gaming Set, dice | 1 set | Carried, Wayfarer | Ordinary game dice; no gaming-set proficiency or special luck bonus. Not a source of fabricated campaign rolls. |
| Backpack | 1 | Carried, Entertainer's Pack | Ordinary container; track capacity under the equipment rules. |
| Bedroll | 2 | Secured to carried gear | One from Entertainer's Pack, one from Wayfarer; bedding only, no automatic rest or healing. |
| Bell | 1 | Carried, Entertainer's Pack | Ordinary audible signal; no automatic alarm spell. |
| Bullseye Lantern | 1 | Carried and unlit, Entertainer's Pack | When fueled and lit, produces Bright Light in a 60-foot Cone and Dim Light for an additional 60 feet. Consumes Oil fuel as below. |
| Costume | 3 | Packed, Entertainer's Pack | One court-performer costume, one dockworker costume, one market-vendor costume; mundane garments. Wearing an appropriate costume grants Advantage on an ability check to impersonate the represented person or type, under the item rule, not general Advantage on all social checks. |
| Mirror | 1 | Carried, Entertainer's Pack | Handheld steel mirror; usable for inspection, looking around corners, or reflected signals. |
| Oil | 8 flasks | Sealed, Entertainer's Pack | Each unused flask supplies 6 hours of Lamp/Lantern fuel. See Consumables and known Oil mechanics. |
| Rations | 9 daily portions | Carried, Entertainer's Pack | Nine person-days of ordinary travel food, not nine days for the whole party. |
| Tinderbox | 1 | Carried, Entertainer's Pack | Lighting exposed fuel, such as a Lantern, takes a Bonus Action; another fire takes 1 minute under the item rule. Does not conjure fuel. |
| Waterskin | 1 | Full, Entertainer's Pack | Holds 4 pints of water; track use and refilling. No automatic purification. |

### Currency

- **Platinum:** 0 PP
- **Gold:** 35 GP
- **Electrum:** 0 EP
- **Silver:** 0 SP
- **Copper:** 0 CP
- **Other currency:** None
- **Source reconciliation:** 19 GP Bard + 16 GP Wayfarer = 35 GP; no expenditures

### Consumables / Charges

- **Rations:** 9 / 9 daily portions available
- **Oil:** 8 / 8 full unused flasks; total potential Lantern fuel 48 hours. No flask has been opened or fuel time spent.
- **Water:** 4 / 4 pints in one Waterskin
- **Ammunition:** None; four reusable Daggers are tracked individually by location and possession rather than duplicated as ammunition
- **Charged items / attunements:** None
- **Class/species/feat resources:** Owned by `character_sheet.md`, not counted again as inventory charges

#### Known Oil mechanics

As part of the Attack action, one attack can be replaced by throwing an Oil flask at a creature or object within 20 feet. The target makes a Dexterity save against DC 13 = 8 + Seren's Dexterity modifier 3 + Proficiency Bonus 2. On failure it is coated; Fire damage before the oil dries after 1 minute triggers the item's additional 5 Fire damage.

A Utilize action can instead coat a level 5-foot-square space within 5 feet. If lit, it burns for 2 rounds (12 seconds), dealing 5 Fire damage to a creature entering or ending its turn there, at most once per turn. These are the item's game mechanics, not an action taken during setup.

A flask used as Lamp or Lantern fuel provides 6 total burning hours, which may be split by extinguishing and relighting. Track the remaining fuel if partially used; do not merge a partial flask with the eight-full-flask starting total.

### Important / Quest Items

Hearthstring is Seren's familiar named lute and has personal significance but remains mechanically ordinary. No quest item, magic item, hidden property, extra keepsake, or unidentified possession is established.

### Expenditures

None. This is starting equipment selection, not a gameplay transaction. Campaign Day 1, 08:00:00 remains unchanged.

### Starting Equipment References

- Bard equipment: official SRD 5.2.1 p. 31 and `https://www.dndbeyond.com/classes/2190876-bard`
- Wayfarer equipment: official D&D Beyond complete example at `https://www.dndbeyond.com/posts/1785-the-backgrounds-and-origin-feats-in-the-2024`
- Item mechanics and Entertainer's Pack contents: SRD 5.2.1 pp. 89-100; complete bundle contents on p. 97
- The character sheet's Build Sources section provides SRD source and license attribution.

## Current Party NPC Inventories

Party membership itself is authoritative in `NPC-state.md`.

Only NPCs currently traveling with the party should receive expanded active inventory records here. Their full identity, stats, relationships, conditions, off-party location, and master ownership lists remain in `NPC-state.md`.

### Current Party NPC Inventory Template

`NPC-####` is a template placeholder only. Replace it with the NPC's actual stable ID from `NPC-state.md` when creating the active inventory section.

#### NPC-#### - NPC Name

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

The NPC party-membership and possession-reconciliation procedure is defined in `../../Rule/NPCS_AND_PARTY_MEMBERSHIP.md`.

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

This file contains only campaign-local inventory state and inventory-specific mechanics/schema. Fresh-campaign isolation is defined in `../../Rule/CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`. Append-first preservation and completed-save transfer rules are defined in `../../Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md`. Campaign Turn staging and save approval are defined in `../../Rule/CAMPAIGN_TURNS_AND_STEPS.md` and `../../Rule/SAVES_VERIFICATION_AND_RECOVERY.md`.

`NPC-state.md` remains the master ownership list for each persistent NPC; this file remains the detailed active bookkeeping owner for possessions carried by the current party.
