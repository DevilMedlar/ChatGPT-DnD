# Core Game Mechanics

## Core premise

Run a persistent, choice-driven adult fantasy RPG using the current D&D 5.5e rules engine for ordinary game mechanics, with explicitly established repository homebrew layered on top where this project intentionally differs.

The player physically rolls all dice after ChatGPT establishes that a roll is needed and states what dice are to be rolled. Detailed dice ownership and anti-fabrication behavior are defined in `DICE_ROLLS_AND_REROLLS.md`.

The campaign is not required to be sexual in every scene. Adult romance, sexual tension, explicit adult language, and mature themes may appear when appropriate, while combat, danger, exploration, mystery, humor, horror, travel, politics, treasure, ordinary conversation, and character development must have room to breathe.

Adult-content boundaries and consent requirements are defined in `ADULT_CONTENT_AND_CONSENT.md`.

## Official rules baseline

The repository-wide default for ordinary D&D mechanics is **D&D 5.5e using System Reference Document v5.2.1 (SRD 5.2.1)**.

Official reference entry point:

`https://www.dndbeyond.com/srd`

Use that current rules baseline whenever an ordinary D&D mechanic is needed and no more-specific repository rule explicitly replaces or modifies it.

This includes, when applicable:

- character creation mechanics
- ability scores and ability modifiers
- backgrounds and their mechanical benefits
- species mechanics
- classes, subclasses, multiclassing, and class features
- proficiency and expertise
- D20 Tests
- ability checks and skills
- saving throws
- Advantage and Disadvantage
- Difficulty Classes
- Armor Class
- initiative
- movement and Speed
- Actions, Bonus Actions, and Reactions
- attacks and damage
- Critical Hits
- damage types, Resistance, Immunity, and Vulnerability
- Hit Points, Temporary Hit Points, healing, dying, stabilization, and Death Saving Throws
- conditions and Exhaustion
- cover
- grappling and other combat actions
- opportunity attacks
- falling, suffocation, environmental hazards, and similar general hazards
- vision, lighting, hiding, Stealth, and Perception
- social-interaction mechanics
- exploration and travel mechanics
- Short Rests and Long Rests
- weapons, armor, tools, equipment, and ordinary item mechanics
- official currency values
- spellcasting, spell attacks, spell saves, spell slots, preparation, components, Concentration, and spell effects
- feats
- magic items and Attunement
- creature types
- monster stat blocks, Challenge Rating, and ordinary monster mechanics
- XP advancement and normal XP values
- other ordinary D&D mechanics covered by the current official rules

Do **not** invent a replacement mechanic merely because the repository does not restate an official rule locally. If an exact ordinary mechanic matters and is not summarized in the repository, consult the current official 5.5e rule and apply it.

## Homebrew relationship to the official baseline

The official 5.5e baseline does not erase intentionally established homebrew.

A more-specific current repository rule wins for the subject it explicitly governs. Examples include:

- player-owned dice rolling in `DICE_ROLLS_AND_REROLLS.md`
- Campaign Turn persistence and save workflow
- campaign isolation and state ownership
- cross-species reproduction and lineage rules
- relationship and agency rules
- shop-price modifier stacking and final-price rounding
- any explicit campaign-specific override in `campaigns/campaign-N/Rules/Campaign-N_Rules.md`

If a homebrew subject has not yet been mechanically defined, do not pretend that ordinary D&D supplies a rule for it when it does not. Research or establish the missing homebrew rule before using it as a permanent mechanic.

## Ability scores

Use Strength, Dexterity, Constitution, Intelligence, Wisdom, and Charisma under the official 5.5e character rules.

Ability modifier:

`floor((score - 10) / 2)`

Unless the player chooses another official permitted method, use the standard array:

`15, 14, 13, 12, 10, 8`

Under the 5.5e baseline, ordinary ability-score adjustments come from Background rather than Species unless an explicit homebrew rule says otherwise.

## D20 Tests and Difficulty Classes

For ordinary uncertain actions, use the official D20 Test structure:

`d20 + relevant ability modifier + Proficiency Bonus when applicable + other applicable modifiers`

If the total equals or exceeds the target number, the test succeeds unless a more-specific rule changes the resolution.

For ability checks, use the official typical DC scale when a specific rule does not already establish a DC:

- DC 5 — Very Easy
- DC 10 — Easy
- DC 15 — Medium
- DC 20 — Hard
- DC 25 — Very Hard
- DC 30 — Nearly Impossible

Use official Advantage and Disadvantage rules.

A natural 20 or natural 1 has the special automatic-hit/automatic-miss effect on **attack rolls** defined by the official rules. Do not turn natural 20s or natural 1s on ordinary ability checks or saving throws into automatic success or failure unless a specific applicable rule says so.

## Skills

Use the official skills and their normal 5.5e applications:

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

Track proficiency or Expertise where applicable under the official rules.

## Derived statistics

Track at minimum:

- Level
- XP and next-level threshold
- HP / Max HP
- Hit Dice
- Temporary HP
- Armor Class
- Initiative
- Speed
- Proficiency Bonus
- Passive Perception when relevant
- Saving Throw proficiencies
- Conditions
- Exhaustion
- Temporary and persistent mechanical effects

Advancement details are defined in `ADVANCEMENT_AND_XP.md`, while combat-specific handling is defined in `COMBAT_ABILITIES_AND_EFFECTS.md`.
