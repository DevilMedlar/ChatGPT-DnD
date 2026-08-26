# Shops, Pricing, and Transactions

## Standard official item sourcing

Normal standard vendor stock uses official D&D items whose usable mechanics are freely viewable.

For a candidate standard official item:

1. choose it from the relevant official item or equipment catalog/category
2. open the item's direct official page before using it as normal stock
3. verify that enough actual mechanics are freely viewable to use the item without requiring a purchase
4. reject a candidate whose page is only a teaser, marketplace redirect, ownership prompt, or otherwise hides the usable mechanics, and choose another suitable official item instead
5. place the verified direct official URL on the **item name itself** in the vendor stock row

The campaign does not maintain a duplicate local official-item catalog for normal standard vendor items.

An approved official source is a mechanics/reference authority for a standard item while it remains shop stock, but it is **not** the campaign's vendor-price authority.

External URLs and access rules can change. Recheck a stored reference when an item is newly stocked or when the existing reference no longer works. If a reference fails at acquisition time, resolve that case before finalizing the owned-item mechanics snapshot.

This repository intentionally does not assume one universal official D&D edition/version for every D&D-derived mechanic. Official shop references must align with the applicable researched global standard once that item/mechanical subject has one established under `CORE_GAME_MECHANICS.md` and the relevant reusable rule files. Until that research and decision are complete, the unresolved official version choice is a research/design topic rather than a missing-state or audit defect; do not invent a universal edition baseline merely to fill the gap.

If a numbered campaign explicitly overrides an established global standard, apply that campaign's `Rules/Campaign-N_Rules.md` override only to that campaign.

Homebrew, custom, unique, campaign-created, and mechanically modified items are outside this standard official vendor-item flow and must use their established campaign mechanics instead of being forced into the normal official-stock schema.

## Storefront presentation

`NPC-state.md` owns persistent business-level vendor state and current shop stock.

For normal standard official stock, a storefront row may contain:

- linked Item name
- Base Price
- Qty
- Category
- Key Mechanics
- Short Description

`Category` and `Key Mechanics` are compact storefront fields derived from the current linked official reference. `Short Description` is compact generated storefront text. These are presentation fields, not independent permanent mechanical authorities.

Do not add a separate official-reference column, duplicate local official-item catalog, locally maintained full copy of standard official mechanics, or extra generated inspection block that merely repeats the stock row.

Shop stock is **business inventory**, not the shopkeeper's personal carried possessions and not party inventory.

## Routine-item Base Prices

`routine_item_prices.md` is authoritative for which items are classified as routine/basic repeat goods for recurring-price purposes and for each such item's current recurring **Base Price**.

The routine/basic classification is a campaign shopping classification, not the same thing as an official D&D rarity category.

A routine/basic item must use its established recurring Base Price whenever stocked. Every vendor stock row for that routine item mirrors the current value in `routine_item_prices.md` and must not independently redefine it.

Use recurring Base Prices for ordinary goods the campaign intentionally wants priced consistently across merchants, especially items commonly purchased repeatedly or in quantity.

If an item has no entry in `routine_item_prices.md`, do not claim it already has an established routine recurring Base Price.

Do not reconstruct routine-item prices from deleted files, repository history, previous chats, assistant memory, another campaign, or external listed prices unless the player explicitly establishes or imports that information for the campaign.

When an established recurring Base Price changes, update `routine_item_prices.md`, append its compact change-history record, and reconcile every currently stocked vendor row that mirrors that item in the same completed save.

Vendor-specific price differences continue to use Final Price modifiers rather than redefining the recurring Base Price.

## Base Price and Final Price

`Base Price` is the campaign starting price before applicable vendor or transaction modifiers.

For official items that are not routine/basic repeat goods, the GM may establish a reasonable Base Price when the item appears in stock.

Relevant considerations can include rarity, mechanical power, usefulness, duration or number of uses, whether the item is consumed, replaceability, local scarcity, item category, and comparable established campaign prices.

After Base Price is established:

`final price = base price +/- applicable merchant or unused contextual modifiers`

Merchant markup/discount is business or relationship pricing, such as ordinary shop policy, relationship treatment, reputation, faction standing, or negotiation.

