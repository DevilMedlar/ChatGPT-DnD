# MOCK STORE OPTION B - Official D&D Shop References

> **DESIGN MOCK ONLY - NOT CAMPAIGN CANON**
>
> This root-level file exists only to test shop/vendor architecture for audit issue #13. Nothing in this file establishes Campaign 1 NPCs, shops, items, prices, mechanics, locations, loot, or story facts. Do not import any part of it into campaign canon unless the player explicitly approves that change later.

## Working Design Goal

Model shops more like a game vendor screen while avoiding a large local copy of official D&D item mechanics.

1. the vendor/shop owns business rules and current quantity
2. normal shop stock is selected from **official D&D items whose usable mechanics are freely viewable**
3. official shop items are found through the official D&D item/equipment catalog or its categories, then filtered to direct item pages whose useful mechanics are freely accessible
4. D&D Beyond is used as the reference for standard item mechanics, abilities, properties, type, rarity, description, and similar published details
5. D&D Beyond is **not the pricing authority for this shop system**
6. the **item name itself is the verified direct official link**
7. clicking the item name opens the freely viewable official item details; no separate official-item inspection layer is needed
8. `Category` and `Key Mechanics` are compact storefront fields derived from the current official reference; `Short Description` is compact generated storefront text
9. homebrew, custom, unique, campaign-created, or mechanically modified items are **outside vendor mechanics and outside this store mock**
10. routine/basic repeat goods **must use the established recurring Base Price for that specific item type whenever stocked**
11. non-routine official items may receive a reasonable GM-generated Base Price when they appear in stock
12. shop-specific markup or discount is applied after Base Price to determine the Final Price
13. a pricing factor must not be counted twice in the same stock listing or transaction
14. when an official item is purchased, the mechanically relevant facts needed to use that owned item are snapshotted into `inventory.md`; later changes to the external official page do not silently rewrite the already-owned campaign item

This is still a design mock. It does **not** finalize the campaign's D&D edition/rules baseline, exact markup math, restock math, buy-back rules, exact shop-generation rules, or a rigid formula for GM-generated prices.

---

# Vendor Scope Boundary

This store architecture covers **freely viewable official D&D items only**.

Homebrew, custom, unique, campaign-created, or mechanically modified items are not part of vendor stock mechanics in this design. Their discovery, storage, mechanics, inspection, and persistence belong outside this store mock.

---

# Official D&D Shop Source Rule

Normal shop stock should use official D&D items whose useful mechanics can be viewed freely.

For each candidate item:

1. choose an official item from the relevant official D&D catalog/category
2. open the item's direct official page before using it
3. verify that the page exposes enough of the actual item mechanics to use the item without requiring a purchase
4. if the page is only a teaser, marketplace redirect, ownership prompt, or otherwise hides the usable mechanics, do **not** use that item as normal shop stock
5. choose another freely viewable official item instead
6. place the verified direct official URL on the **item name itself** in `Current Shop Stock`

A page merely existing is not enough. The usable rules must actually be viewable for free.

The campaign does not need to build or maintain its own copy of the official item catalog. The official catalog/categories are used to find suitable items, and the direct item page is what the shop row links to.

D&D Beyond is a **mechanical reference**, not a shop-pricing database for this design. A listed or missing price on the official page does not control the campaign's vendor Base Price.

Because websites and access rules can change, a stored item link may be rechecked when that item is newly stocked again or when the existing reference no longer works.

## Rules-Version Note

This mock is testing the **shop/reference architecture**, not resolving audit issue #1 about the campaign's exact D&D fallback rules baseline.

Before this design becomes Campaign 1 canon, official shop references should be aligned with whichever D&D rules/version baseline Campaign 1 adopts.

---

# Mock Vendor

## Shop / Services

### Business-Level State

- **Business name:** Ash & Ember Outfitters
- **Business type:** Adventuring goods, weapons, armor, tools, consumables, and occasional freely accessible official magic items
- **Owner / operator:** Mock NPC only
- **Location:** Mock location only
- **Currency accepted:** Gold, silver, copper
- **Restock behavior:** Routine goods may restock regularly; uncommon or rare stock may restock slowly or unpredictably
- **Special-order capability:** Some freely accessible official items by arrangement when appropriate
- **Buy-back policy:** Example only; not finalized
- **Base markup / discount rules:** Example only; not finalized
- **Current party discount / markup:** Example only; not finalized
- **Reason for discount / markup:** Relationship, reputation, faction standing, negotiation, event, scarcity, or another established cause

---

# Pricing Model

## Base Price

`Base Price` is the starting campaign price before that shop's applicable markup or discount.

There are two pricing cases in this mock.

### 1. Routine / Basic Repeat Goods

