## Active campaign

`campaigns/active_campaign.json` selects the campaign currently in play. It is a pointer, not a duplicate live save.

Each campaign's own `active_game.json` is authoritative for that campaign's **last completed campaign state header**. During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

The two required core PCs are stored as PC-format character state through `character_sheet.md`, `active_game.json`, and `inventory.md`. Each campaign also owns its own routine-item Base Price reference, world state, chronological session history, temporary Campaign Turn ledger, and visual-reference log.

Update current mutable state in place when it changes through the approved persistence workflow.

## Active campaign

`active_campaign.json` is a pointer only. It identifies which numbered campaign is currently active and the path to that campaign's `active_game.json`.

Live gameplay state does **not** belong in `active_campaign.json`. Completed Campaign Turn, completed/pre-game scene name, location, character-creation completion state, completed PC advancement state, save revision, and the latest synchronization note belong in the active campaign's own `active_game.json`. The current unfinished Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.

Campaign saves are isolated by folder:

- Campaign 1 saves to `campaign-1/` and uses `campaign-1/active_game.json`.
- Campaign 2 saves to `campaign-2/` and uses `campaign-2/active_game.json`.
- Campaign 3 saves to `campaign-3/` and uses `campaign-3/active_game.json`.
- Continue the same pattern for later campaigns.

Changing campaigns changes the pointer in `active_campaign.json`; it does not move, merge, or copy campaign state.