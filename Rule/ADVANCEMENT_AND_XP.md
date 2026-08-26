# Advancement and XP

## Official advancement baseline

Use the current D&D 5.5e cumulative Experience Point system from SRD 5.2.1.

XP never resets when a character gains a level. `xp_current` means the character's total accumulated XP, and `xp_next_level` means the next cumulative XP total required to gain a level.

Milestone advancement is not the repository default. Use it only if the player explicitly establishes it as a campaign-specific override.

## Official cumulative XP thresholds

Use these official cumulative thresholds:

- Level 1: 0 XP
- Level 2: 300 XP
- Level 3: 900 XP
- Level 4: 2,700 XP
- Level 5: 6,500 XP
- Level 6: 14,000 XP
- Level 7: 23,000 XP
- Level 8: 34,000 XP
- Level 9: 48,000 XP
- Level 10: 64,000 XP
- Level 11: 85,000 XP
- Level 12: 100,000 XP
- Level 13: 120,000 XP
- Level 14: 140,000 XP
- Level 15: 165,000 XP
- Level 16: 195,000 XP
- Level 17: 225,000 XP
- Level 18: 265,000 XP
- Level 19: 305,000 XP
- Level 20: 355,000 XP

When a character's XP total equals or exceeds a threshold, that character reaches the corresponding level and gains the official level benefits for that class/total character level.

For multiclass characters, advancement uses total character level exactly as defined by the official 5.5e rules.

## Awarding XP

Use official 5.5e XP values and guidance rather than a custom repository advancement curve.

For monsters, use the XP value associated with the creature's official Challenge Rating or stat block. XP may be awarded for defeating a monster in combat or otherwise neutralizing the threat when the official rules support that result.

For noncombat challenges, quests, discoveries, social accomplishments, exploration, and similar achievements, use the current official DM guidance for XP awards rather than assigning arbitrary values merely to force a desired leveling pace.

Do not award XP merely because a die was rolled, and do not count the same accomplishment more than once.

Do not create generic percentage XP bonuses, food-buff XP multipliers, potion XP bonuses, or similar advancement modifiers unless a specific explicit homebrew feature establishes one.

If a legitimate explicit homebrew effect modifies an XP award and creates a fractional XP result, use normal arithmetic rounding unless that effect defines another rule:

- `.5` or higher rounds up to the next whole XP
- below `.5` rounds down

## Level-up mechanics

When a character gains a level, apply the official 5.5e level-advancement rules for that character's class or multiclass combination, including applicable class features, Proficiency Bonus changes, Hit Points/Hit Dice, feats or Ability Score Improvements, spellcasting progression, subclass features, and other level-dependent mechanics.

Do not invent missing level benefits. Verify the applicable current official rule or established homebrew class rule.

## Core-PC name stability

Once a required core PC's canonical **Name** is finalized during character creation, that Name remains fixed for the campaign and is the stable key used for that PC's advancement record.

Titles, ranks, honorifics, epithets, nicknames, aliases, disguises, relationship labels, transformations, or similar descriptive changes do **not** change the canonical Name and do not change the advancement key.

When useful, a current title, rank, epithet, or similar mutable descriptor may be added as a small bullet under that PC's `Personal / Relationship Continuity` section in `character_sheet.md` and may later be updated or removed without changing the PC's Name.

A genuine transcription or data-entry mistake in the recorded Name may be corrected as an error correction. If such a correction changes the advancement key, update the key and all required mirrors/references together so no advancement state is lost or duplicated. This correction rule is for fixing an erroneous record, not for ordinary in-fiction renaming.

## PC advancement state authority

Within each numbered campaign:

- `active_game.json` owns the authoritative **completed PC advancement state** through campaign-wide `xp_mode` and `character_advancement.<character>.level`, `xp_current`, and `xp_next_level`.
- `xp_mode: cumulative` means the official cumulative XP system defined above.
- In `New-Sheets/active_game.json`, `PLAYER_CONTROLLED_PC_NAME` and `CHATGPT_CONTROLLED_PC_NAME` are template-only placeholder keys. Replace each with the corresponding core PC's actual established canonical Name when that Name is finalized; do not leave template placeholder keys in a completed character-creation save.
- Once replaced, those canonical Names are stable advancement keys for the campaign under the Core-PC name stability rule above.
- `character_sheet.md` displays each core PC's Level and XP as synchronized human-readable mirrors of that completed state. Those mirror values do not override `active_game.json`.
- The required ChatGPT-controlled PC / co-protagonist uses the same PC-format advancement authority as the player-controlled PC and is not routed through generic NPC advancement unless a campaign-specific rule explicitly says otherwise.
- During an active Campaign Turn, staged XP awards and level changes belong in `turn_save.md` and temporarily overlay the completed permanent representations until approved reconciliation.
- After any completed save that changes PC advancement, the Level/XP mirrors in `character_sheet.md` must exactly match the authoritative values in `active_game.json`.
- `xp_next_level` must always equal the next official cumulative threshold for the character's current level unless an explicit campaign-specific advancement override is active.

General persistence, save reconciliation, and Campaign Turn staging rules are defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`, `CAMPAIGN_TURNS_AND_STEPS.md`, and `SAVES_VERIFICATION_AND_RECOVERY.md`.