Routine/basic repeat goods **must use the established recurring Base Price for that specific item type whenever stocked**.

Examples can include:

- torches
- basic weapons
- basic armor
- ordinary tools
- common ammunition
- recurring consumables

If two merchants sell the same item and that item is classified as a routine/basic repeat good, both listings start from that item's established recurring Base Price.

This rule applies **only** to items classified as routine/basic repeat goods. It does not require every item appearing at multiple merchants to share the same Base Price.

Different merchants may still reach different Final Prices through their own applicable markup or discount rules.

This prevents common goods from being randomly repriced every time they appear without forcing the same pricing behavior onto rarer or less routine items.

### 2. Other Official Items

For official items that are not treated as routine/basic repeat goods, the GM may reasonably generate a Base Price when the item appears in stock.

That generated price should make sense for the item and campaign context rather than being arbitrary noise.

Useful considerations can include:

- rarity
- mechanical power
- usefulness
- duration or number of uses
- whether the item is consumed
- how difficult it is to replace
- local scarcity
- item category
- comparable items already established in the campaign

The general pricing direction should remain intuitive. A stronger potion should normally cost more than a weaker potion. A more powerful special arrow should normally cost more than a weaker one. More powerful, rarer, or more useful equipment should generally trend upward in price.

The mock does not require a permanent global price registry for these items. The GM can establish a reasonable Base Price when the item appears.

## Final Price

After Base Price is established, applicable vendor or transaction modifiers can change the price paid:

`final price = base price +/- applicable shop markup/discount or other unused transaction modifier`

### Merchant Pricing vs. Context Pricing

A merchant's markup or discount is part of that shop's business/relationship pricing behavior.

Examples include:

- ordinary shop markup
- ordinary shop discount
- party relationship discount
- reputation-based treatment
- faction standing
- negotiation

Contextual market factors can also affect pricing, such as:

- local scarcity
- temporary shortages
- unusual demand
- temporary events
- another established market circumstance

### No Double Counting Rule

A pricing factor must not be applied more than once to the same stock listing or transaction.

If scarcity, rarity, local conditions, or another factor was already used when establishing that listing's Base Price, that **same factor** must not be applied again as a Final Price modifier.

For example:

```text
Scarcity already increased Base Price
        ↓
Do NOT apply scarcity again to Final Price
```

A normal merchant markup or discount may still apply afterward because it is a **different pricing factor** from the scarcity already included in Base Price.

Likewise, if a contextual factor was not used to establish Base Price, it may affect Final Price when appropriate, but only once.

The exact stacking, ordering, and rounding rules for multiple distinct modifiers are **not decided by this mock**.

---

## Current Shop Stock - Vendor Screen

This is the compact browse view, similar in spirit to a video-game vendor screen.

**The item name is the link.** Clicking an ordinary official item name opens its verified freely viewable official page directly.

`Category` and `Key Mechanics` are compact storefront fields derived from the current linked official item reference. They are presentation data, not an independent mechanical authority.

`Short Description` is compact generated storefront text based on the item and its current official reference. It is not a second canonical item definition.