Contextual market factors include scarcity, shortages, unusual demand, temporary events, and similar established market circumstances.

A pricing factor must not be counted more than once in the same stock listing or transaction. If scarcity, rarity, local conditions, or another factor already affected the Base Price, the same factor must not be applied again to Final Price.

A distinct merchant markup or discount may still apply afterward because it is a different pricing factor.

## Currency, modifier stacking, and rounding

Campaign currency follows the official current D&D coin values:

- `1 Copper Piece (CP) = 1 CP`
- `1 Silver Piece (SP) = 10 CP`
- `1 Electrum Piece (EP) = 50 CP = 5 SP`
- `1 Gold Piece (GP) = 100 CP = 10 SP = 2 EP`
- `1 Platinum Piece (PP) = 1,000 CP = 100 SP = 20 EP = 10 GP`

Gold Piece (GP) is the standard wealth reference unit, while actual holdings and transactions may use any official coin denomination.

For price calculations, convert monetary values to copper-equivalent units so mixed denominations and fractional results can be resolved consistently.

### Percentage modifiers

Multiple percentage modifiers stack **additively**. Calculate every percentage modifier independently from the same Base Price rather than applying percentages sequentially to an already modified subtotal.

For Base Price `B` and percentage modifiers `p1`, `p2`, and so on:

`percentage-adjusted price = B + (B × p1) + (B × p2) + ...`

A discount is represented by a negative percentage.

### Flat modifiers

After calculating all percentage adjustments from Base Price, add or subtract any distinct flat-price modifiers.

General form:

`final unrounded price = B + sum(B × percentage modifiers) + sum(flat modifiers)`

Do not double-count a factor already included in Base Price.

Example:

`50 CP + (50 CP × 0.10) - (50 CP × 0.05) + 5 CP - 10 CP`

`= 50 CP + 5 CP - 2.5 CP + 5 CP - 10 CP`

`= 47.5 CP`

Final price: `48 CP`.

### Denomination conversion and rounding

Convert fractional higher denominations downward using the official exchange values before rounding.

Examples:

- `1.5 GP = 1 GP 1 EP` (equivalently `1 GP 5 SP`)
- `1.5 SP = 1 SP 5 CP`

Only a remaining fractional **copper** amount requires rounding. Use normal arithmetic rounding:

- `.5` copper or higher rounds up to the next whole copper
- below `.5` copper rounds down

Examples:

- `1.5 CP = 2 CP`
- `47.50 CP = 48 CP`
- `47.49 CP = 47 CP`

After final copper rounding, the price may be displayed in the largest convenient official denominations using CP, SP, EP, GP, and PP.

## Shop purchase flow

During an active Campaign Turn, a purchase is staged in `turn_save.md` under `Pending Shop Transactions`; do not immediately rewrite permanent vendor or inventory files.

A staged transaction must preserve enough information to reconcile all connected sides of the purchase, including when relevant:

- shop NPC ID / business
- buyer
- official item reference
- item and quantity
- Base Price and its basis
- factors already included in Base Price
- Final Price modifiers
- Final Transaction Price
- vendor stock before and after
- buyer currency delta
- inventory target and acquisition
- acquisition mechanics snapshot
- stack result
- notes

A completed purchase has connected state on both sides:

- vendor quantity decreases by the purchased quantity
- buyer currency decreases by the approved Final Transaction Price
- the buyer gains the purchased item in the appropriate inventory record
- the acquired item's mechanically relevant facts are preserved in the inventory snapshot when required
- compatible or separate stack handling follows `INVENTORY_EQUIPMENT_AND_ITEMS.md`
- if the buyer is a current-party persistent NPC, that NPC's master ownership list in `NPC-state.md` is reconciled too

After save approval, reconcile all connected sides together. Never permanently apply only the vendor side, only the currency side, or only the inventory side.

A pricing factor recorded as already included in Base Price must not also appear as a Final Price modifier for the same transaction.

Once an official item has been acquired and its relevant mechanics are established in campaign inventory, later changes to the external official page do not silently rewrite the already-owned campaign item.

Transaction save behavior is governed by `CAMPAIGN_TURNS_AND_STEPS.md` and `SAVES_VERIFICATION_AND_RECOVERY.md`.
