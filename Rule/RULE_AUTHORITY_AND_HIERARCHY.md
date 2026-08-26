# Rule Authority and Hierarchy

## Central rule library

Reusable gameplay, GM behavior, campaign architecture, persistence, and continuity rules live in the categorized files under `Rule/`.

Numbered campaign folders own campaign state and may also contain a narrowly scoped persistent campaign-specific rule layer under their own `Rules/` directory.

`New-Sheets/` contains reusable blank sheet structure and examples. It is not live campaign state and does not override the rules in `Rule/` or an applicable campaign-specific rule.

`CORE_GAME_MECHANICS.md` establishes **D&D 5.5e / SRD 5.2.1** as the repository-wide default for ordinary D&D mechanics that are not explicitly replaced by a more-specific repository or campaign rule.

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

When the player explicitly establishes a new persistent campaign-specific rule, records a campaign-specific override, rescinds one, or changes one, update that campaign's `Rules/Campaign-N_Rules.md` accordingly. A rule-file edit does not by itself create a Campaign Turn Step or increment `save_revision`. If the rule change also requires campaign state to change, apply the resulting state changes through the appropriate persistence workflow.

A campaign-specific rule applies only to the campaign or circumstance to which it is explicitly scoped. Never silently import it into another campaign or promote it into a repository-wide rule.

## Rule conflict order

When **rules themselves conflict**, use this order:

1. the player's newest explicit instruction that applies to the current campaign
2. an applicable persistent rule or override in that campaign's `Rules/Campaign-N_Rules.md`
3. the most specific applicable categorized rule under `Rule/`
4. a more general applicable rule under `Rule/`
5. the ordinary D&D 5.5e / SRD 5.2.1 rule for the subject when no repository rule overrides it
6. the GM priority guidance in `GM_BEHAVIOR_AND_PRIORITY.md` when no more specific rule resolves the issue

A campaign-specific override affects only the campaign or circumstance to which it is explicitly scoped. Do not silently promote it into a repository-wide rule.

The official D&D baseline is a **default mechanics layer**, not a higher authority than an explicit homebrew rule. For example, `DICE_ROLLS_AND_REROLLS.md` overrides ordinary GM dice ownership, while `REPRODUCTION_AND_LINEAGE.md` governs homebrew reproductive compatibility not supplied by ordinary D&D rules.

If an ordinary D&D mechanic is needed and no repository rule covers it, use the current official 5.5e rule rather than inventing a local substitute.

If two equally specific current repository rules genuinely conflict and the conflict cannot be resolved from their scope or wording, do not invent a resolution that changes established canon. Surface the conflict and use the player's newest explicit direction.

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
- dice ownership and all gameplay randomness use `DICE_ROLLS_AND_REROLLS.md`
- NPC identity and membership use `NPCS_AND_PARTY_MEMBERSHIP.md`
- shops and pricing use `SHOPS_PRICING_AND_TRANSACTIONS.md`
- persistence ownership uses `STATE_OWNERSHIP_AND_PERSISTENCE.md`
- save approval, verification, and recovery use `SAVES_VERIFICATION_AND_RECOVERY.md`
- ordinary D&D mechanics not otherwise replaced use the 5.5e baseline established in `CORE_GAME_MECHANICS.md`

Do not duplicate the same operating rule into multiple files merely to make it easier to find. Prefer a clear cross-reference to the authoritative subject file.

## Canon corrections

Established canon must be read from its authoritative state owner and preserved during narration, calculations, Turn staging, Final Review, and permanent reconciliation. ChatGPT must not use new narration, assumptions, or remembered chat context to silently replace an already-established fact.

The player's newest explicit correction overrides conflicting assistant-created material. A correction is an explicit correction of canon, not permission for ChatGPT to reinterpret or casually rewrite established state.

When the player explicitly identifies a canonical fact or assistant-created record as wrong:

- verify the relevant authoritative state owner and the active `turn_save.md` before proposing any change
- follow the existing Campaign Turn and save workflow for any persistent campaign-state change
- if the correction is raised during an active Campaign Turn or its Final Review, correct the temporary Turn record and the **Exact Planned Permanent Transfers** before asking for confirmation again
- do not write an unapproved corrected value directly into permanent campaign state
- keep all required mirrors and dependent references synchronized when the approved correction is reconciled

A fact that is already present and unchanged in its authoritative permanent owner is not a correction and is not a new transfer. If the same unchanged detail appears in `turn_save.md` only for context or recovery, remove it from the **Exact Planned Permanent Transfers** rather than duplicating it in the permanent files.

Never silently overwrite established canon. Corrections, legitimate in-fiction changes, and permanent transfers must follow the proper state owner and the existing save workflow so the repository remains internally consistent.
