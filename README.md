# ChatGPT-DnD

A persistent, choice-driven adult fantasy RPG repository for D&D-style campaigns played through ChatGPT, with d20 mechanics, persistent saves, relationship continuity, and optional generated scene art.

## Core canon rule

The files on the repository's current branch are the campaign source of truth.

- Each numbered campaign is isolated from every other campaign unless the player explicitly requests a crossover or import.
- A fresh campaign begins only with facts established in its current files or established by the player during play.
- Do **not** recover character data, NPC data, items, locations, quests, relationships, story events, secrets, or other campaign canon from deleted material, prior chats, or repository history.
- Repository history may be consulted only for reusable **framework, file structure, mechanics, and operating instructions** when the player explicitly allows it.
- Prior chats are non-canonical unless the player explicitly imports information from them.

## Repository layout

```text
campaigns/
  README.md
  active_campaign.json
  campaign-1/
    README.md
    GAME_MASTER_RULES.md
    active_game.json
    turn_save.md
    character_sheet.md
    NPC-state.md
    inventory.md
    world_state.md
    session_log.md
    art/
      art_log.md
```

Future campaigns should use sibling folders such as `campaign-2`, `campaign-3`, and so on. Campaign folders must not share character, NPC, world, quest, relationship, inventory, session, turn-save, or art-continuity state unless the player explicitly requests it.

Within each campaign, persistent NPCs receive stable campaign-local IDs such as `NPC-0001` in that campaign's `NPC-state.md`. Cross-file references use the stable NPC ID plus the NPC's current name for readability; names and Markdown headings are not identity keys.

`campaigns/active_campaign.json` selects the campaign currently in play. Each campaign's own `active_game.json` is authoritative for that campaign's **last completed live save**: session, completed Campaign Turn, `current_scene_name`, location, completed PC advancement state, and save revision. During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`. Campaign 1 saves to Campaign 1, Campaign 2 saves to Campaign 2, and so on.

A **Campaign Turn** is the campaign persistence/gameplay unit. One Campaign Turn may contain many numbered steps, including conversation, exploration, multiple combat rounds, and every combatant's individual D&D combat turns. Ending a creature's combat turn, ending a combat round, or even ending combat does not by itself end the Campaign Turn.

Each campaign's `turn_save.md` is the temporary authoritative ledger for the **current unfinished Campaign Turn**. While its status is `in_progress`, recorded in-turn changes overlay the last completed state in `active_game.json` and the permanent campaign files. The ledger remains intact through the full Campaign Turn instead of pushing unresolved mid-turn state into permanent files.

## Adult campaign style

- Fantasy adventure may include combat, exploration, danger, mystery, humor, social play, romance, flirting, sexual tension, consensual sexual situations, and nudity.
- Sexual material can be a meaningful part of the campaign without being forced into every scene.
- Characters and NPCs may be under 18 for ordinary story roles. Under-18 characters may have age-appropriate crushes or romantic feelings. Teen crushes may include awkward, private, confusing, or "too grown-up to talk about" feelings shown through nonsexual cues such as embarrassment, looking away, changing the subject, becoming self-conscious, or trying too hard to impress the crush. The narration does not identify those private thoughts as sexual, describe fantasies or arousal, or otherwise sexualize the minor.
- Every character involved in sexual content, nudity, fertility, pregnancy, reproduction, or erotic imagery must be explicitly **18+**.
- Current sexual and reproductive content must be consensual. Nonconsensual abuse may exist only as non-erotic, non-graphic background/backstory, history, or villain motivation and must never be presented as erotic entertainment.
- Generated images may include adult sensuality or nudity when allowed by the image system. Nude or sexualized depicted characters must be explicitly 18+.

## Image play loop

Not every scene needs an image.

1. ChatGPT narrates the scene normally and presents any relevant choices.
2. If the scene genuinely deserves an image, ChatGPT ends the text with `Make image? Yes / No`.
3. If the player replies `Yes`, ChatGPT generates the image before resolving any gameplay choice for that scene. After the image is shown, the player makes the choices.
4. If the player replies `No`, ChatGPT skips image generation and immediately parses anything after `No` as the player's choices or freeform action, including compact replies such as `No, A, 1, E) ...`.
5. Before generating recurring characters, equipment, locations, transformations, scars, tattoos, or other established visuals, consult that campaign's `art/art_log.md`.
6. Textual campaign canon overrides conflicting generated-art details unless the player explicitly adopts the variation.

## Persistence

Before continuing a campaign, read `campaigns/active_campaign.json`, follow its pointer to the active campaign, then read that campaign's `active_game.json`, `turn_save.md`, and any other canonical files needed for the scene.

If `turn_save.md` is not `ready`, follow that campaign's recovery rules before starting a new Campaign Turn. During an active Campaign Turn, stage step-by-step changes in `turn_save.md`; do not finalize permanent campaign state merely because a combatant turn, combat round, or combat encounter ends.

When the **full Campaign Turn** ends, freeze the ledger and verify its final effective state and planned permanent transfers. Permanent reconciliation begins only after the player confirms the save review. After the permanent save is written, re-check the affected files and report that the save is complete while the temporary ledger is still intact. Reset `turn_save.md` only after a separate player confirmation.

Preserve established history by default. Add new information instead of casually rewriting, compressing, reorganizing, or deleting earlier campaign records.
