## Active campaign

`campaigns/active_campaign.json` selects the campaign currently in play. It is a pointer, not a duplicate live save.

Each campaign's own `active_game.json` is authoritative for that campaign's **last completed campaign state header**. During an unfinished Campaign Turn, the live Campaign Turn number, Current Step, and Current Scene belong in that campaign's `turn_save.md`.
