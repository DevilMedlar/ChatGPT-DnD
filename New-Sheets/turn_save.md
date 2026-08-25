# Turn Save — Campaign 1

This file is the temporary authoritative ledger for the current unfinished **Campaign Turn**.

It carries only the live Campaign Turn record. Detailed Campaign Turn terminology, roll-recording conventions, end interpretation, confirmation gates, reconciliation, verification, recovery, and reset rules belong in `../GAME_MASTER_RULES.md`.

The starting state is the current completed canonical campaign state at the recorded `Base save revision`; do not copy that entire state into this file. Record the steps, scene changes, other changes, pending shop transactions, and compact effective in-turn values needed to continue or recover the Campaign Turn.

## Active Campaign Turn

- **Campaign Turn:** 1
- **Status:** ready
- **Current Step:** 0
- **Current Scene:** None yet.
- **Base save revision:** 0

## Turn Events

None yet.

## Current In-Turn State

None yet.

## Pending Shop Transactions

None yet.

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

None yet.

## Final Turn Review

- **Status:** not_started
- **Final Turn State:** None yet.
- **Exact Planned Permanent Transfers:** None yet.
- **Player save confirmation:** not_requested

## Permanent Save Verification

- **Status:** not_started
- **Completed save revision:** None
- **Verification notes:** None.

## Reset Approval

- **Status:** not_requested
- **Player reset confirmation:** not_requested
