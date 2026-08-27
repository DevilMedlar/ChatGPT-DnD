# Turn Save

This file is the temporary authoritative ledger for the current unfinished **Campaign Turn**.

When this skeleton is copied into a numbered campaign, keep the explanatory text and labeled transaction/check templates in that campaign's copy as fill-out guidance. They are documentation, not staged Turn events, conception checks, or transactions.

It carries only the live Campaign Turn record as canonical state. Detailed Campaign Turn terminology, roll-recording conventions, and end interpretation are defined in `../Rule/CAMPAIGN_TURNS_AND_STEPS.md`. Confirmation gates, reconciliation, verification, recovery, and reset rules are defined in `../Rule/SAVES_VERIFICATION_AND_RECOVERY.md`. Reproductive compatibility, fertility, conception targets, and reproductive-state persistence are defined in `../Rule/REPRODUCTION_AND_LINEAGE.md`.

The starting state is the current completed canonical campaign state at the recorded `Base save revision`; do not copy that entire state into this file. Record the steps, scene changes, other changes, pending reproductive checks, pending shop transactions, and compact effective in-turn values needed to continue or recover the Campaign Turn.

## Active Campaign Turn

- **Campaign Turn:**
- **Status:**
- **Current Step:**
- **Current Scene:**
- **Base save revision:**

## Turn Events

## Current In-Turn State

## Pending Reproductive Checks

Record only mechanically qualifying reproductive checks and the continuity facts needed for recovery. Do not record graphic scene detail merely to prove that a check occurred.

### Conception Check Template

- **In-world date / approximate time:**
- **Female parent / stable ID:**
- **Male parent / stable ID:**
- **Compatibility category:** Naturally compatible / Cross-species compatible / Conditionally compatible
- **Conditional requirements and whether satisfied:**
- **Male fertility status / modifier:**
- **Female fertility status / modifier:**
- **Prevention / contraception state:** None / Effective block / Chance-based method / Other established effect
- **Prevention failure roll, if required:**
- **Base Conception Target:**
- **Explicit effect modifiers:**
- **Final Conception Target:**
- **First player d10 result, tens digit:**
- **Second player d10 result, ones digit:**
- **Combined percentile result:** Treat `0` or a numbered `10` as digit `0`; `00` = `100`
- **Outcome:** Conception / No conception / Blocked before conception roll
- **Development route on success:** Live-bearing pregnancy / Fertilized-egg or clutch formation / Other established route
- **Character knowledge:**
- **Pending permanent destination on success:** `character_sheet.md` / `NPC-state.md` / both parents' records as applicable
- **Notes:**

Use at most one conception check per distinct male/female pairing during the same 24 in-world hours. After a successful conception, do not make later conception checks for that female until the resulting pregnancy, egg-forming, or other blocking reproductive state ends.

An unsuccessful check normally creates no permanent transfer unless it changes an ongoing fertility investigation, treatment, relationship decision, or other lasting state.

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
