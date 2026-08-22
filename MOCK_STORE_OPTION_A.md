# MOCK STORE OPTION A — Vendor-Local Item Details

> **DESIGN MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file exists only to test shop/vendor architecture for audit issue #13. Nothing in this file establishes Campaign 1 NPCs, shops, items, prices, mechanics, locations, or story facts. Do not import any part of it into campaign canon unless the player explicitly approves that change later.

## Design Goal

Model a shop more like a game vendor screen:

1. the vendor/shop owns business rules
2. `Current Shop Stock` is the compact storefront the player can browse at a glance
3. complicated item mechanics are stored once in vendor-local detailed records
4. inspecting an item builds a detailed view from the current stock row plus the stable detailed record
5. stock quantity and base price belong to the vendor stock row, not to the mechanical item definition
6. hidden or unidentified properties remain stored for continuity but are filtered out of player-facing inspection until legitimately learned

This option deliberately keeps both the shop and its complicated item definitions together in the same vendor record. It does **not** introduce a separate global item catalog or item-ID system.

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

`Base Price` is the item's unmodified shop price stored in the stock record.

The final narrated transaction price is calculated when the purchase is actually being resolved:

`final price = base price +/- applicable markup/discount`

The exact stacking/order/rounding rules for multiple modifiers are **not decided by this mock**.

A relationship discount or temporary markup does not rewrite the stored base price unless the base price itself permanently changes.

---

## Current Shop Stock — Vendor Screen

This is the compact browse view. `Key Mechanics` contains short recognizable traits, ability names, slots, charges, or other useful at-a-glance information. It is **not** the full mechanical definition.

| Item | Base Price | Qty | Type | Key Mechanics | Short Description |
|---|---:|---:|---|---|---|
| Traveler's Torch | 1 sp | 20 | Utility | Burns 1 hour | Waxed wooden torch for ordinary travel use. |
| Redleaf Tonic | 5 gp | 6 | Consumable | Minor Healing | Small red-glass vial of restorative tonic. |
| Blazebrand Longsword | 500 gp | 2 | Weapon | Blaze; 1 Gem Slot | Blackened longsword with a faint ember glow along the edge. |
| Frostglass Charm | 240 gp | 1 | Wondrous | Cold Ward; Attunement | Pale glass charm that remains cool to the touch. |
| Locksmith's Roll | 25 gp | 3 | Tool | Precision Tools | Compact leather roll containing fine picks and tension tools. |
| Ashen Reliquary | 120 gp | 1 | Curio | Unknown Aura | Sealed silver reliquary dusted with gray ash. |

### Simple Item Rule

A simple stock item does not need a detailed record when the stock row plus already-established campaign rules are enough to resolve it consistently.

For example, `Traveler's Torch` may remain only a stock row if no special mechanics need to be preserved.

### Complex Item Rule

A complicated, magical, charged, cursed, slotted, attuned, unusual, or otherwise mechanically important item gets one detailed vendor-local record below.

The detailed record does **not** repeat current shop quantity or base price. Those remain owned by `Current Shop Stock`.

---

## Vendor-Local Detailed Item Records

### Blazebrand Longsword

- **Type:** Weapon — longsword
- **Rarity:** Mock rarity only
- **Damage / armor / defense:** Example placeholder; exact campaign damage rules not being decided here
- **Attack modifier:** None established by this mock
- **Damage modifier:** None established by this mock
- **Damage type:** Slashing
- **Gem slots:** 1
- **Requirements:** None established by this mock
- **Attunement / bonding:** Example: required
- **Durability / condition:** Normal unless play establishes otherwise
- **Known properties:** Blaze; one gem slot
- **Unidentified properties:** No
- **Description:** A blackened longsword whose edge gives off a low ember glow when drawn.

#### Ability — Blaze

- **Description:** Example named ability for testing vendor display and inspection behavior.
- **Mechanical effect:** Deliberately not finalized in this mock.
- **Activation:** Not finalized
- **Uses / charges:** Not finalized
- **Recharge:** Not finalized
- **Duration:** Not finalized
- **Requirements:** Not finalized
- **Stacking / exclusivity:** Not finalized

### Frostglass Charm

- **Type:** Wondrous item
- **Rarity:** Mock rarity only
- **Requirements:** None established by this mock
- **Attunement / bonding:** Example: required
- **Charges / uses:** None established by this mock
- **Known properties:** Cold Ward
- **Unidentified properties:** No
- **Description:** A translucent pale-blue charm that stays cold even near open flame.

#### Ability — Cold Ward

- **Description:** Example named ability for testing the inspection model.
- **Mechanical effect:** Deliberately not finalized in this mock.
- **Activation:** Not finalized
- **Duration:** Not finalized

