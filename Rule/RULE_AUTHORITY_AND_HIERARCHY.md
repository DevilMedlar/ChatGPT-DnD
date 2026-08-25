# Rule Authority and Hierarchy

## Central rule library

Reusable gameplay, GM behavior, campaign architecture, persistence, and continuity rules live in the categorized files under `Rule/`.

Numbered campaign folders own campaign state. They should not duplicate shared rules merely for convenience.

`New-Sheets/` contains reusable blank sheet structure and examples. It is not live campaign state and does not override the rules in `Rule/`.

## Rule conflict order

When **rules themselves conflict**, use this order:

1. the player's newest explicit instruction that applies to the current campaign
2. an explicitly scoped campaign-specific rule or override recorded on the repository's current branch, when one exists
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

Never silently overwrite established canon. When a correction or override changes persistent state, apply it through the correct state owner and save workflow so the repository remains internally consistent.
