# Campaign 1

Persistent save folder for the first ChatGPT-DnD campaign.

## Status

- **Phase:** In play
- **Tone:** Anything Goes Sandbox
- **Session:** 1
- **Current live state:** See `../active_campaign.json` and `saves/active_game.json` for the current turn, scene, step, and XP.

## Canonical files

- `GAME_MASTER_RULES.md` — Campaign 1 mechanics, XP, per-turn continuity rules, and content boundaries.
- `saves/active_game.json` — compact machine-readable campaign state.
- `saves/character_sheet.md` — player character record and advancement progress.
- `saves/inventory.md` — item record.
- `saves/world_state.md` — locations, NPCs, factions, relationships, quests, and unresolved threads.
- `saves/session_log.md` — chronological checkpoints, rolls, and XP awards.
- `art/art_log.md` — visual continuity for generated art.

## Per-turn persistence

After every gameplay turn, synchronize the live campaign-state files listed in `GAME_MASTER_RULES.md`. A file with no substantive state change receives a last-sync/status marker instead of being silently skipped.

Treat this folder as self-contained. Future campaigns should use sibling folders such as `campaign-2`, `campaign-3`, and so on rather than sharing Campaign 1 state.
