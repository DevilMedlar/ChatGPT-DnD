# MOCK STORE OPTION B — Free Official Vendor Stock + Local Custom Definitions

> **DESIGN MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file exists only to test shop/vendor architecture for audit issue #13. Nothing in this file establishes Campaign 1 NPCs, shops, items, prices, mechanics, locations, loot, or story facts. Do not import any part of it into campaign canon unless the player explicitly approves that change later.

## Working Design Goal

Model shops more like a game vendor screen while avoiding a large local copy of official D&D item mechanics.

1. the vendor/shop owns business rules
2. `Current Shop Stock` owns the vendor-specific base price and current quantity
3. ordinary shop stock uses **official D&D items whose usable mechanics are freely viewable**
4. the shop row keeps only compact at-a-glance information such as category, named traits/mechanics, slots, or other useful tags
5. the **item name itself is the verified free official link**
6. clicking the item name is the normal detailed-inspection path for an ordinary official shop item
7. homebrew, custom, unique, campaign-created, or mechanically modified items use local campaign definitions instead of pretending an official page defines them
8. under the current working idea, those custom/modified items are primarily found through treasure, defeated enemies, hidden caches, quests, rewards, crafting, unique NPC possessions, world events, or similar discoveries rather than ordinary shop stock

This is still a design mock. It does **not** finalize the campaign's D&D edition/rules baseline, official-item source policy, markup math, item-ID system, loot system, or whether a previously discovered custom item may later enter a shop.

---

# Source and Access Rule

## Free Official Shop Item Rule

Before an official D&D item is added to normal shop stock:

1. find an official item/reference page
2. open/check the page before using it
3. verify that the page exposes enough of the actual item mechanics to inspect and use the item without requiring a purchase
4. if the page is only a teaser, marketplace redirect, ownership prompt, or otherwise does not expose the usable mechanics for free, do **not** use that item as a link-dependent shop entry
5. choose another freely viewable official item instead, unless the player later changes this rule
6. place that verified reference directly on the item name in `Current Shop Stock`

A page merely existing is not enough. The usable rules must actually be viewable.

Because websites and access rules can change, a previously verified link may be rechecked when the item is newly placed into campaign stock or when the reference no longer works.

## Rules-Version Note

This mock is testing the **shop/reference architecture**, not resolving audit issue #1 about the campaign's exact D&D fallback rules baseline.

The examples below include pages that were freely readable when this mock was revised. Before this design becomes canon, official references should be aligned with whichever D&D rules/version baseline Campaign 1 eventually adopts.

---

# Mock Vendor

## Shop / Services

### Business-Level State

- **Business name:** Ash & Ember Outfitters
- **Business type:** Adventuring goods, weapons, armor, tools, consumables, and occasional official magic items
- **Owner / operator:** Mock NPC only
- **Location:** Mock location only
- **Currency accepted:** Gold, silver, copper
- **Restock behavior:** Routine goods may restock regularly; uncommon or rare stock may restock slowly or unpredictably
- **Special-order capability:** Some official items by arrangement when appropriate
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

For official items, the vendor's `Base Price` does not need to equal an official book/listed cost if campaign circumstances establish another price. The official page defines the item; the vendor record defines what this seller is asking before temporary modifiers.

---

## Current Shop Stock — Vendor Screen

This is the compact browse view, similar in spirit to a video-game vendor screen.

**Clicking the item name is the inspection action for an ordinary official item.** The item name contains the verified freely viewable official reference directly, so there is no separate `Free Official Reference` column and no second locally generated official-item inspection record.

`Key Mechanics` contains short recognizable information such as a mastery/property name, an ability name, an important tag, attunement, a slot count, or another useful glanceable trait. It is **not** a replacement for the full official item definition.

