# Core Game Mechanics

## Core premise

Run a persistent, choice-driven adult fantasy RPG with D&D-style d20 mechanics, meaningful consequences, strong continuity, optional generated scene art, and mature themes.

The player physically rolls all dice after ChatGPT establishes that a roll is needed and states what dice are to be rolled. Detailed dice ownership and reroll behavior are defined in `DICE_ROLLS_AND_REROLLS.md`.

The campaign is not required to be sexual in every scene. Adult romance, sexual tension, explicit adult language, and mature themes may appear when appropriate, while combat, danger, exploration, mystery, humor, horror, travel, politics, treasure, ordinary conversation, and character development must have room to breathe.

Adult-content boundaries and consent requirements are defined in `ADULT_CONTENT_AND_CONSENT.md`.

## Official and homebrew rules research status

This repository intentionally uses a mixture of explicitly established homebrew rules and D&D-derived official mechanics. A single official D&D edition or rules-version baseline is **not** assumed to govern every subject unless such a global standard is deliberately established after the relevant research is completed.

- Categorized homebrew rules already established under `Rule/` govern their own subjects and are not displaced merely because an official D&D rule differs.
- For subjects intended to use official D&D mechanics, research the relevant official rules, available versions, and their interaction with the repository's existing rules before establishing a permanent global standard.
- Different mechanical subjects may require separate researched decisions rather than one repository-wide edition choice.
- An official-rules/version question that has not yet been researched and decided is an intentional **research/design topic**, not by itself a missing-rule, missing-state, or audit defect.
- Do not invent a global edition/version choice merely to resolve an undecided research topic.
- Once a global mechanical standard for a subject is deliberately established, record it in the appropriate reusable file under `Rule/` and apply it consistently unless the global rule is later changed.
- `campaigns/campaign-N/Rules/Campaign-N_Rules.md` is used only when the player explicitly changes or overrides the applicable global rule for that numbered campaign; it is not the normal owner of repository-wide mechanical standards.

A future review or repository audit should flag this area only when there is an actual contradiction, an established mechanic lacks the authority needed to use it consistently, or a previously decided standard is being applied inconsistently. The mere absence of one universal D&D edition declaration is not an issue.

## Ability scores

Use Strength, Dexterity, Constitution, Intelligence, Wisdom, and Charisma.

Ability modifier:

`floor((score - 10) / 2)`

Unless the player chooses another method, use the standard array:

`15, 14, 13, 12, 10, 8`

## Resolution system

For uncertain actions, use:

`d20 + ability modifier + proficiency when applicable + situational modifiers`

Typical DCs:

- 8 — easy under pressure
- 10 — routine
- 12 — moderate
- 15 — hard
- 18 — very hard
- 22 — exceptional

Natural 20s and natural 1s may produce especially strong narrative consequences when appropriate, but they do not make impossible actions possible.

## Skills

Track proficiency or expertise where relevant:

- Acrobatics
- Animal Handling
- Arcana
- Athletics
- Deception
- History
- Insight
- Intimidation
- Investigation
- Medicine
- Nature
- Perception
- Performance
- Persuasion
- Religion
- Sleight of Hand
- Stealth
- Survival

## Derived statistics

Track at minimum:

- Level
- XP and next-level threshold
- HP / Max HP
- Temporary HP
- Armor Class
- Initiative
- Speed
- Proficiency Bonus
- Passive Perception
- Conditions
- Exhaustion or equivalent long-term strain when used
- Temporary effects

Advancement details are defined in `ADVANCEMENT_AND_XP.md`, while combat-specific handling is defined in `COMBAT_ABILITIES_AND_EFFECTS.md`.
