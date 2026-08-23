# Routine Item Base Prices — Campaign 1

This file is the authoritative Campaign 1 reference for **routine/basic repeat goods** and their recurring **Base Prices**.

It exists so ordinary items that are repeatedly bought, bought in quantity, or encountered across multiple shops do not receive a newly invented Base Price every time they appear.

This file does **not** define official item mechanics and does **not** own vendor quantity, merchant markup/discount, contextual transaction modifiers, Final Transaction Price, or party inventory.

## Authority and Scope

- An item is treated as a **routine/basic repeat good for recurring-price purposes** only when it has an established entry in this file.
- This file owns that item's current recurring **Base Price** for Campaign 1.
- `GAME_MASTER_RULES.md` owns the rules for how Base Price and Final Price are used, including merchant pricing, contextual pricing, and the no-double-counting rule.
- A shop's `NPC-state.md` stock row **mirrors** the current recurring Base Price from this file for a routine/basic item. The vendor row does not independently redefine that Base Price.
- Vendor-specific markup, discount, relationship treatment, negotiation, or another vendor-specific pricing difference changes the **Final Price**, not the recurring Base Price stored here.
- Contextual market factors follow `GAME_MASTER_RULES.md`. A factor already incorporated into a Base Price must not be applied again to the same transaction.
- The verified official item page remains the mechanics/reference authority while a standard official item is shop stock.
- After purchase, `inventory.md` owns the acquired item's mechanically relevant campaign snapshot.

The routine/basic classification here is a **Campaign 1 shopping classification**, not the same thing as an official D&D rarity category such as Common, Uncommon, Rare, or another rules-defined rarity.

## Establishing a Routine Item Base Price

Use this file for ordinary goods that Campaign 1 intentionally wants to price consistently across merchants, especially items commonly purchased repeatedly or in quantity.

When establishing an entry:

1. identify the exact item under the campaign's adopted rules/reference context
2. explicitly classify it as a routine/basic repeat good
3. establish one recurring Campaign 1 Base Price for that item
4. record the item and Base Price in `Current Routine Item Base Prices`
5. use that Base Price whenever a vendor stocks the item as a routine/basic repeat good

Do not put a vendor-specific markup, discount, relationship modifier, negotiation result, temporary shortage effect, or other transaction-specific adjustment into this file merely to make one merchant's price different.

If an item does not yet have an entry here, do not claim that it already has an established recurring routine Base Price. Establish the entry through the appropriate completed-save workflow before relying on routine-price authority.

## Changing an Established Routine Base Price

A change here is a **campaign-wide Base Price change**, not a single-vendor adjustment.

- Change an established routine Base Price only when Campaign 1 explicitly changes that item's recurring baseline.
- Record the old value, new value, reason, and completed save context in `Base Price Change History`.
- When an established routine Base Price changes, reconcile every currently stocked vendor row for that routine item so its mirrored Base Price matches this file in the same completed save whenever such rows exist.
- If the change occurs during an active Campaign Turn, stage it in `turn_save.md`, include this file and every affected vendor record in `Pending Permanent Transfers`, and apply the permanent changes only after Confirmation Gate 1.
- Merchant-specific differences continue to belong in vendor/transaction modifiers rather than creating competing Base Prices here.

## Current Routine Item Base Prices

**No routine/basic item Base Prices are established yet.**

| Item | Base Price | Notes |
|---|---:|---|

Do not add placeholder items merely to populate the table. Add an entry only when Campaign 1 explicitly establishes that routine item and its Base Price.

## Base Price Change History

None yet.

When needed, use a compact chronological format such as:

`- Save revision / Campaign Turn or other completed-save context — Item: old Base Price -> new Base Price — reason`

## Continuity Rule

Do not reconstruct routine-item prices from deleted files, repository history, previous chats, memory, another campaign, or external listed prices unless the player explicitly establishes or imports that information for Campaign 1.

D&D Beyond or another official rules source may define item mechanics, but it is **not** the authority for Campaign 1's recurring vendor Base Prices.
