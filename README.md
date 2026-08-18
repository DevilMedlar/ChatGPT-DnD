# ChatGPT-DnD

A persistent chat-driven adult fantasy RPG repository designed to hold multiple independent campaigns.

## Repository layout

Each campaign lives in its own self-contained folder under `campaigns/`.

- `campaigns/active_campaign.json` — tells ChatGPT which campaign is currently active and carries the compact live phase/session/turn/XP pointer.
- `campaigns/campaign-1/` — Campaign 1 and all of its persistent state.
- Future campaigns should use sibling folders such as `campaigns/campaign-2/`, `campaigns/campaign-3/`, and so on.

Campaign folders must not share character, world, quest, relationship, inventory, session, or art-continuity state unless the player explicitly requests a crossover.

## Active campaign

**Campaign:** Campaign 1

**Path:** `campaigns/campaign-1/`

**Phase:** In play

**Session:** 1

**Tone:** Anything Goes Sandbox

For the current turn, scene, step, and XP summary, use `campaigns/active_campaign.json` and `campaigns/campaign-1/saves/active_game.json` rather than duplicating volatile state here.

## Campaign 1 canonical files

- `campaigns/campaign-1/GAME_MASTER_RULES.md` — mechanics, XP rules, continuity rules, content boundaries, and the image decision workflow.
- `campaigns/campaign-1/saves/active_game.json` — compact machine-readable state.
- `campaigns/campaign-1/saves/character_sheet.md` — human-readable player character sheet and XP progress.
- `campaigns/campaign-1/saves/inventory.md` — inventory and equipment state for the player and party members.
- `campaigns/campaign-1/saves/world_state.md` — locations, NPCs, factions, relationships, quests, consequences, and unresolved threads.
- `campaigns/campaign-1/saves/session_log.md` — chronological campaign summaries, rolls, XP awards, and checkpoints.
- `campaigns/campaign-1/art/art_log.md` — canonical visual details and generated-art continuity notes.

## Continuity rule

Before continuing play, read `campaigns/active_campaign.json`, then load the canonical files inside that campaign folder that are relevant to the current scene.

After **every gameplay turn**, synchronize all live campaign-state files listed in `GAME_MASTER_RULES.md`. Even when HP, inventory, or art does not change, its corresponding live-state file receives an updated sync/status marker rather than being silently left behind. Static documentation is updated only when its documentation actually changes.

Never silently replace an established fact. The newest explicit player choice controls when records conflict, and the affected save files should be repaired to agree.

## XP

Campaign 1 uses numeric XP. Current XP and the next-level threshold are tracked in the active campaign pointer, active game state, character sheet, and session log.

## Image play loop

Not every scene needs an image. When a scene genuinely deserves one, finish the normal narration and choices, then ask `Make image? Yes / No`.

- `Yes` — generate the image first, using `art/art_log.md` for continuity. The player makes or resolves gameplay choices after seeing it.
- `No` — skip image generation. Any remaining text in the same reply is treated as the player's selections or freeform action, such as `No, A, 1, E) ...`.

Generated campaign art should be stored in the campaign `art/` root whenever a persistent repository copy can be created, and the art log should record the path.

## Adult-content rule

All characters involved in romance, nudity, sexual tension, sexual activity, fertility, pregnancy, breeding, or reproductive storylines must be explicitly 18+. Adult romance, sexuality, sensuality, nudity, fertility/pregnancy themes, and consenting cross-species lineage storylines may appear within platform limits. Generated art follows the same adult-only rule and the capabilities of the image system.
