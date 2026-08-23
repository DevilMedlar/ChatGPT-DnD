# ChatGPT-DnD

A persistent, choice-driven adult fantasy RPG repository for D&D-style campaigns played through ChatGPT, with d20 mechanics, persistent saves, relationship continuity, and optional generated scene art.

## Rule hierarchy

Shared rules are intentionally kept **outside** individual numbered campaign folders so a new campaign does not require another full rules audit or copy of the same rulebook.

- `GAME_MASTER_RULES.md` — repository-wide gameplay mechanics and behavior: core premise, adult-content rules, homebrew lineage framework, character-creation requirements, d20 resolution, advancement math, combat, player agency, dice ownership, image-generation behavior, reference-art behavior, and general priority order.
- `campaigns/GAME_MASTER_RULES.md` — shared numbered-campaign architecture: fresh-campaign isolation, append-first preservation, PC advancement state ownership, Campaign Turn lifecycle, character-creation checkpoint saves, file ownership, NPC persistence, vendor/shop persistence, image metadata staging, save revisions, verification, recovery, and session-log behavior.
- `campaigns/campaign-N/GAME_MASTER_RULES.md` — optional **campaign-local overlay only**. It contains campaign-specific canon, exceptions, or overrides that would be wrong to impose on every campaign. It must not become another copy of the shared rulebooks.

When **rules themselves conflict**, use this order:

1. the player's newest explicit instruction for that campaign
2. that campaign's local rule overlay, when present
3. `campaigns/GAME_MASTER_RULES.md`
4. root `GAME_MASTER_RULES.md`

The campaign's canonical state files are not a lower-priority rule layer. Each state file remains authoritative for the facts and mutable state assigned to it by the ownership rules. Read rules and state together rather than using a generic rule to overwrite established state that belongs to another authority.

## Core canon rule

The files on the repository's current branch are the campaign source of truth.

- Each numbered campaign is isolated from every other campaign unless the player explicitly requests a crossover or import.
- A fresh campaign begins only with facts established in its current files or established by the player during play.
- Do **not** recover character data, NPC data, items, locations, quests, relationships, story events, secrets, or other campaign canon from deleted material, prior chats, or repository history.
- Repository history may be consulted only for reusable **framework, file structure, mechanics, and operating instructions** when the player explicitly allows it.
- Prior chats are non-canonical unless the player explicitly imports information from them.

Detailed enforcement belongs to the shared rule files above rather than being duplicated here.

## Repository layout

```text
GAME_MASTER_RULES.md
campaigns/
  README.md
  GAME_MASTER_RULES.md
  active_campaign.json
  campaign-1/
    README.md
    GAME_MASTER_RULES.md   # Campaign 1-only overlay
    active_game.json
    turn_save.md
    character_sheet.md
    NPC-state.md
    routine_item_prices.md
    inventory.md
    world_state.md
    session_log.md
    art/
      art_log.md
```

Future campaigns use sibling folders such as `campaign-2`, `campaign-3`, and so on. They inherit the root and `campaigns/` rulebooks automatically. A new campaign needs a local `GAME_MASTER_RULES.md` only when it has campaign-specific rules or canon that belong in an overlay.

Campaign folders must not share character, NPC, world, quest, relationship, inventory, session, turn-save, pricing-reference, or art-continuity state unless the player explicitly requests it.

## Active campaign

`campaigns/active_campaign.json` selects the campaign currently in play. It is a pointer, not a duplicate live save.

Each campaign's own `active_game.json` is authoritative for that campaign's **last completed live save**. During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

Before continuing play:

1. read the shared rule hierarchy
2. read `campaigns/active_campaign.json`
3. follow its pointer to the active numbered campaign
4. read that campaign's local overlay if one exists
5. read `active_game.json`, `turn_save.md`, and the other canonical state files needed for the scene

## Campaign-local identity and state

Within each campaign, persistent NPCs receive stable campaign-local IDs such as `NPC-0001` in that campaign's `NPC-state.md`. Cross-file references use the stable NPC ID plus the NPC's current name for readability; names and Markdown headings are not identity keys.

Each campaign owns its own routine-item Base Price reference, inventory, world state, chronological session history, temporary Campaign Turn ledger, and visual-continuity log.

## Campaign Turn summary

A **Campaign Turn** is the persistence/gameplay unit. One Campaign Turn may contain many numbered Steps, including conversation, exploration, multiple combat rounds, and every combatant's individual D&D combat turns. Ending a creature's combat turn, ending a combat round, or even ending combat does not by itself end the Campaign Turn.

Each campaign's `turn_save.md` remains the temporary authoritative ledger until the full Campaign Turn is intentionally completed, reviewed, confirmed, reconciled, verified, and separately approved for reset.

The complete lifecycle and recovery behavior are owned by `campaigns/GAME_MASTER_RULES.md`.

## Images

The repository-wide image play loop and player-managed generated-image-binary rule are owned by root `GAME_MASTER_RULES.md`.

Each campaign's `art/art_log.md` owns that campaign's visual-continuity metadata. Image-path and visual-canon staging during Campaign Turns follows `campaigns/GAME_MASTER_RULES.md`.

## Preservation

Preserve established history by default. Add new information instead of casually rewriting, compressing, reorganizing, or deleting earlier campaign records. Detailed save, verification, correction, and recovery rules live in `campaigns/GAME_MASTER_RULES.md`.
