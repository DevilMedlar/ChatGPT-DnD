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
6. the shop row keeps only compact at-a-glance information such as category, named traits/mechanics, slots, or other useful tags
7. the **item name itself is the verified direct official link**
8. clicking the item name opens the freely viewable official item details; no separate official-item inspection layer is needed
9. homebrew, custom, unique, campaign-created, or mechanically modified items are **outside vendor mechanics and outside this store mock**
10. routine/basic repeat goods may use a stable recurring Base Price, while other official items may receive a reasonable GM-generated Base Price when they appear in stock
11. shop-specific markup or discount is applied after Base Price to determine the Final Price

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

There are two practical pricing cases in this mock.

### 1. Routine / Basic Repeat Goods

Ordinary goods that recur frequently can use a stable expected Base Price.

Examples might include:

- torches
- basic weapons
- basic armor
- ordinary tools
- common ammunition
- recurring consumables

If two merchants sell the same basic repeat item under normal circumstances, they can use the same established Base Price.

This prevents common goods from being randomly repriced every time they appear.

### 2. Other Official Items

For official items that are not treated as routine fixed-price goods, the GM may reasonably generate a Base Price when the item appears in stock.

That generated price should make sense for the item and campaign context rather than being arbitrary noise.

Useful considerations include:

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

After Base Price is established, the shop or transaction may modify it:

`final price = base price +/- applicable shop markup/discount`

Possible modifiers include:

- shop markup
- shop discount
- party relationship
- reputation
- faction standing
- negotiation
- local scarcity
- temporary events
- other established circumstances

The exact stacking, ordering, and rounding rules for multiple modifiers are **not decided by this mock**.

A markup or discount changes the Final Price. It does not need to rewrite the Base Price used for that stock listing.

---

## Current Shop Stock - Vendor Screen

This is the compact browse view, similar in spirit to a video-game vendor screen.

**The item name is the link.** Clicking an ordinary official item name opens its verified freely viewable official page directly.

`Key Mechanics` contains short recognizable information such as a weapon property, mastery, important effect, attunement note, slot count, or another useful glanceable trait. It is intentionally compact and does not replace the official item page.

| Item | Base Price | Qty | Category | Key Mechanics | Short Description |
|---|---:|---:|---|---|---|
| [Torch](https://www.dndbeyond.com/equipment/437-torch) | 1 cp | 20 | Adventuring Gear | Burns 1 hour; Light | Ordinary handheld light source. |
| [Dagger](https://www.dndbeyond.com/equipment/3-dagger) | 2 gp | 8 | Weapon | Finesse; Light; Thrown; Nick | Small versatile piercing weapon. |
| [Longsword](https://www.dndbeyond.com/equipment/4-longsword) | 15 gp | 4 | Weapon | Versatile; Sap | Martial slashing weapon usable one- or two-handed. |
| [Shield](https://www.dndbeyond.com/equipment/8-shield) | 10 gp | 3 | Armor / Shield | +2 AC while properly used | Standard defensive shield. |
| [Thieves' Tools](https://www.dndbeyond.com/equipment/495-thieves-tools) | 25 gp | 2 | Tool | Locks; Traps; Dexterity | Specialized tools for locks and traps. |
| [Bag of Holding](https://www.dndbeyond.com/magic-items/4581-bag-of-holding) | 400 gp | 1 | Wondrous Item | Extradimensional Storage | Magical container with much greater interior capacity than its exterior suggests. |

> **Mock-data warning:** The quantities and Base Prices in this table are design examples only. They are not Campaign 1 canon. Some routine/basic items may eventually use stable recurring Base Prices; other items may receive a reasonable GM-generated Base Price when stocked. D&D Beyond links provide official item mechanics/details, not price authority.

### Stock Ownership Rule

The vendor owns or records facts needed for the current shop state:

- current availability
- current quantity
- the Base Price being used for this stock listing
- shop markup / discount rules
- current shop- or party-specific modifiers
- compact vendor-screen tags
- short storefront description
- the verified direct official URL attached to the item name

For a routine/basic repeat good, the displayed Base Price can reuse its already established recurring price.

For another official item, the GM may generate a reasonable Base Price for that stock appearance.

The freely viewable official source owns the standard official item's published mechanical definition, but **not the campaign vendor price**.

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
Establish Base Price
   ├── routine/basic repeat good -> reuse stable expected Base Price
   └── other official item -> GM generates reasonable Base Price
        ↓
Apply this shop's markup/discount when calculating Final Price
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
Applicable shop markup / discount
        ↓
Final Transaction Price
        ↓ purchase
Vendor Qty decreases
        +
Party Inventory gains the purchased official item
```

The shop's responsibility ends after the stock and transaction state are updated. Any later inventory-specific or non-vendor changes to that item belong outside vendor mechanics.

---

# Same Item Pricing at Different Vendors

Pricing depends on whether the item is treated as a routine/basic repeat good or as another GM-priced official item.

## Routine / Basic Example

Two merchants selling the same ordinary repeat item can begin from the same established Base Price while still reaching different Final Prices through shop modifiers.

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

The official item mechanics remain the same because both links point to the official reference. Pricing remains campaign/vendor logic handled by the GM.

---

# Revised Option B Ownership Model

```text
Official D&D Catalog / Categories
└── discovery source for candidate official shop items

Freely Viewable Direct Official Item Page
└── standard published item mechanics / abilities / properties / details
    └── NOT campaign vendor price authority

Campaign Pricing
├── routine/basic repeat item
│   └── stable expected Base Price may be reused
│
└── other official item
    └── GM generates reasonable Base Price when stocked

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
    ├── category
    ├── compact key mechanics
    └── short description

Transaction
└── Base Price + applicable vendor modifiers -> Final Price
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
- Allows routine/basic repeat goods to stay predictably priced.
- Allows rarer or less routine official items to receive reasonable GM-generated Base Prices without requiring a global price database.
- Lets vendor markup/discount produce the Final Price after Base Price is established.
- Keeps current quantity vendor-owned.
- Leaves full standard official mechanics on the freely viewable official item page instead of copying them into `NPC-state.md`.
- Rejects inaccessible/paywalled item pages before they become normal shop stock.
- Keeps homebrew/custom/modified items completely outside vendor mechanics.

# Questions Still Open

- Campaign 1 still needs an explicit D&D rules/version baseline before official references can be standardized confidently.
- External official URLs or access rules can change, so links may occasionally need rechecking or replacement.
- We still need exact markup/discount stacking and rounding rules.
- The mock intentionally does not define a rigid formula for GM-generated Base Prices; pricing should remain reasonable and scale with item strength, rarity, usefulness, and comparable established prices.
- We still need to decide whether shop `Key Mechanics` and `Short Description` are always manually stored vendor-facing summaries or can sometimes be generated from the freely viewable official page.

---

**Status:** Design option only. Not approved. Not Campaign 1 canon.