### Ashen Reliquary

- **Type:** Curio / possible magical item
- **Rarity:** Unknown to the player in this example
- **Requirements:** Unknown
- **Attunement / bonding:** Unknown
- **Known properties:** Faint unidentified aura
- **Unidentified properties:** Yes
- **Description:** A sealed silver reliquary with old ash packed into its engraved seams.

#### Hidden Properties — GM / Continuity Only

> These are intentionally mock hidden details used only to test information filtering. They must not appear in the player-facing vendor screen or inspection result unless discovered through legitimate play.

- **Hidden property A:** Mock curse/effect placeholder
- **Hidden property B:** Mock trigger placeholder

---

# Example Item Inspection

Player request:

`Inspect the Blazebrand Longsword.`

The inspection view is assembled from the current vendor stock plus the stable detailed record. The current price and quantity are **displayed** here but are not duplicated in the stored detailed definition.

## Blazebrand Longsword — Inspection View

- **Base Price:** 500 gp  
  Source: current shop stock
- **Available:** 2  
  Source: current shop stock
- **Type:** Weapon — longsword
- **Rarity:** Mock rarity only
- **Key Mechanics:** Blaze; 1 Gem Slot
- **Damage:** Example placeholder; exact campaign damage rules not decided here
- **Attunement:** Required in this mock
- **Description:** A blackened longsword whose edge gives off a low ember glow when drawn.

### Blaze

Full currently-known ability details would be shown here from the stable detailed record.

### Final Purchase Price

Narration may then calculate a transaction-specific price from the base price and currently applicable business/relationship modifiers.

Example structure only:

```text
Base Price                         500 gp
+ applicable markup               ?????
- applicable discount             ?????
----------------------------------------
Final Transaction Price           ?????
```

The final transaction price is not written back over `Base Price` merely because a temporary modifier applied.

---

# Example Hidden-Information Inspection

Player request:

`Inspect the Ashen Reliquary.`

Player-facing result may show:

- **Base Price:** 120 gp
- **Available:** 1
- **Type:** Curio
- **Known Mechanics:** Unknown Aura
- **Known Description:** Sealed silver reliquary dusted with gray ash
- **Unidentified:** Yes

It must **not** reveal the mock hidden curse/trigger simply because those properties exist in the stored vendor-local detail record.

---

# Option A Ownership Model

```text
Shop / Services
│
├── Business-Level State
│   ├── business rules
│   ├── restocking
│   ├── buy-back policy
│   └── markup / discount rules
│
├── Current Shop Stock
│   ├── item name
│   ├── base price
│   ├── current quantity
│   ├── type
│   ├── compact key mechanics
│   └── short description
│
└── Vendor-Local Detailed Item Records
    ├── stable full mechanics
    ├── abilities / effects
    ├── requirements
    ├── rarity
    ├── full description
    ├── known properties
    └── hidden / unidentified properties
```

Inspection is a **view**, not a second independently maintained stock record:

```text
Current Shop Stock
        +
Vendor-Local Detailed Record
        +
Current player knowledge
        ↓
Generated Item Inspection
```

---

# Strengths of Option A

- Fits the repository's current idea that shop stock belongs in the relevant NPC's `NPC-state.md` record.
- No new campaign file or global item registry is required.
- Base price and quantity have one authoritative home.
- Full mechanics have one authoritative home within that vendor.
- Inspection can be rich without duplicating mutable shop state.
- Hidden information can remain in the detailed record while being filtered from narration.
- Easy to start using with a small number of shops/items.

# Weaknesses / Questions of Option A

- If the same complex item appears in several shops, its detailed definition may be copied into several NPC records.
- Repeated definitions could eventually drift if one copy is updated and another is forgotten.
- Item names/headings are doing most of the linking between the stock row and its detailed record.
- A vendor with a very large catalog could make one NPC record bulky.
- This option does not solve reusable item definitions across shops, loot, crafting, treasure, and party inventory.

# Questions to Test Before Choosing

1. Is vendor-local simplicity more valuable than reusable item definitions?
2. How often do we expect the exact same complex item type to appear in multiple places?
3. Do unique magic items need stable item IDs, or is the NPC/shop context enough?
4. Should `Key Mechanics` be renamed to `Traits / Mechanics`, `Key Traits`, or something else?
5. Should the vendor screen show `Type`, or should type appear only during inspection?
6. Should base price always be stored per vendor stock row, even if several vendors carry the same item?
7. How should multiple markup/discount modifiers combine and round?

---

**Status:** Design option only. Not approved. Not Campaign 1 canon.
