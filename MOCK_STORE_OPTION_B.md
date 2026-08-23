# MOCK STORE OPTION B - Free Official Shop Catalog + Local Custom Items

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
8. homebrew, custom, unique, campaign-created, or mechanically modified items use local campaign definitions instead of pretending an official page fully defines them
9. under the current working idea, those custom/modified items are primarily found through treasure, defeated enemies, hidden caches, quests, rewards, crafting, unique NPC possessions, world events, or similar discoveries rather than ordinary shop stock

This is still a design mock. It does **not** finalize the campaign's D&D edition/rules baseline, markup math, loot system, custom-item storage location, or whether a previously discovered custom item may later enter commerce.

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

# Homebrew / Custom / Modified Items

## Working Discovery Rule

Under the current design direction, homebrew, custom, unique, campaign-created, or mechanically modified items are primarily discovered outside ordinary merchant stock.

Possible sources include:

- treasure chests
- defeated enemies or bodies
- hidden caches
- dungeon rewards
- quest rewards
- unique NPC possessions
- crafting
- transformations
- faction rewards
- world events
- relic discoveries
- secret rooms
- boss encounters
- other established campaign discoveries

This keeps normal shops grounded in freely accessible official items while allowing Campaign 1's stranger and more memorable equipment to emerge through play.

This rule is **not yet final**. A later decision could allow a discovered custom item type to enter commerce, be copied, be crafted for sale, or appear in a specialist shop if the world establishes that outcome.

---

# Local Definition Model for Custom Items

A normal official shop item can rely on its verified freely viewable official page for standard mechanics.

A homebrew/custom item cannot, so its stable mechanics must be preserved locally once it becomes real Campaign 1 canon.

The following examples are still **mock only** and are not shop stock.

## Blazebrand Longsword - Mock Custom Item

- **Source type:** Homebrew / custom
- **Discovery example:** Treasure from a defeated boss
- **Canonical item name:** Blazebrand Longsword
- **Type:** Weapon - longsword
- **Rarity:** Mock rarity only
- **Damage / armor / defense:** Example placeholder; exact campaign damage rules not decided here
- **Damage type:** Slashing
- **Gem slots:** 1
- **Attunement / bonding:** Example: required
- **Known properties:** Blaze; one gem slot
- **Unidentified properties:** No
- **Description:** A blackened longsword whose edge gives off a low ember glow when drawn.

### Ability - Blaze

- **Description:** Example named homebrew ability.
- **Mechanical effect:** Deliberately not finalized in this mock.
- **Activation:** Not finalized
- **Uses / charges:** Not finalized
- **Recharge:** Not finalized
- **Duration:** Not finalized
- **Requirements:** Not finalized
- **Stacking / exclusivity:** Not finalized

## Ashen Reliquary - Mock Unique Item

- **Source type:** Homebrew / unique
- **Discovery example:** Hidden cache or sealed tomb
- **Canonical item name:** Ashen Reliquary
- **Type:** Curio / possible magical item
- **Rarity:** Unknown to the player in this example
- **Requirements:** Unknown
- **Attunement / bonding:** Unknown
- **Known properties:** Faint unidentified aura
- **Unidentified properties:** Yes
- **Description:** A sealed silver reliquary with old ash packed into its engraved seams.

### Hidden Properties - GM / Continuity Only

> These are intentionally mock hidden details used only to test information filtering. They must not appear in player-facing narration or inspection until discovered through legitimate play.

- **Hidden property A:** Mock curse/effect placeholder
- **Hidden property B:** Mock trigger placeholder

---

# Custom Item Inspection Model

Custom items still need local inspection behavior because there is no official page that defines the custom mechanics.

```text
Local Custom Item Definition
        +
Specific Item Instance State when relevant
        +
Current player knowledge
        ↓
Generated Custom Item Inspection
```

A custom item's hidden properties remain stored for continuity but are filtered from player-facing inspection until legitimately discovered.

Once custom mechanics are established, they stay stable unless play legitimately changes the item.

---

# Modified Official Item Rule

If an official item is mechanically altered by Campaign 1, its linked official page can still define the unchanged base item, but it no longer defines the entire campaign object.

Conceptually:

```text
Linked Official Base Item
        +
Locally Stored Campaign Modification
        ↓
Modified Campaign Item
```

The campaign-specific modification must be stored locally.

Examples:

- an ordinary official longsword gains a permanent fire ability
- a shield acquires a curse
- a Bag of Holding is permanently altered by a campaign event
- an official weapon gains a unique socket/gem system not present in the official rules

A modified official item is therefore treated as campaign-specific state for the part that differs from the official definition.

---

# Purchased Official Item Transition

When an ordinary official item is bought:

```text
Vendor Stock
    ↓ purchase
Vendor Qty decreases
    +
Party Inventory gains the linked official item / necessary local active state
```

The campaign does not need to copy the full standard official definition into inventory merely because ownership changed.

Instance-specific state still belongs locally when relevant, such as:

- quantity
- equipped/carried/stored state
- current charges or ammunition
- durability / damage
- attunement
- custom name
- socketed gem
- discovered curse
- campaign modification

This separates **what the official item is** from **what happened to this particular campaign copy**.

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

Local Custom Definition
├── homebrew / unique / campaign-created mechanics
├── campaign modifications to official items when needed
├── abilities / effects
├── requirements
├── descriptions
└── hidden / unidentified properties
```

### Ordinary Official Item Details

```text
Current Shop Stock
        ↓
Click linked Item name
        ↓
Freely viewable direct official item page
```

### Custom Item Inspection

```text
Local Custom Definition
        +
Instance State when relevant
        +
Current player knowledge
        ↓
Generated Detailed Inspection
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
- Keeps homebrew/custom/modified item mechanics local only when Campaign 1 actually needs local mechanics.
- Lets custom/unique loot primarily come from exploration, enemies, quests, rewards, crafting, and discoveries rather than routine vendor shelves.

# Questions Still Open

- Campaign 1 still needs an explicit D&D rules/version baseline before official references can be standardized confidently.
- External official URLs or access rules can change, so links may occasionally need rechecking or replacement.
- We still need to decide where local homebrew/custom item definitions permanently live if this architecture is adopted.
- We still need to decide whether custom items can later become legitimate shop stock after being discovered, crafted, copied, commissioned, or commercialized in the story.
- We still need exact markup/discount stacking and rounding rules.
- We still need to decide whether shop `Key Mechanics` and `Short Description` are always manually stored vendor-facing summaries or can sometimes be generated from the freely viewable official page.

---

**Status:** Design option only. Not approved. Not Campaign 1 canon.
