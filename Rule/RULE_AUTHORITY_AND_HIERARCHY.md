# Rule Authority and Hierarchy

## Central rule library

Reusable gameplay, character-option, campaign-clock, GM-behavior, campaign-architecture, persistence, reproduction, and continuity rules live in categorized files under `Rule/`.

Each numbered campaign may add a narrowly scoped persistent local-rule delta in:

`campaigns/campaign-N/Rules/Campaign-N_Rules.md`

`New-Sheets/` contains blank reusable structure and guidance. It is not a rule authority or live campaign state.

`CORE_GAME_MECHANICS.md` establishes D&D 5.5e / SRD 5.2.1 as the default for ordinary mechanics not replaced by a more-specific repository or campaign rule.

## Campaign-specific rule layer

A campaign-local rule file owns only explicit persistent rules and overrides scoped to that campaign, such as:

- mechanical overrides
- species, class, background, feat, or lineage additions
- exceptional premises
- agency or behavior overrides
- alternative calendars or time rules
- campaign-specific reproductive or compatibility rules
- explicit operating instructions intended to persist

Do not copy unchanged global rules into it merely for convenience.

Ordinary character, NPC, family, inventory, clock, relationship, world, quest, shop, session, and art facts are state, not local rules.

A campaign-specific rule never silently carries into another campaign or becomes global.

## Rule conflict order

When rules conflict, use this order:

1. the player's newest explicit instruction that applies to the current scope
2. an applicable persistent rule in the active campaign's local rule file
3. the most specific applicable categorized rule under `Rule/`
4. a more general applicable rule under `Rule/`
5. the ordinary D&D 5.5e / SRD 5.2.1 rule when no homebrew rule replaces it
6. `GM_BEHAVIOR_AND_PRIORITY.md` when no more-specific rule resolves the issue

The official D&D baseline is a default layer, not a higher authority than explicit homebrew.

Examples:

- `PLAYABLE_CHARACTER_OPTIONS.md` overrides the broader official species menu for PC creation.
- `REPRODUCTION_AND_LINEAGE.md` governs reproduction that ordinary D&D does not define.
- `DICE_ROLLS_AND_REROLLS.md` overrides ordinary GM dice ownership.
- `CORE_GAME_MECHANICS.md` owns the repository campaign clock.
- a campaign-local override may replace one of those rules only for its stated campaign and scope.

If equally specific current rules genuinely conflict and scope cannot resolve them, surface the conflict and follow the player's newest explicit direction. Do not invent a canon-changing answer.

## Subject ownership

Use the file that most directly owns the subject.

- adult boundaries and consent: `ADULT_CONTENT_AND_CONSENT.md`
- advancement and XP: `ADVANCEMENT_AND_XP.md`
- campaign setup and activation: `CAMPAIGN_SETUP_ACTIVATION_AND_NAVIGATION.md`
- Campaign Turn operation: `CAMPAIGN_TURNS_AND_STEPS.md`
- fresh-campaign isolation: `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`
- character-creation workflow: `CHARACTER_CREATION.md`
- selectable species and character-option mechanics: `PLAYABLE_CHARACTER_OPTIONS.md`
- ordinary mechanics and campaign clock: `CORE_GAME_MECHANICS.md`
- core-PC agency: `CORE_PARTY_AND_CHARACTER_AGENCY.md`
- all randomness and rerolls: `DICE_ROLLS_AND_REROLLS.md`
- GM priorities: `GM_BEHAVIOR_AND_PRIORITY.md`
- inventory and item state: `INVENTORY_EQUIPMENT_AND_ITEMS.md`
- NPC identity and party state: `NPCS_AND_PARTY_MEMBERSHIP.md`
- relationships: `RELATIONSHIPS_AND_SOCIAL_INTERACTIONS.md`
- reproduction, hybrid inheritance, birth, development, and later generations: `REPRODUCTION_AND_LINEAGE.md`
- save confirmation, verification, recovery, and reset: `SAVES_VERIFICATION_AND_RECOVERY.md`
- shops and pricing: `SHOPS_PRICING_AND_TRANSACTIONS.md`
- file/state ownership: `STATE_OWNERSHIP_AND_PERSISTENCE.md`
- world, schedules, quests, clues, and consequences: `WORLD_QUESTS_AND_CONTINUITY.md`

Do not duplicate one operating rule across several files merely to make it easier to find. Use clear cross-references.

## State is not a lower-priority rulebook

Campaign state files are not a lower-priority set of rules. They are authoritative for the facts assigned to them.

Read rules and state together:

- rules determine how the game operates
- state records what is currently true
- the live `turn_save.md` overlay temporarily modifies the older completed state
- a general rule does not silently erase established state
- legitimate gameplay changes state through the save workflow

The authoritative current clock, a character's established species, an NPC's stable ID, an existing relationship, an inventory quantity, a pregnancy, an egg, a due date, or a quest status remains a binding fact until properly changed.

## Scope and specificity

A specific rule applies only to the subject and circumstances it actually governs.

Examples:

- the True Dragon form accommodation solves True Dragon physical access; it does not grant every shapechanger reproductive eligibility
- the four-slot hybrid package governs inherited species mechanics; it does not grant class features or equipment
- the 24-hour conception limit governs conception checks; it does not redefine Long Rests
- the Campaign Day bookkeeping calendar does not establish a season, holiday, or sunrise without world-state canon

Do not broaden a narrow rule by implication.

## Canon corrections

Established canon must be read from its authoritative state owner and preserved during narration, calculations, clock advancement, Turn staging, Final Review, and reconciliation.

The player's newest explicit correction overrides conflicting assistant-created material.

When a canonical record is identified as wrong:

1. read its authoritative owner and the active Turn overlay
2. identify every dependent mirror, schedule, calculation, or cross-reference
3. during revision 0, correct the pre-game state directly and synchronize it
4. during gameplay, correct the temporary Turn record or proposed transfer first
5. recalculate affected clocks, deadlines, due dates, resources, inheritance, and Final Turn State
6. show a corrected review again when confirmation is required
7. reconcile only approved changes

An unchanged fact already present in its owner is not a new transfer. Remove it from Exact Planned Permanent Transfers rather than duplicating it.

Never silently overwrite established canon, choose between unresolved conflicting facts, or rewrite unrelated history for convenience.
