## Advancement

Use numeric **cumulative XP** unless the player later chooses milestone advancement.

XP never resets when a character levels. `xp_current` means total XP earned during the campaign, and `xp_next_level` means the next cumulative total required to level up.

Default cumulative thresholds:

- Level 1: 0 total XP
- Level 2: 100 total XP
- Level 3: 500 total XP
- Level 4: 1000 total XP

Example: reaching 100 total XP advances a level-1 character to level 2. The character keeps 100 XP and then advances to level 3 upon reaching 500 total XP.

Higher thresholds must be added as needed. Each next-level XP threshold must be greater than the previous threshold and should increase by a reasonable amount for the higher level rather than using a trivial or flat increase. Define the next required threshold before a character can advance into a level whose threshold is not yet recorded.

Award XP for meaningful accomplishments such as encounters, discoveries, investigation, social breakthroughs, quest progress, dangerous exploration, clever solutions, and consequential failures that genuinely move the story forward. Do not award XP merely for rolling a die, and do not double-count the same accomplishment. Do **not** give the same amount of XP for everything. Determine a reasonable base amount for the accomplishment, then apply any bonus XP gain from established items, abilities, potions, food buffs, or other effects.

When an XP calculation produces a fractional result, use normal arithmetic rounding unless the effect explicitly defines another rule: `.5` or higher rounds up to the next whole XP, while anything below `.5` rounds down.

Campaign-specific advancement state authority and persistence rules live in `campaigns/GAME_MASTER_RULES.md`.

## PC advancement authority

The repository-wide gameplay rulebook owns **how** PC advancement works: XP mode, default thresholds, award logic, rounding, and level-up behavior.

Within each numbered campaign:

- `active_game.json` owns the authoritative **completed PC advancement state** through campaign-wide `xp_mode` and `character_advancement.<character>.level`, `xp_current`, and `xp_next_level`.
- `character_sheet.md` displays each core PC's Level and XP as synchronized human-readable mirrors of that completed state. Those mirror values do not override `active_game.json`.
- The required ChatGPT-controlled PC / co-protagonist uses the same PC-format advancement authority as the player-controlled PC. She is not routed through generic NPC advancement unless a campaign-specific rule explicitly says otherwise.
- During an active Campaign Turn, staged XP awards, threshold changes, and level changes belong in `turn_save.md` and temporarily overlay the completed permanent representations until approved reconciliation.
- After any completed save that changes PC advancement, the Level/XP mirrors in `character_sheet.md` must exactly match the authoritative values in `active_game.json`.