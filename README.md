# ChatGPT-DnD

A persistent chat-driven adult fantasy RPG repository designed to hold multiple independent campaigns.

## Repository layout

Each campaign lives in its own self-contained folder under `campaigns/`.

- `campaigns/active_campaign.json` — tells ChatGPT which campaign is currently active.
- `campaigns/campaign-1/` — Campaign 1 and all of its persistent state.
- Future campaigns should use sibling folders such as `campaigns/campaign-2/`, `campaigns/campaign-3/`, and so on.

Campaign folders must not share character, world, quest, relationship, inventory, session, or art-continuity state unless the player explicitly requests a crossover.

## Active campaign

**Campaign:** Campaign 1

**Path:** `campaigns/campaign-1/`

**Phase:** Character creation

**Tone:** Anything Goes Sandbox

**Session:** 0

**Current step:** Character identity

## Campaign 1 canonical files

- `campaigns/campaign-1/GAME_MASTER_RULES.md` — mechanics, continuity rules, and content boundaries.
- `campaigns/campaign-1/saves/active_game.json` — compact machine-readable state.
- `campaigns/campaign-1/saves/character_sheet.md` — human-readable player character sheet.
- `campaigns/campaign-1/saves/world_state.md` — locations, NPCs, factions, relationships, quests, consequences, and unresolved threads.
- `campaigns/campaign-1/saves/session_log.md` — chronological campaign summaries and checkpoints.
- `campaigns/campaign-1/art/art_log.md` — canonical visual details and generated-art continuity notes.

## Continuity rule

Before continuing play, read `campaigns/active_campaign.json`, then load the canonical files inside that campaign folder. After meaningful changes to the character, inventory, abilities, quests, relationships, world, or canonical visuals, update that campaign only.

All sexual or romantic characters must be unambiguously adults. Mature themes are allowed within platform safety limits; explicit sexual acts are handled non-graphically/fade-to-black, and generated art uses non-explicit sensual presentation with intimate anatomy obscured when necessary.
