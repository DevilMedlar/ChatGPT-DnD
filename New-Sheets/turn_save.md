# Turn Save

This file is the temporary authoritative ledger for the current unfinished **Campaign Turn**.

It carries only the live Campaign Turn record. Detailed Campaign Turn terminology, roll-recording conventions, and end interpretation are defined in `../Rule/CAMPAIGN_TURNS_AND_STEPS.md`. Confirmation gates, reconciliation, verification, recovery, and reset rules are defined in `../Rule/SAVES_VERIFICATION_AND_RECOVERY.md`.

The starting state is the current completed canonical campaign state at the recorded `Base save revision`; do not copy that entire state into this file. Record the steps, scene changes, other changes, pending shop transactions, and compact effective in-turn values needed to continue or recover the Campaign Turn.

## Active Campaign Turn

- **Campaign Turn:**
- **Status:**
- **Current Step:**
- **Current Scene:**
- **Base save revision:**

## Turn Events

## Current In-Turn State

## Pending Shop Transactions

When a shop purchase occurs during an active Campaign Turn, keep the transaction temporary here until Confirmation Gate 1. Use one compact record per transaction and preserve enough information to reconcile every connected side of the purchase.

### Shop Transaction Template

- **Shop NPC ID / business:**
- **Buyer:**
- **Official item reference:** If applicable
- **Item:**
- **Quantity:**
- **Base Price:**
- **Base Price basis:** Routine recurring / GM-established
- **Factors already included in Base Price:** None / list each distinct factor once
- **Final Price modifiers applied:** None / list each distinct modifier once, including its amount or effect when known
- **Final Transaction Price:**
- **Vendor stock before / after:**
- **Buyer currency delta:**
- **Inventory target / acquisition:**
- **Acquisition mechanics snapshot:** Pending / compact staged mechanics / approved source for reconciliation
- **Stack result:** New entry / Merge with compatible stack / Keep separate / Not applicable
- **Notes:**

A staged purchase is one connected transaction. Vendor quantity, buyer currency, inventory acquisition, and acquisition snapshot must reconcile together; do not permanently apply only one side. A pricing factor recorded as already included in Base Price must not also appear as a Final Price modifier for the same transaction. If the buyer is a current-party persistent NPC, include the required `NPC-state.md` master-ownership update in `Pending Permanent Transfers`.

## Pending Permanent Transfers

## Final Turn Review

- **Status:**
- **Final Turn State:**
- **Exact Planned Permanent Transfers:**
- **Player save confirmation:**

## Permanent Save Verification

- **Status:**
- **Completed save revision:**
- **Verification notes:**

## Reset Approval

- **Status:**
- **Player reset confirmation:**
