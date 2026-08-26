# Canon, History, and Campaign Isolation

## Current-branch canon

The files on the repository's current branch are the campaign source of truth.

- Each numbered campaign is isolated from every other campaign unless the player explicitly requests a crossover or import.
- A campaign begins only with facts established in its current files or explicitly established by the player for that campaign.
- A campaign-specific rule applies only to the numbered campaign whose `Rules/Campaign-N_Rules.md` records it unless the player explicitly imports or promotes that rule elsewhere.
- Prior chats are non-canonical unless the player explicitly imports specific information from them.
- The player's newest explicit statement overrides conflicting assistant-created material.
- Never silently overwrite established canon.

## Fresh-start isolation

Do **not** recover, infer, reconstruct, or borrow character data, NPC data, items, locations, factions, relationships, quests, story events, secrets, rolls, consequences, visual canon, campaign-specific rules, or any other campaign content from:

- another campaign
- deleted files or deleted material
- repository history
- previous chats
- assistant memory

unless the player explicitly requests a specific import.

Repository history may be consulted only for reusable **framework, file structure, mechanics, templates, and operating instructions**, and only when the player explicitly allows that use.

Historical framework is never evidence that any historical character, NPC, item, location, relationship, quest, story fact, or campaign-specific rule exists in the current campaign.

Campaign folders must not share character, NPC, world, quest, relationship, inventory, session, turn-save, pricing-reference, art-continuity state, or campaign-specific rules unless the player explicitly requests a crossover or import.

## Preserving established history

Preserve established chronological history by default.

Historical records should not be rewritten, compressed away, or reorganized merely for neatness. Current mutable state may still be updated in place when it legitimately changes.

Detailed append-first, correction, and current-state replacement behavior is defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`.
