# MOCK STORE OPTION B — Vendor Stock + Reusable Item Definitions

> **DESIGN MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file exists only to test shop/vendor architecture for audit issue #13. Nothing in this file establishes Campaign 1 NPCs, shops, items, prices, mechanics, locations, or story facts. Do not import any part of it into campaign canon unless the player explicitly approves that change later.

## Design Goal

Model a shop like a game vendor screen while separating **vendor-specific stock state** from **reusable item definitions**.

1. the vendor/shop owns business rules
2. `Current Shop Stock` owns base price and current quantity for that vendor
3. compact key mechanics remain visible in the vendor screen
4. complicated item mechanics live in one reusable definition referenced by the stock row
5. item inspection combines vendor stock state + reusable definition + current player knowledge
6. hidden or unidentified properties remain stored for continuity but are filtered from player-facing inspection until legitimately learned

This option introduces mock item-definition keys to test whether recurring items need a stable identity separate from a vendor and separate from their display name.

The item keys in this file are **design examples only**. This mock does not decide that Campaign 1 must adopt item IDs.

---

# Mock Vendor

## Shop / Services

### Business-Level State

- **Business name:** Ash & Ember Outfitters
- **Business type:** Adventuring goods, weapons, curios, and supplies
- **Owner / operator:** Mock NPC only
- **Location:** Mock location only
- **Currency accepted:** Gold, silver, copper
- **Restock behavior:** Routine goods may restock regularly; rare or unique stock may not
- **Special-order capability:** Some items by arrangement
- **Buy-back policy:** Example only; not finalized
- **Base markup / discount rules:** Example only; not finalized
- **Current party discount / markup:** Example only; not finalized
- **Reason for discount / markup:** Relationship, reputation, faction standing, negotiation, event, or other established cause

### Price Meaning

`Base Price` is vendor-specific stock state.

The final narrated transaction price is calculated at purchase time:

`final price = base price +/- applicable markup/discount`

The exact stacking/order/rounding rules for multiple modifiers are **not decided by this mock**.

A temporary relationship discount or markup does not rewrite the stored base price unless the vendor's base price itself permanently changes.

---

## Current Shop Stock — Vendor Screen

`Definition Key` is bookkeeping only. It does not need to be narrated to the player.

| Item | Base Price | Qty | Type | Key Mechanics | Short Description | Definition Key |
|---|---:|---:|---|---|---|---|
| Traveler's Torch | 1 sp | 20 | Utility | Burns 1 hour | Waxed wooden torch for ordinary travel use. | ITEM-MOCK-0001 |
| Redleaf Tonic | 5 gp | 6 | Consumable | Minor Healing | Small red-glass vial of restorative tonic. | ITEM-MOCK-0002 |
| Blazebrand Longsword | 500 gp | 2 | Weapon | Blaze; 1 Gem Slot | Blackened longsword with a faint ember glow along the edge. | ITEM-MOCK-0003 |
| Frostglass Charm | 240 gp | 1 | Wondrous | Cold Ward; Attunement | Pale glass charm that remains cool to the touch. | ITEM-MOCK-0004 |
| Locksmith's Roll | 25 gp | 3 | Tool | Precision Tools | Compact leather roll containing fine picks and tension tools. | ITEM-MOCK-0005 |
| Ashen Reliquary | 120 gp | 1 | Curio | Unknown Aura | Sealed silver reliquary dusted with gray ash. | ITEM-MOCK-0006 |

### Stock Ownership Rule

The vendor row owns only facts that can vary by vendor or over time:

- current availability
- current quantity
- vendor-specific base price
- short vendor-screen presentation

The reusable definition does **not** own vendor quantity or vendor base price.

---

# Mock Reusable Item Definitions

These definitions represent the stable mechanical identity of an item type or unique item. They could eventually live in a dedicated campaign item catalog if this architecture were chosen, but this mock deliberately keeps them in the same root design file so no campaign structure is being changed yet.

## ITEM-MOCK-0001 — Traveler's Torch