| Item | Base Price | Qty | Category | Key Mechanics | Short Description |
|---|---:|---:|---|---|---|
| [Torch](https://www.dndbeyond.com/equipment/437-torch) | 1 cp | 20 | Adventuring Gear | Burns 1 hour; Light | Ordinary handheld light source. |
| [Dagger](https://www.dndbeyond.com/equipment/3-dagger) | 2 gp | 8 | Weapon | Finesse; Light; Thrown; Nick | Small versatile piercing weapon. |
| [Longsword](https://www.dndbeyond.com/equipment/4-longsword) | 15 gp | 4 | Weapon | Versatile; Sap | Martial slashing weapon usable one- or two-handed. |
| [Shield](https://www.dndbeyond.com/equipment/8-shield) | 10 gp | 3 | Armor / Shield | +2 AC while properly used | Standard defensive shield. |
| [Thieves' Tools](https://www.dndbeyond.com/equipment/495-thieves-tools) | 25 gp | 2 | Tool | Locks; Traps; Dexterity | Specialized tools for locks and traps. |
| [Bag of Holding](https://www.dndbeyond.com/magic-items/4581-bag-of-holding) | 400 gp | 1 | Wondrous Item | Extradimensional Storage | Magical container with much greater interior capacity than its exterior suggests. |

> **Mock-data warning:** The quantities and vendor-specific base prices in this table are design examples only. They are not Campaign 1 canon. The links are included only to test the free-reference workflow and clickable-item-name idea.

### Linked Item Name Test

The `Longsword` table cell above is written in the Markdown source as:

```md
[Longsword](https://www.dndbeyond.com/equipment/4-longsword)
```

If GitHub renders the table normally, the visible word **Longsword** in the Item column should itself be clickable and should open the official item page.

This mock deliberately tests that behavior before the architecture is adopted.

### Stock Ownership Rule

The vendor row owns facts that can vary by vendor or over time:

- current availability
- current quantity
- vendor-specific base price
- compact vendor-screen tags
- short storefront description
- the verified official reference attached to the item name

The official source owns the standard official item's published mechanical definition.

The shop does **not** need:

- a separate official-reference column
- a second locally maintained detailed copy of official mechanics
- a generated official-item inspection block whose only purpose is to repeat the same vendor-row information and provide the same link

For an ordinary official item, the compact row is the shop view and the linked item name is the route to full details.

---

# Official Item Browse / Inspection Flow

```text
Generate or restock vendor
        ↓
Choose candidate official item
        ↓
Verify usable official mechanics are freely viewable
        ↓
Attach verified reference directly to Item name
        ↓
Show compact Current Shop Stock row
        ↓
Player wants full details
        ↓
Player clicks Item name
        ↓
Official free item page
```

No intermediate locally generated official-item inspection screen is required unless a later gameplay/UI reason makes one useful.

---

# Official Reference Categories

The exact category structure is not finalized, but the shop can conceptually source official items from categories such as:

- Weapons
- Armor / Shields
- Adventuring Gear
- Tools
- Potions / Consumables when freely viewable
- Magic Items when freely viewable
- Other official equipment categories supported by the chosen D&D rules baseline

The point of the category is discovery and organization. The authoritative external detail is the checked official item/reference page, not a locally rewritten copy.

---

# Paywall / Access Failure Behavior

If a candidate shop item fails the free-access check:

```text
Candidate Official Item
        ↓
Check Official Reference
        ↓
Are usable mechanics freely viewable?
   ├── YES
   │    ↓
   │  Item may be used in normal shop stock
   │  Attach checked reference to Item name
   │
   └── NO
        ↓
      Do not use it as link-dependent shop stock
      Choose another freely viewable official item
```

Do not wait until the player clicks the item during play to discover that its useful mechanics are inaccessible.

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

This helps keep normal shops grounded in verified free official references while allowing Campaign 1's stranger and more memorable equipment to emerge through play.

This rule is **not yet final**. A later decision could allow a discovered homebrew item type to enter commerce, be copied, be crafted for sale, or appear in a specialist shop if the world establishes that outcome.

---

# Local Definition Model for Custom Items

Official shop items can lean on their verified free official reference.

A homebrew/custom/modified item cannot, so its stable mechanics must be preserved locally once the item becomes real campaign canon.

The following examples are still **mock only** and are not shop stock.

## MOCK-CUSTOM-0001 — Blazebrand Longsword

- **Source type:** Homebrew / custom
- **Discovery example:** Treasure from a defeated boss
- **Canonical item name:** Blazebrand Longsword
- **Type:** Weapon — longsword
- **Rarity:** Mock rarity only
- **Damage / armor / defense:** Example placeholder; exact campaign damage rules not decided here
- **Damage type:** Slashing
- **Gem slots:** 1
- **Attunement / bonding:** Example: required
- **Known properties:** Blaze; one gem slot
- **Unidentified properties:** No
- **Description:** A blackened longsword whose edge gives off a low ember glow when drawn.

### Ability — Blaze

- **Description:** Example named homebrew ability.
- **Mechanical effect:** Deliberately not finalized in this mock.
- **Activation:** Not finalized
- **Uses / charges:** Not finalized
- **Recharge:** Not finalized
- **Duration:** Not finalized
- **Requirements:** Not finalized
- **Stacking / exclusivity:** Not finalized

## MOCK-CUSTOM-0002 — Ashen Reliquary

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

### Hidden Properties — GM / Continuity Only

> These are intentionally mock hidden details used only to test information filtering. They must not appear in player-facing narration or inspection until discovered through legitimate play.

- **Hidden property A:** Mock curse/effect placeholder
- **Hidden property B:** Mock trigger placeholder

---

# Custom Item Inspection Model

For a custom item there is no official external definition to rely on.

Inspection instead uses:

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

The same item should not mysteriously acquire different mechanics every time the player looks at it. Once its mechanics are established, its local definition is stable unless play legitimately changes the item.

---

# Modified Official Item Rule

If an official item is mechanically altered by Campaign 1, the official page can still explain the unchanged base item, but it no longer defines the entire campaign object.

Conceptually:

```text
Official Item Reference
        +
Campaign Modification
        ↓
Modified Campaign Item
```

The campaign-specific modification must be stored locally.

Examples:

- an ordinary official longsword gains a permanent fire ability
- a shield acquires a curse
- a Bag of Holding is permanently altered by a campaign event
- an official weapon gains a unique socket/gem system not present in the official rules

At that point the local campaign state must clearly preserve what differs from the official definition.

---

# Purchased Item Transition

When an ordinary official item is bought:

```text
Vendor Stock
    ↓ purchase
Vendor Qty decreases
    +
Party Inventory gains official item reference / necessary active state
```

The campaign does not need to copy the full official definition into every inventory entry merely because ownership changed.

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

Two vendors can sell the same official item without duplicating its standard mechanics.

Example:

```text
Ash & Ember Outfitters
[Longsword] — Base Price 15 gp — Qty 4
    ↓
Same checked official Longsword reference

Another Vendor
[Longsword] — Base Price 18 gp — Qty 1
    ↓
Same checked official Longsword reference
```

The vendors own their own price and quantity. Both item names can point to the same verified official definition.

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
    ├── vendor-specific base price
    ├── current quantity
    ├── category
    ├── compact key mechanics
    └── short description

Verified Free Official Reference
└── attached directly to the Item name
    └── standard published mechanics for normal shop items

Local Custom Definition
├── homebrew / unique / campaign-created mechanics
├── campaign modifications to official items when needed
├── abilities / effects
├── requirements
├── descriptions
└── hidden / unidentified properties
```

### Official Item Details

```text
Current Shop Stock
        ↓
Click linked Item name
        ↓
Verified free official item page
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

- Cuts out most locally duplicated inspection data for ordinary official shop items.
- Removes the extra `Free Official Reference` table column by attaching the reference directly to the item name.
- Removes the need for a redundant generated official-item inspection block in the normal browse flow.
- Base price and quantity remain vendor-owned with one clear authority.
- Full standard mechanics remain on the official free reference instead of being recopied into `NPC-state.md`.
- Paywalled/inaccessible official items can be rejected before they enter normal shop stock.
- Shops remain easy to browse in a compact vendor-screen format.
- Homebrew/custom items still have stable local mechanics when Campaign 1 needs them.
- Custom/unique loot can feel special because it primarily comes from exploration, enemies, quests, rewards, crafting, and discoveries rather than routine vendor shelves.
- The same official item can appear at several vendors with different stock and prices without redefining its mechanics.
- Purchased official items can keep a reference to their standard definition while local inventory tracks only campaign-specific state.

# Weaknesses / Questions Still Open

- We need to verify that the linked-item-name presentation actually feels good in GitHub's rendered Markdown table. This mock now exists specifically to test that.
- Campaign 1 still needs an explicit D&D rules/version baseline before official references can be standardized confidently.
- External official URLs can change, so links may occasionally need rechecking or replacement.
- We still need to decide where local homebrew/custom item definitions permanently live if this architecture is adopted.
- We still need to decide whether custom items can later become legitimate shop stock after being discovered, crafted, copied, commissioned, or commercialized in the story.
- We still need exact markup/discount stacking and rounding rules.
- We still need to decide whether shop `Key Mechanics` and `Short Description` are always manually stored vendor-facing summaries or can sometimes be generated from the official reference.
- We still need to decide what happens when an official item page is free when stocked but later becomes unavailable.

---

**Status:** Design option only. Not approved. Not Campaign 1 canon.
