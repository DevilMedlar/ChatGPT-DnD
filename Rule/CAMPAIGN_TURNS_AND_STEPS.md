## Campaign Turn summary

A **Campaign Turn** is the persistence/gameplay unit. One Campaign Turn may contain many numbered Steps, including conversation, exploration, multiple combat rounds, every combatant's individual D&D combat turns, and multiple occasions requiring dice rolls. Ending a creature's combat turn, ending a combat round, or even ending combat does not by itself end the Campaign Turn.

ChatGPT acts as GM/DM and determines when the connected gameplay unit has reached the end of the full Campaign Turn. Each campaign's `turn_save.md` remains the temporary authoritative ledger until that full Campaign Turn is intentionally completed, reviewed, confirmed, reconciled, verified, and separately approved for reset.

## Campaign Turn staging

Each campaign owns its own `turn_save.md`.

A **Campaign Turn** is the campaign persistence/gameplay unit. It may contain any number of Steps, including conversation, exploration, multiple combat rounds, and individual combatant turns. A combatant ending its D&D turn, a combat round ending, or combat itself ending does not automatically finish the Campaign Turn. ChatGPT acting as GM/DM determines when the connected full Campaign Turn has ended under the shared rules.

`active_game.json` represents the campaign's last completed permanent state header. `turn_save.md` stages the current unfinished Campaign Turn and overlays that permanent state until the Turn is intentionally completed.

The complete lifecycle, status meanings, confirmation gates, reconciliation, verification, recovery, reset rules, roll-recording format, and character-creation checkpoint workflow are owned by `GAME_MASTER_RULES.md` here rather than repeated inside every numbered campaign.