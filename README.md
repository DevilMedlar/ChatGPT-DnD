# ChatGPT-DnD

A persistent, choice-driven adult fantasy tabletop campaign run through ChatGPT with D&D-style mechanics, campaign saves, relationship continuity, and optional generated scene art.

## Campaign style

- Fantasy adventure with d20-style checks, combat, exploration, social play, consequences, leveling, equipment, quests, and persistent world state.
- Adult sexual themes, romance, flirting, erotic situations, and consensual sexual content may be part of play.
- Every character involved in romance, sexual content, nudity, fertility, pregnancy, or reproduction must be explicitly **18+**.
- Generated images may include adult sensuality or nudity when allowed by the image system.
- The campaign should never force sexual content into every scene. Adventure, danger, mystery, humor, combat, exploration, and ordinary character moments remain part of the game.

## Repository layout

```text
campaigns/
  active_campaign.json
  campaign-1/
    README.md
    GAME_MASTER_RULES.md
    active_game.json
    character_sheet.md
    inventory.md
    world_state.md
    session_log.md
    art/
      art_log.md
```

Each campaign is self-contained. Future games should use sibling folders such as `campaign-2`, `campaign-3`, and so on.

## Image workflow

Scene art is optional rather than automatic.

1. ChatGPT narrates the scene and presents any relevant choices.
2. If the scene genuinely deserves an image, ChatGPT ends with `Make image? Yes / No`.
3. `Yes` means generate the image first. Gameplay choices wait until after the image is shown.
4. `No` means skip the image. Any remaining text in the same reply is immediately treated as the player's gameplay choice or freeform action, including compact replies such as `No, A, 1, E) ...`.
5. Before generating recurring characters, equipment, transformations, locations, or other established visuals, consult `campaigns/campaign-1/art/art_log.md`.

## Source of truth

The current campaign files on the repository's current branch are canonical. Established facts should be preserved unless the player explicitly changes them or a correction is required for consistency.
