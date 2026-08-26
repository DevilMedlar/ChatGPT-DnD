# Rule Authority and Hierarchy

## Central rule library

Reusable gameplay, GM behavior, campaign architecture, persistence, and continuity rules live in the categorized files under `Rule/`.

Numbered campaign folders own campaign state and may also contain a narrowly scoped persistent campaign-specific rule layer under their own `Rules/` directory.

`New-Sheets/` contains reusable blank sheet structure and examples. It is not live campaign state and does not override the rules in `Rule/` or an applicable campaign-specific rule.

## Campaign-specific rule layer

Persistent rules that apply only to one numbered campaign live in:

`campaigns/campaign-N/Rules/Campaign-N_Rules.md`

This file is the campaign's canonical local rule layer.

Use it only for persistent campaign-specific:

- operating rules
- mechanical overrides
- agency or behavior overrides
- exceptional premises
- rule clarifications intentionally scoped to that campaign
- other explicit player instructions that are intended to remain rules for that campaign across future sessions

Do **not** copy unchanged repository-wide rules into the campaign-specific rule file merely for convenience. The local file should contain only the campaign-specific delta from the reusable rules under `Rule/`.

Ordinary character, NPC, relationship, inventory, world, quest, shop, session, advancement, art, and other campaign facts are **state**, not local rules, and remain in their assigned state files.

When the player explicitly establishes a new persistent campaign-specific rule, records a campaign-specific override, rescinds one, or changes one, update that campaign's `Rules/Campaign-N_Rules.md` accordingly. A rule-file edit does not by itself create a Campaign Turn Step or increment `save_revision`. If the rule change also requires campaign state to change, apply those state changes through the appropriate persistence workflow.

A campaign-specific rule applies only to the campaign or circumstance to which it is explicitly scoped. Never silently import it into another campaign or promote it into a repository-wide rule.

## Rule conflict order

When **rules themselves conflict**, use this order:

1. the player's newest explicit instruction that applies to the current campaign
2. an applicable persistent rule or override in that campaign's `Rules/Campaign-N_Rules.md`
3. the most specific applicable categorized rule under `Rule/`
4. a more general applicable rule under `Rule/`
5. the GM priority guidance in `GM_BEHAVIOR_AND_PRIORITY.md` when no more specific rule resolves the issue

A campaign-specific override affects only the campaign or circumstance to which it is explicitly scoped. Do not silently promote it into a repository-wide rule.

If two equally specific current rules genuinely conflict and the conflict cannot be resolved from their scope or wording, do not invent a resolution that changes established canon. Surface the conflict and use the player's newest explicit direction.

## State is not a lower-priority rule layer

Campaign state files are not a lower-priority rulebook. Each state file remains authoritative for the facts and mutable state assigned to it by `STATE_OWNERSHIP_AND_PERSISTENCE.md`.

Read rules and state together:

- rules determine how the game operates
- state records what is currently true in the campaign
- a general rule does not silently erase an established campaign fact merely because the fact is stored in state rather than in a rule file
- the player's newest explicit correction may supersede conflicting assistant-created state or rules for that campaign

When a state fact legitimately changes through play, update it through the applicable persistence workflow rather than treating the old value as a competing rule.

## Scope and specificity

Use the rule file whose subject most directly owns the issue.

Examples:

- consent questions use `ADULT_CONTENT_AND_CONSENT.md`
- advancement uses `ADVANCEMENT_AND_XP.md`
- Campaign Turn lifecycle uses `CAMPAIGN_TURNS_AND_STEPS.md`
- dice ownership uses `DICE_ROLLS_AND_REROLLS.md`
- NPC identity and membership use `NPCS_AND_PARTY_MEMBERSHIP.md`
- shops and pricing use `SHOPS_PRICING_AND_TRANSACTIONS.md`
- persistence ownership uses `STATE_OWNERSHIP_AND_PERSISTENCE.md`
- save approval, verification, and recovery use `SAVES_VERIFICATION_AND_RECOVERY.md`

Do not duplicate the same operating rule into multiple files merely to make it easier to find. Prefer a clear cross-reference to the authoritative subject file.

## Canon corrections

The player's newest explicit statement overrides conflicting assistant-created material.

Never silently overwrite established canon.

When a correction, clarification, or retcon changes persistent state **outside an active Campaign Turn** and is not an in-fiction gameplay event, apply it directly to the correct state owner under the non-gameplay correction and repository-maintenance rule in `STATE_OWNERSHIP_AND_PERSISTENCE.md`. Keep required mirrors/references synchronized and preserve useful historical correction context. Such a correction does not create a Campaign Turn Step or increment `save_revision`.

When a change is meant to occur **through play as an in-fiction event**, use the Campaign Turn staging and save workflow instead.

If a Campaign Turn is already open, do not silently rewrite its completed base state underneath the temporary ledger. Resolve the correction in a way that keeps the ledger and completed state consistent.