- **Canonical item name:** Traveler's Torch
- **Type:** Utility
- **Rarity:** Common / ordinary in this mock
- **Stable mechanics:** Burns for 1 hour when lit
- **Description:** Waxed wooden torch suitable for ordinary travel use.
- **Hidden / unidentified properties:** None

## ITEM-MOCK-0002 — Redleaf Tonic

- **Canonical item name:** Redleaf Tonic
- **Type:** Consumable
- **Rarity:** Mock rarity only
- **Stable mechanics:** Minor Healing
- **Consumed on use:** Yes
- **Description:** Small red-glass vial of restorative tonic.
- **Hidden / unidentified properties:** None

## ITEM-MOCK-0003 — Blazebrand Longsword

- **Canonical item name:** Blazebrand Longsword
- **Type:** Weapon — longsword
- **Rarity:** Mock rarity only
- **Damage / armor / defense:** Example placeholder; exact campaign damage rules not being decided here
- **Attack modifier:** None established by this mock
- **Damage modifier:** None established by this mock
- **Damage type:** Slashing
- **Gem slots:** 1
- **Requirements:** None established by this mock
- **Attunement / bonding:** Example: required
- **Durability / condition:** Normal unless a specific instance changes during play
- **Known properties:** Blaze; one gem slot
- **Unidentified properties:** No
- **Description:** A blackened longsword whose edge gives off a low ember glow when drawn.

### Ability — Blaze

- **Description:** Example named ability for testing vendor display and inspection behavior.
- **Mechanical effect:** Deliberately not finalized in this mock.
- **Activation:** Not finalized
- **Uses / charges:** Not finalized
- **Recharge:** Not finalized
- **Duration:** Not finalized
- **Requirements:** Not finalized
- **Stacking / exclusivity:** Not finalized

## ITEM-MOCK-0004 — Frostglass Charm

- **Canonical item name:** Frostglass Charm
- **Type:** Wondrous item
- **Rarity:** Mock rarity only
- **Requirements:** None established by this mock
- **Attunement / bonding:** Example: required
- **Known properties:** Cold Ward
- **Unidentified properties:** No
- **Description:** A translucent pale-blue charm that stays cold even near open flame.

### Ability — Cold Ward

- **Description:** Example named ability for testing the inspection model.
- **Mechanical effect:** Deliberately not finalized in this mock.
- **Activation:** Not finalized
- **Duration:** Not finalized

## ITEM-MOCK-0005 — Locksmith's Roll

- **Canonical item name:** Locksmith's Roll
- **Type:** Tool
- **Rarity:** Common / ordinary in this mock
- **Stable mechanics:** Precision Tools
- **Description:** Compact leather roll containing fine picks and tension tools.
- **Hidden / unidentified properties:** None

## ITEM-MOCK-0006 — Ashen Reliquary

- **Canonical item name:** Ashen Reliquary
- **Type:** Curio / possible magical item
- **Rarity:** Unknown to the player in this example
- **Requirements:** Unknown
- **Attunement / bonding:** Unknown
- **Known properties:** Faint unidentified aura
- **Unidentified properties:** Yes
- **Description:** A sealed silver reliquary with old ash packed into its engraved seams.

### Hidden Properties — GM / Continuity Only

> These are intentionally mock hidden details used only to test information filtering. They must not appear in the player-facing vendor screen or inspection result unless discovered through legitimate play.

- **Hidden property A:** Mock curse/effect placeholder
- **Hidden property B:** Mock trigger placeholder

---

# Example Item Inspection

Player request:

`Inspect the Blazebrand Longsword.`

The inspection view resolves the stock row's `Definition Key`, then combines vendor state with the reusable definition.

## Blazebrand Longsword — Inspection View

- **Base Price:** 500 gp  
  Source: Ash & Ember Outfitters current stock
- **Available:** 2  
  Source: Ash & Ember Outfitters current stock
- **Type:** Weapon — longsword  
  Source: ITEM-MOCK-0003 definition
