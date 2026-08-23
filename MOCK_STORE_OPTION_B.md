# MOCK STORE OPTION B - Free Official Shop Catalog

> **DESIGN MOCK ONLY - NOT CAMPAIGN CANON**
>
> This root-level file exists only to test shop/vendor architecture for audit issue #13. Nothing in this file establishes Campaign 1 NPCs, shops, items, prices, mechanics, locations, loot, or story facts. Do not import any part of it into campaign canon unless the player explicitly approves that change later.

## Working Design Goal

Model shops more like a game vendor screen while avoiding a large local copy of official D&D item mechanics.

1. the vendor/shop owns business rules
2. `Current Shop Stock` owns the vendor-specific base price and current quantity
3. normal shop stock is selected from **official D&D items whose usable mechanics are freely viewable**
4. official shop items are discovered through the official free item/equipment catalog or its categories, not through a locally maintained duplicate catalog
5. the shop row keeps only compact at-a-glance information such as category, named traits/mechanics, slots, or other useful tags
6. the **item name itself is the verified direct official link**
7. clicking the item name opens the full freely viewable official item details; no separate official-item inspection layer is needed
8. homebrew, custom, unique, campaign-created, or mechanically modified items are **outside vendor mechanics and outside this store mock**

This is still a design mock. It does **not** finalize the campaign's D&D edition/rules baseline, markup math, restock math, buy-back rules, or exact shop-generation rules.

---

# Vendor Scope Boundary

This store architecture covers **freely viewable official D&D items only**.

Homebrew, custom, unique, campaign-created, or mechanically modified items are not part of vendor stock mechanics in this design. Their discovery, storage, mechanics, inspection, and persistence belong outside this store mock.

---

# Official Free Shop Source Rule

Normal shop stock should use freely accessible official D&D items.

For each candidate item:

1. choose an official item from the relevant official catalog/category
2. open the item's direct official page before using it
3. verify that the page exposes enough of the actual item mechanics to use the item without requiring a purchase
4. if the page is only a teaser, marketplace redirect, ownership prompt, or otherwise hides the usable mechanics, do **not** use that item as normal shop stock
5. choose another freely viewable official item instead
6. place the verified direct official URL on the **item name itself** in `Current Shop Stock`

A page merely existing is not enough. The usable rules must actually be viewable for free.

The campaign does not need to build or maintain its own copy of the official item catalog. The official catalog/categories are used to find suitable items, and the direct verified item page is what the shop row links to.

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

### Price Meaning

`Base Price` is vendor-specific stock state.

The final narrated transaction price is calculated when a purchase is actually resolved:

`final price = base price +/- applicable markup/discount`

The exact stacking, ordering, and rounding rules for multiple modifiers are **not decided by this mock**.

A temporary relationship discount or markup does not rewrite the stored base price unless the vendor's base price itself permanently changes.

The official item page defines the standard item mechanics. The vendor record defines what this seller is asking before temporary transaction modifiers.

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

> **Mock-data warning:** The quantities and vendor-specific base prices in this table are design examples only. They are not Campaign 1 canon. The linked item names exist to test the proposed official-free-shop workflow, not to decide Campaign 1 availability.

### Stock Ownership Rule

The vendor row owns facts that can vary by vendor or over time:

- current availability
- current quantity
- vendor-specific base price
- compact vendor-screen tags
- short storefront description
- the verified direct official URL attached to the item name

The freely viewable official source owns the standard official item's published mechanical definition.

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
Choose candidate from official free catalog/category
        ↓
Open candidate's direct official item page
        ↓
Are usable mechanics freely viewable?
   ├── NO
   │    ↓
   │  Reject candidate for normal shop stock
   │  Choose another official free item
   │
   └── YES
        ↓
Attach direct verified URL to Item name
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
Vendor Stock
    ↓ purchase
Vendor Qty decreases
    +
Party Inventory gains the purchased official item
```

The shop's responsibility ends after the stock and transaction state are updated. Any later inventory-specific or non-vendor changes to that item belong outside vendor mechanics.

---

# Same Official Item at Another Vendor

Two vendors can sell the same freely viewable official item without duplicating its standard mechanics.

```text
Ash & Ember Outfitters
Linked Longsword - Base Price 15 gp - Qty 4
        ↓
Direct verified official Longsword page

Another Vendor
Linked Longsword - Base Price 18 gp - Qty 1
        ↓
Same direct verified official Longsword page
```

Each vendor owns its own price and quantity. Both item names can point to the same freely viewable official definition.

---

# Revised Option B Ownership Model

```text
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
    │   └── direct verified free official item page
    ├── vendor-specific base price
    ├── current quantity
    ├── category
    ├── compact key mechanics
    └── short description

Official D&D Free Catalog / Categories
└── discovery source for normal shop items

Freely Viewable Direct Official Item Page
└── standard published mechanics for the linked shop item
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

- Uses the official free item catalog/categories instead of building a duplicate local official-item catalog.
- Makes the item name itself the direct official link.
- Removes the extra `Free Official Reference` table column.
- Removes the redundant locally generated inspection layer for ordinary official shop items.
- Keeps normal shop rows compact and vendor-screen-like.
- Keeps base price and quantity vendor-owned with one clear authority.
- Leaves full standard official mechanics on the freely viewable official item page instead of copying them into `NPC-state.md`.
- Rejects inaccessible/paywalled item pages before they become normal shop stock.
- Allows the same official item to appear at multiple vendors with different stock and prices without redefining its mechanics.
- Keeps homebrew/custom/modified items completely outside vendor mechanics.

# Questions Still Open

- Campaign 1 still needs an explicit D&D rules/version baseline before official references can be standardized confidently.
- External official URLs or access rules can change, so links may occasionally need rechecking or replacement.
- We still need exact markup/discount stacking and rounding rules.
- We still need to decide whether shop `Key Mechanics` and `Short Description` are always manually stored vendor-facing summaries or can sometimes be generated from the freely viewable official page.

---

**Status:** Design option only. Not approved. Not Campaign 1 canon.
