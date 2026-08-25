# ChatGPT-DnD

A persistent, choice-driven adult fantasy RPG repository for D&D-style campaigns played through ChatGPT, with d20 mechanics, persistent saves, relationship continuity, and optional generated scene art.

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

## Core party

Every numbered campaign has two required core PCs before Campaign Turn 1 begins:

- one male he/him **player-controlled PC**
- one female she/her **ChatGPT-controlled PC / co-protagonist**

Both use full PC character creation, advancement, inventory, and mechanical state. The ChatGPT-controlled co-protagonist is not an NPC. The two core PCs remain together as one party and do not split into solo or NPC-only side adventures unless the player explicitly changes that repository-wide rule for the campaign.

Marriage, romance, sexual activity, attraction, or another intimate relationship between the two core PCs is not assumed. Those facts exist only when established by that campaign's canonical state.

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
    GAME_MASTER_RULES.md   # Campaign 1-only rules overlay
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

Future campaigns use sibling folders such as `campaign-2`, `campaign-3`, and so on. They inherit the root and `campaigns/` rulebooks automatically. A new campaign needs a local `GAME_MASTER_RULES.md` only when it has campaign-specific operating, agency, behavior, or mechanical rules that belong in an overlay.

Campaign folders must not share character, NPC, world, quest, relationship, inventory, session, turn-save, pricing-reference, or art-continuity state unless the player explicitly requests it.

## Active campaign

`campaigns/active_campaign.json` selects the campaign currently in play. It is a pointer, not a duplicate live save.

Each campaign's own `active_game.json` is authoritative for that campaign's **last completed campaign state header**. During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

Before continuing play:

1. read the shared rule hierarchy
2. read `campaigns/active_campaign.json`
3. follow its pointer to the active numbered campaign
4. read that campaign's local rules overlay if one exists
5. read `active_game.json` and `turn_save.md`
6. use the `turn_save.md` status to recover, resume, review, verify, reset, or begin the next Campaign Turn correctly
7. read the other canonical state files needed for the current scene

## Campaign-local identity and state

Within each campaign, persistent NPCs receive stable campaign-local IDs such as `NPC-0001` in that campaign's `NPC-state.md`. Cross-file references use the stable NPC ID plus the NPC's current name for readability; names and Markdown headings are not identity keys.

The two required core PCs are stored as PC-format character state through `character_sheet.md`, `active_game.json`, and `inventory.md`. Each campaign also owns its own routine-item Base Price reference, world state, chronological session history, temporary Campaign Turn ledger, and visual-reference log.

## Campaign Turn summary

A **Campaign Turn** is the persistence/gameplay unit. One Campaign Turn may contain many numbered Steps, including conversation, exploration, multiple combat rounds, every combatant's individual D&D combat turns, and multiple occasions requiring dice rolls. Ending a creature's combat turn, ending a combat round, or even ending combat does not by itself end the Campaign Turn.

ChatGPT acts as GM/DM and determines when the connected gameplay unit has reached the end of the full Campaign Turn. Each campaign's `turn_save.md` remains the temporary authoritative ledger until that full Campaign Turn is intentionally completed, reviewed, confirmed, reconciled, verified, and separately approved for reset.

The complete lifecycle and recovery behavior are owned by `campaigns/GAME_MASTER_RULES.md`.

## Images

The repository-wide image play loop and player-managed generated-image-binary rule are owned by root `GAME_MASTER_RULES.md`.

Textual appearance canon remains in the state file that owns the character, NPC, location, or item. Each campaign's `art/art_log.md` owns verified reference-image paths and visual-reference continuity metadata rather than duplicating textual appearance authority. Image-path and reference-metadata staging during Campaign Turns follows `campaigns/GAME_MASTER_RULES.md`.

## Preservation

Preserve established chronological history by default. Update current mutable state in place when it changes through the approved persistence workflow. Detailed save, verification, correction, and recovery rules live in `campaigns/GAME_MASTER_RULES.md`.