- **Rarity:** Mock rarity only
- **Key Mechanics:** Blaze; 1 Gem Slot
- **Damage:** Example placeholder; exact campaign damage rules not decided here
- **Attunement:** Required in this mock
- **Description:** A blackened longsword whose edge gives off a low ember glow when drawn.

### Blaze

Full currently-known ability details would be shown from `ITEM-MOCK-0003`.

### Final Purchase Price

Example structure only:

```text
Base Price                         500 gp
+ applicable markup               ?????
- applicable discount             ?????
----------------------------------------
Final Transaction Price           ?????
```

The item definition does not change because one merchant charges more, another charges less, or DevilMedlar earns a temporary discount.

---

# Same Item at Another Vendor

This is the main reason to test Option B.

A second mock vendor could stock the same item definition without copying its mechanics:

| Item | Base Price | Qty | Type | Key Mechanics | Short Description | Definition Key |
|---|---:|---:|---|---|---|---|
| Blazebrand Longsword | 620 gp | 1 | Weapon | Blaze; 1 Gem Slot | Imported ember-forged longsword. | ITEM-MOCK-0003 |

Now:

- Ash & Ember Outfitters owns `500 gp / Qty 2`
- the second vendor owns `620 gp / Qty 1`
- both point to the same stable item mechanics
- changing the item's canonical `Blaze` definition happens once

This demonstrates vendor-specific price/availability without duplicating the mechanical item truth.

---

# Unique Item Instance Question

A reusable definition solves item-type identity, but a specific physical instance may later gain unique state:

```text
Blazebrand Longsword definition
        ↓
Specific purchased sword
        ↓
condition / durability / socketed gem / attunement / curse discovery / custom name
```

If Campaign 1 eventually needs instance-level item identity, that would be a separate design problem. This mock does **not** assume every ordinary item needs a unique instance ID.

---

# Option B Ownership Model

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
    ├── display item name
    ├── vendor-specific base price
    ├── current quantity
    ├── compact key mechanics
    ├── short description
    └── stable definition reference

Reusable Item Definition
├── canonical item identity
├── type / rarity
├── stable full mechanics
├── abilities / effects
├── requirements
├── full description
├── known properties
└── hidden / unidentified properties
```

Inspection is generated:

```text
Vendor Stock State
        +
Reusable Item Definition
        +
Current player knowledge
        ↓
Generated Item Inspection
```

---

# Strengths of Option B

- Base price and quantity remain vendor-owned with no duplicate authority.
- Full mechanical details are defined once and can be reused across multiple shops, loot sources, crafting systems, or inventories.
- A stable definition key avoids relying only on names/headings when similar items exist.
- One mechanical correction can update every future inspection of that item definition.
- Different vendors can charge different base prices and carry different quantities without redefining the item.
- Hidden information remains part of the item truth while narration can filter it by player knowledge.

# Weaknesses / Questions of Option B

- Introduces an item-definition registry concept that the current repository does not yet have.
- Stable item keys create extra bookkeeping.
- Could be overengineered for ordinary one-off campaign items.
- A future campaign item-catalog file would need its own ownership and persistence rules.
- Item type/definition identity and unique physical-instance identity are different problems and could become confusing if not separated clearly.
- The vendor screen still carries compact display fields such as `Type`, `Key Mechanics`, and `Short Description`; we would need to decide whether those are intentionally vendor-facing summaries or should be generated from the item definition too.

# Questions to Test Before Choosing

1. Do we expect reusable item types to appear in several shops, treasure, crafting, and party inventories often enough to justify a catalog?
2. Should every defined item get a stable definition key, or only complex/important items?
3. Should ordinary items such as torches use a catalog entry or remain simple vendor rows?
4. Should vendor `Key Mechanics` and `Short Description` be manually written storefront text, or generated from the definition?
5. Should base price always remain vendor-specific rather than part of the reusable definition?
6. When an item is purchased, should inventory reference the reusable definition while owning its instance-specific state?
7. Do unique items eventually need stable instance IDs distinct from reusable item-definition IDs?
8. How should multiple markup/discount modifiers combine and round?

---

**Status:** Design option only. Not approved. Not Campaign 1 canon.
