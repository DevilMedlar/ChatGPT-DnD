## Rule hierarchy

Shared rules are intentionally kept **outside** individual numbered campaign folders so a new campaign does not require another full rules audit or copy of the same rulebook.

- `GAME_MASTER_RULES.md` — repository-wide gameplay mechanics and behavior: core premise, required two-core-PC party structure, adult-content rules, homebrew lineage framework, character-creation requirements, d20 resolution, advancement math, combat, player/ChatGPT-controlled PC agency, dice ownership, image-generation behavior, reference-art behavior, and general priority order.
- `campaigns/GAME_MASTER_RULES.md` — shared numbered-campaign architecture: fresh-campaign isolation, append-first preservation, PC advancement state ownership, Campaign Turn lifecycle, character-creation checkpoint saves, file ownership, NPC persistence, vendor/shop persistence, visual-reference metadata staging, save revisions, verification, recovery, and session-log behavior.
- `campaigns/campaign-N/GAME_MASTER_RULES.md` — optional **campaign-local rules overlay only**. It contains campaign-specific operating rules, agency rules, behavior rules, mechanical overrides, or exceptional premises that would be wrong to impose on every campaign. Ordinary character, NPC, relationship, world, inventory, quest, and other campaign facts remain in their assigned state files.

When **rules themselves conflict**, use this order:

1. the player's newest explicit instruction for that campaign
2. that campaign's local rule overlay, when present
3. `campaigns/GAME_MASTER_RULES.md`
4. root `GAME_MASTER_RULES.md`

The campaign's canonical state files are not a lower-priority rule layer. Each state file remains authoritative for the facts and mutable state assigned to it by the ownership rules. Read rules and state together rather than using a generic rule to overwrite established state that belongs to another authority.

# Shared Game Master Rules

These rules apply to every numbered campaign in this repository unless a campaign explicitly establishes a narrower campaign-specific override.

Campaign-state architecture, Campaign Turn persistence, file ownership, recovery, NPC persistence, vendor persistence, and other shared numbered-campaign bookkeeping rules live in `campaigns/GAME_MASTER_RULES.md`. A numbered campaign may keep a local `GAME_MASTER_RULES.md` only for campaign-specific operating rules, agency rules, mechanical overrides, or exceptional premises that do not belong in the shared layers. Ordinary character, NPC, relationship, world, inventory, quest, and other campaign facts belong in their assigned state files rather than being duplicated into rule files.

The player's newest explicit statement overrides conflicting assistant-created material. Never silently overwrite established canon.

# Campaigns

Each numbered campaign lives in its own folder and keeps its own **canon and mutable state**. Shared numbered-campaign operating rules live here in `GAME_MASTER_RULES.md` so future campaigns do not need another full copy of the persistence architecture.

Repository-wide gameplay rules live one level above in `../GAME_MASTER_RULES.md`.

## Shared rule inheritance

Every numbered campaign inherits:

1. `../GAME_MASTER_RULES.md` — repository-wide gameplay rules, including the required two-core-PC party structure
2. `GAME_MASTER_RULES.md` — shared numbered-campaign persistence and ownership rules
3. an optional local `campaign-N/GAME_MASTER_RULES.md` — campaign-specific operating, agency, behavior, or mechanical overrides only

A local campaign rule file must not duplicate the shared rulebooks or ordinary campaign facts merely for convenience. Character, NPC, relationship, world, inventory, quest, and other state facts belong in their assigned state files.

# Shared Campaign Rules

These rules apply to every numbered campaign under `campaigns/` unless that campaign explicitly establishes a narrower local override.

Repository-wide gameplay mechanics and behavioral rules live in `../GAME_MASTER_RULES.md`. Each numbered campaign owns its own canon and mutable state. A campaign-local `GAME_MASTER_RULES.md`, when present, should contain only campaign-specific operating rules, agency rules, mechanical overrides, or exceptional premises rather than duplicating shared rules or ordinary state facts.

Throughout this file, references such as `active_game.json`, `turn_save.md`, `character_sheet.md`, `NPC-state.md`, `routine_item_prices.md`, `inventory.md`, `world_state.md`, `session_log.md`, and `art/art_log.md` mean the corresponding files inside the active numbered campaign folder.