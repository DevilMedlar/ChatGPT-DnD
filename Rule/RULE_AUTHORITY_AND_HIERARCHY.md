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