| Item | Base Price | Qty | Category | Key Mechanics | Short Description |
|---|---:|---:|---|---|---|
| [Torch](https://www.dndbeyond.com/equipment/437-torch) | 1 cp | 20 | Adventuring Gear | Burns 1 hour; Light | Ordinary handheld light source. |
| [Dagger](https://www.dndbeyond.com/equipment/3-dagger) | 2 gp | 8 | Weapon | Finesse; Light; Thrown; Nick | Small versatile piercing weapon. |
| [Longsword](https://www.dndbeyond.com/equipment/4-longsword) | 15 gp | 4 | Weapon | Versatile; Sap | Martial slashing weapon usable one- or two-handed. |
| [Shield](https://www.dndbeyond.com/equipment/8-shield) | 10 gp | 3 | Armor / Shield | +2 AC while properly used | Standard defensive shield. |
| [Thieves' Tools](https://www.dndbeyond.com/equipment/495-thieves-tools) | 25 gp | 2 | Tool | Locks; Traps; Dexterity | Specialized tools for locks and traps. |
| [Bag of Holding](https://www.dndbeyond.com/magic-items/4581-bag-of-holding) | 400 gp | 1 | Wondrous Item | Extradimensional Storage | Magical container with much greater interior capacity than its exterior suggests. |

> **Mock-data warning:** The quantities and Base Prices in this table are design examples only. They are not Campaign 1 canon. Routine/basic repeat goods must use their established recurring Base Price when stocked; other official items may receive a reasonable GM-generated Base Price. D&D Beyond links provide official item mechanics/details, not price authority.

### Stock Ownership Rule

The vendor owns or records facts needed for the current shop state:

- current availability
- current quantity
- the Base Price being used for this stock listing
- shop markup / discount rules
- current shop- or party-specific modifiers
- the verified direct official URL attached to the item name

For a routine/basic repeat good, the displayed Base Price reuses that specific item's established recurring Base Price.

For another official item, the GM may generate a reasonable Base Price for that stock appearance.

`Category`, `Key Mechanics`, and `Short Description` are storefront presentation fields derived or generated from the current linked official reference. They do not become a second authority for the item's permanent mechanics.

The freely viewable official source owns the standard official item's published mechanical definition while the item remains shop stock, but **not the campaign vendor price**.

The shop does **not** need:

- a separate official-reference column
- a local copy of the official item catalog
- a second locally maintained detailed copy of standard official mechanics
- a generated official-item inspection block that repeats the vendor row and then supplies the same link

For an ordinary official shop item, the compact stock row is the shop presentation and the linked item name is the route to full details.

---

# Official Item Details Flow

```text
Generate or restock vendor
        ↓
Choose candidate from official D&D catalog/category
        ↓
Open candidate's direct official item page
        ↓
Are usable mechanics freely viewable?
   ├── NO
   │    ↓
   │  Reject candidate for normal shop stock
   │  Choose another official item
   │
   └── YES
        ↓
Attach direct official URL to Item name
        ↓
Derive Category + Key Mechanics
Generate compact Short Description
        ↓
Establish Base Price
   ├── routine/basic repeat good -> MUST reuse established recurring Base Price
   └── other official item -> GM generates reasonable Base Price
        ↓
Apply each relevant pricing factor no more than once
        ↓
Apply this shop's applicable markup/discount when calculating Final Price
        ↓
Show compact Current Shop Stock row
        ↓
Player wants full mechanics/details
        ↓
Player clicks Item name
        ↓
Freely viewable official item page
```

No intermediate locally generated official-item inspection screen is required.

---

# Official Shop Categories

The exact category structure depends on the chosen D&D rules baseline, but normal shop stock can conceptually be sourced from official categories such as:

- Weapons
- Armor / Shields
- Adventuring Gear
- Tools
- Potions / Consumables when freely viewable
- Magic Items when freely viewable
- Other official equipment categories supported by the chosen rules baseline

Categories are for finding and organizing official items. They are not locally copied item definitions.

The shop row links to the **direct item page**, not merely to the category page.

---

# Free-Access Failure Behavior

If a candidate official item fails the free-access check, it is not used as normal shop stock under this design.

Do not wait until the player clicks an item during play to discover that its useful mechanics are inaccessible.

```text
Candidate Official Item
        ↓
Open direct official page
        ↓
Usable mechanics freely viewable?
   ├── YES -> link Item name and use candidate
   └── NO  -> reject candidate and choose another
```

---

# Purchased Official Item Transition

When an official shop item is bought:

```text
Base Price used for this stock listing
        +
Applicable pricing modifiers, each counted once
        ↓
Final Transaction Price
        ↓ purchase
Vendor Qty decreases
        +
Party Inventory gains the purchased official item
        ↓
Snapshot mechanically relevant owned-item facts into inventory.md
```

## Acquisition Snapshot Rule

At acquisition, `inventory.md` should preserve the mechanically relevant facts needed to continue using the purchased item correctly in Campaign 1.

For example, depending on the item, that can include:

- item name and type
- quantity
- damage / armor / defense information
- attack or damage modifiers
- damage type
- weapon properties or mastery
- charges / uses / ammunition
- recharge rules
- attunement
- granted abilities or effects
- relevant durations, saves, resistances, requirements, or other mechanics
- other active state required by `inventory.md`

The purpose is to preserve the campaign's owned-item mechanics, not to copy the entire external published page word-for-word.

`character_sheet.md` may show an equipment summary when useful, but `inventory.md` remains the detailed authoritative home for owned item mechanics.

Once the item has been acquired and its relevant mechanics have been recorded into campaign inventory, later edits to D&D Beyond or another external official reference do **not** automatically change that already-owned campaign item.

```text
Official page at time of purchase
        ↓
Relevant mechanics snapshot
        ↓
inventory.md
        ↓
Owned Campaign Item
```

If the external official item later changes:

```text
Future shop listings may use the then-current approved official reference

Already-owned campaign item
        ↓
keeps its established inventory mechanics
        ↓
unless Campaign 1 explicitly changes or updates that item through play or an approved rules change
```

The shop's responsibility ends after the transaction and acquisition transfer are reconciled. Later inventory-specific or non-vendor changes belong outside vendor mechanics.

---

# Same Item Pricing at Different Vendors

Pricing depends on whether the item is treated as a routine/basic repeat good or as another GM-priced official item.

## Routine / Basic Example

Two merchants selling the same item **when that item is classified as a routine/basic repeat good** must begin from that item's established recurring Base Price. They may still reach different Final Prices through shop modifiers.

```text
Established Torch Base Price: 1 cp

Ash & Ember Outfitters
Linked Torch - Base Price 1 cp - Qty 20
Shop modifier: none
Final Price: 1 cp

Another Vendor
Linked Torch - Base Price 1 cp - Qty 10
Shop modifier: +20%
Final Price: calculated from the same 1 cp Base Price
```

This does **not** mean every item shared by two merchants must have the same Base Price. The rule is scoped only to routine/basic repeat goods.

## Other Official Item Example

A less routine item does not require one permanent global Base Price in this mock.

```text
Ash & Ember Outfitters
Linked Bag of Holding
GM-generated Base Price for this stock appearance: 400 gp
Shop modifier: -10%
Final Price: calculated from 400 gp

Another Vendor
Linked Bag of Holding
GM-generated Base Price for this stock appearance: 475 gp
Shop modifier: +5%
Final Price: calculated from 475 gp
```

The official item mechanics remain the same while the item is shop stock because both links point to the official reference. Pricing remains campaign/vendor logic handled by the GM.

---

# Revised Option B Ownership Model

```text
Official D&D Catalog / Categories
└── discovery source for candidate official shop items

Freely Viewable Direct Official Item Page
├── standard published item mechanics / abilities / properties / details while item is shop stock
└── NOT campaign vendor price authority

Storefront Presentation
├── Category -> derived from official reference
├── Key Mechanics -> derived from official reference
└── Short Description -> compact generated storefront text

Campaign Pricing
├── routine/basic repeat item
│   └── MUST reuse that item's established recurring Base Price
│
└── other official item
    └── GM generates reasonable Base Price when stocked

Pricing Factors
└── each distinct factor may affect a listing/transaction no more than once

Vendor / Shop Record
│
├── Business-Level State
│   ├── business rules
│   ├── restocking
│   ├── buy-back policy
│   └── markup / discount rules
│
└── Current Shop Stock
    ├── linked official item name
    │   └── direct freely viewable official item page
    ├── Base Price used for this stock listing
    ├── current vendor quantity
    ├── derived Category
    ├── derived Key Mechanics
    └── generated Short Description

Transaction
└── Base Price + applicable distinct modifiers -> Final Price

Purchase
└── relevant mechanics snapshot -> inventory.md
    └── owned item remains mechanically stable unless Campaign 1 explicitly changes it
```

### Ordinary Official Item Details

```text
Current Shop Stock
        ↓
Click linked Item name
        ↓
Freely viewable direct official item page
```

---

# Strengths of This Revised Option B

- Uses the official D&D item catalog/categories instead of building a duplicate local official-item catalog.
- Filters shop candidates to item pages whose useful mechanics are freely viewable.
- Uses D&D Beyond for mechanics/details rather than pretending it is the campaign's price authority.
- Makes the item name itself the direct official link.
- Removes the extra `Free Official Reference` table column.
- Removes the redundant locally generated inspection layer for ordinary official shop items.
- Keeps normal shop rows compact and vendor-screen-like.
- Makes `Category` and `Key Mechanics` derived storefront data instead of competing mechanical authority.
- Makes `Short Description` generated storefront presentation rather than permanent mechanical truth.
- Requires routine/basic repeat goods to use their established recurring Base Price without extending that rule to non-routine items.
- Allows rarer or less routine official items to receive reasonable GM-generated Base Prices without requiring a global price database.
- Prevents the same scarcity, rarity, or other pricing factor from being counted twice in one listing/transaction.
- Lets vendor markup/discount produce the Final Price after Base Price is established.
- Keeps current quantity vendor-owned.
- Leaves full standard official mechanics on the freely viewable official item page while the item remains shop stock instead of copying them into `NPC-state.md`.
- Snapshots relevant mechanics into `inventory.md` when the item is acquired, preserving continuity for the owned campaign item.
- Prevents later external webpage changes from silently rewriting previously acquired equipment.
- Rejects inaccessible/paywalled item pages before they become normal shop stock.
- Keeps homebrew/custom/modified items completely outside vendor mechanics.

# Questions Still Open

- Campaign 1 still needs an explicit D&D rules/version baseline before official references can be standardized confidently.
- External official URLs or access rules can change, so links may occasionally need rechecking or replacement.
- We still need exact markup/discount stacking and rounding rules for multiple **distinct** modifiers.
- The mock intentionally does not define a rigid formula for GM-generated Base Prices; pricing should remain reasonable and scale with item strength, rarity, usefulness, and comparable established prices.

---

**Status:** Design option only. Not approved. Not Campaign 1 canon.
