## Official shop items and vendor pricing

### Standard official item sourcing

Normal standard vendor stock uses official D&D items whose usable mechanics are freely viewable.

For a candidate standard official item:

1. choose it from the relevant official item/equipment catalog or category
2. open the item's direct official page before using it as normal stock
3. verify that enough actual mechanics are freely viewable to use the item without requiring a purchase
4. reject a candidate whose page is only a teaser, marketplace redirect, ownership prompt, or otherwise hides the usable mechanics, and choose another suitable official item instead
5. place the verified direct official URL on the **item name itself** in the vendor stock row

The campaign does not maintain a duplicate local official-item catalog or a second detailed inspection layer for normal standard vendor items. D&D Beyond or another approved official source is a mechanics/reference authority for the standard item while it remains shop stock, but it is **not** the campaign's vendor-price authority.

External URLs and access rules can change. A stored reference may be rechecked when an item is newly stocked or when the existing reference no longer works. If a reference fails at acquisition time, resolve that case individually before finalizing the owned-item mechanics snapshot.

Official shop references must eventually align with that campaign's chosen D&D rules/version baseline. This vendor architecture does not itself choose that broader baseline.

Homebrew, custom, unique, campaign-created, and mechanically modified items are outside this standard official vendor-item schema. Their mechanics and persistence must be handled by whatever separate campaign architecture governs those items rather than forcing them into the normal official-stock flow.

### Storefront presentation

`NPC-state.md` owns the persistent business-level vendor state and `Current Shop Stock` table.

For normal standard official stock, the row contains:

- linked Item name
- Base Price
- Qty
- Category
- Key Mechanics
- Short Description

`Category` and `Key Mechanics` are compact storefront fields derived from the current linked official reference. `Short Description` is compact generated storefront text. These are presentation fields, not independent permanent mechanical authorities.

Do not add a separate official-reference column, a duplicate local official-item catalog, a locally maintained detailed copy of standard official mechanics, or an extra generated inspection block that repeats the stock row.

### Base Price and Final Price

`Base Price` is the campaign starting price before the applicable vendor or transaction modifiers.

`routine_item_prices.md` is authoritative for which items are classified as routine/basic repeat goods for recurring-price purposes and for each such item's current recurring Base Price. A routine/basic item must use that established Base Price whenever stocked. Every vendor stock row for that routine item mirrors the value from `routine_item_prices.md` and must not independently redefine it.

Use `routine_item_prices.md` for ordinary goods that the campaign intentionally wants to price consistently across merchants, especially items commonly purchased repeatedly or in quantity.

This recurring-price rule applies only to items explicitly classified in `routine_item_prices.md`; it does not require every item appearing at multiple merchants to share one Base Price. If an item has no entry there, do not claim it already has an established routine recurring Base Price. Establish the entry through the appropriate completed-save workflow before relying on routine-price authority.

Do not reconstruct routine-item prices from deleted files, repository history, previous chats, memory, another campaign, or external listed prices unless the player explicitly establishes or imports that information for the campaign.

For other official items, the GM may establish a reasonable Base Price when the item appears in stock. The price should be sensible rather than arbitrary noise. Relevant considerations can include rarity, mechanical power, usefulness, duration or number of uses, whether the item is consumed, replaceability, local scarcity, item category, and comparable established campaign prices. These non-routine items do not require a permanent global Base Price registry.

After Base Price is established:

`final price = base price +/- applicable merchant or unused contextual modifiers`

Merchant markup/discount is business or relationship pricing, such as ordinary shop policy, relationship treatment, reputation, faction standing, or negotiation.

Contextual market factors include scarcity, shortages, unusual demand, temporary events, and similar established market circumstances. A contextual factor is not automatically a merchant markup/discount.

A pricing factor must not be counted more than once in the same stock listing or transaction. If scarcity, rarity, local conditions, or another factor already affected that listing's Base Price, the same factor must not be applied again to Final Price. A distinct merchant markup or discount may still apply afterward because it is a different pricing factor.

Change an established routine Base Price only when the campaign explicitly changes that item's recurring baseline.

A change to an established Base Price in `routine_item_prices.md` is campaign-wide, not a single-vendor adjustment. When that recurring Base Price changes, every currently stocked vendor row for that item must be reconciled to the new mirrored Base Price in the same completed save whenever such rows exist. Vendor-specific price differences continue to use Final Price modifiers instead.

The exact stacking, ordering, and rounding rules for multiple distinct modifiers remain intentionally undecided until the active campaign establishes them.

### Shop purchase flow

During an active Campaign Turn, a purchase is staged in `turn_save.md` under `Pending Shop Transactions`; do not immediately rewrite permanent vendor or inventory files.

A completed purchase has connected state on both sides:

- vendor quantity decreases by the purchased quantity
- buyer currency decreases by the approved Final Transaction Price
- the buyer gains the purchased item in the appropriate inventory record
- the acquired standard official item's mechanically relevant facts are preserved in the acquisition snapshot governed by `inventory.md`
- compatible or separate stack handling follows `inventory.md`
- if the buyer is a current-party persistent NPC, that NPC's master ownership list in `NPC-state.md` is reconciled too

After Confirmation Gate 1, reconcile all connected sides together. Never permanently apply only the vendor side, only the currency side, or only the inventory side of the transaction.

Once an official item has been acquired and its relevant mechanics are established in campaign inventory, later changes to the external official page do not silently rewrite the already-owned campaign item. `inventory.md` owns the acquired-item snapshot and stack-compatibility rules.

When a shop purchase occurs during an active Campaign Turn, keep the transaction temporary here until Confirmation Gate 1. Use one compact record per transaction and preserve enough information to reconcile every connected side of the purchase.

A staged purchase is one connected transaction. Vendor quantity, buyer currency, inventory acquisition, and acquisition snapshot must reconcile together; do not permanently apply only one side. A pricing factor recorded as already included in Base Price must not also appear as a Final Price modifier for the same transaction. If the buyer is a current-party persistent NPC, include the required `NPC-state.md` master-ownership update in `Pending Permanent Transfers`.

This file is the authoritative Campaign 1 data reference for **routine/basic repeat-good classification** and each classified item's recurring **Base Price**.

The shared rules for establishing, using, changing, staging, reconciling, and verifying recurring Base Prices are owned by `../GAME_MASTER_RULES.md`. This file does not redefine those rules.

The routine/basic classification here is a **Campaign 1 shopping classification**, not the same thing as an official D&D rarity category such as Common, Uncommon, Rare, or another rules-defined rarity.

Each entry must identify the exact item under Campaign 1's adopted rules/reference context before the classification and recurring Base Price are established through the shared workflow.

Do not add placeholder items merely to populate the table. Add an entry only when Campaign 1 establishes the classification and Base Price through the shared completed-save workflow.

When an established recurring Base Price changes under the shared rules, append a compact chronological record containing the completed save context, item, old Base Price, new Base Price, and reason.

Suggested format:

`- Save revision / Campaign Turn or other completed-save context — Item: old Base Price -> new Base Price — reason`

## Local Continuity Note

This file contains Campaign 1 price state only. Fresh-campaign isolation and historical-reconstruction restrictions are inherited from `../GAME_MASTER_RULES.md`.
