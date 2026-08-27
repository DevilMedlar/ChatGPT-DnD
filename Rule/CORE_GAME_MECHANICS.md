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
- playable species packages in `PLAYABLE_CHARACTER_OPTIONS.md`
- cross-species reproduction and lineage rules
- relationship and agency rules
- shop-price modifier stacking and final-price rounding
- any explicit campaign-specific override in `campaigns/campaign-N/Rules/Campaign-N_Rules.md`

If a homebrew subject has not yet been mechanically defined, do not pretend that ordinary D&D supplies a rule for it when it does not. Research or establish the missing homebrew rule before using it as a permanent mechanic.

# Campaign clock

## Purpose

Every campaign uses one canonical in-world clock. It supplies the objective time needed for combat, travel, rests, appointments, shops, deadlines, spell and condition duration, conception limits, gestation, egg laying, incubation, hatching, aging, and every other time-dependent rule.

Do not infer elapsed time from message count, real-world time, chat-session length, or narrative convenience.

## Canonical representation

`active_game.json` stores the last completed campaign clock in this form:

```json
"campaign_clock": {
  "calendar": "Campaign Day",
  "day": 1,
  "time": "08:00:00"
}
```

Rules:

- `calendar` identifies the calendar or dating system.
- `day` is a positive integer.
- `time` uses the 24-hour `HH:MM:SS` format.
- `24:00:00` is never stored. Advancing beyond `23:59:59` increments `day` and continues from `00:00:00`.
- Until a setting calendar is established, use sequential `Campaign Day` numbering.
- A later named calendar may map its dates onto the same elapsed timeline without resetting or losing elapsed time.

## Clock ownership

- `active_game.json.campaign_clock` owns the last completed permanent clock.
- `turn_save.md` owns the Start Clock, Current In-Turn Clock, and staged time changes for an unfinished Campaign Turn.
- `world_state.md` owns calendar lore, seasons, named dates, deadlines, appointments, due dates, laying dates, hatching dates, and other scheduled events. It does not duplicate the authoritative current clock.
- `session_log.md` records the start clock, end clock, and elapsed time of completed Campaign Turns when useful for chronology.

During an unfinished Campaign Turn, the effective clock is the current `turn_save.md` clock overlay rather than the older completed clock in `active_game.json`.

## Initialization

A new campaign begins at:

```text
Campaign Day 1, 08:00:00
```

This is a neutral bookkeeping baseline, not an established sunrise, season, holiday, or world fact.

Out-of-fiction character-creation discussion does not advance the campaign clock. When character creation is confirmed, ChatGPT establishes the opening scene's actual day and time. It may retain the initialized value or set another explicit opening value consistent with established canon.

## Advancing time

Time advances only when in-fiction activity or an explicit rule consumes time.

For every material time change:

1. identify the activity or event
2. determine its duration from an applicable rule or a reasonable explicit estimate
3. state the duration before or when resolving the transition
4. add it to the current in-turn clock
5. record the new clock and reason in `turn_save.md`
6. check whether any scheduled event, deadline, effect, rest completion, pregnancy milestone, laying date, hatching date, or other time trigger was reached or crossed

ChatGPT must not silently jump substantial time merely to move the plot.

A brief action whose exact seconds do not matter may be grouped into a scene estimate. A material estimate must be stated and recorded rather than hidden.

## Common durations

- One Combat Round is 6 seconds.
- All turns within the same Combat Round occur during the same 6-second interval; do not add 6 seconds for every combatant.
- Ten consecutive Combat Rounds equal 1 minute.
- Use the current official duration for Short Rests and Long Rests.
- Use official travel pace, Speed, distance, terrain, and vehicle rules when applicable.
- A spell, condition, item, class feature, or other effect uses its stated duration.
- Conversation, shopping, searching, meals, crafting, treatment, downtime, and scene transitions use a reasonable explicit duration based on what actually occurs.
- Simultaneous activities consume the longest overlapping duration, not the sum of every participant's separate duration.

## Precision

Use seconds when combat or a short-duration effect requires them. Use minutes, hours, or days when that precision is sufficient.

Do not manufacture second-by-second bookkeeping for ordinary scenes merely to create false accuracy. The stored clock remains exact after applying the stated scene duration.

## Scheduled events

When the current clock reaches or passes a scheduled event:

- resolve or stage the event at its established time
- do not skip it because a larger time jump crossed its timestamp
- if several events are crossed, resolve them chronologically
- record missed, interrupted, completed, or changed events in the appropriate state owner

A deadline or biological milestone has no random delay unless an explicit rule creates one.

## Final Turn Review and save

The Final Turn Review must show:

- Campaign Turn Start Clock
- proposed End Clock
- total elapsed time
- the material reasons for elapsed time
- every scheduled event or deadline reached or crossed

At approved reconciliation, write the approved End Clock to `active_game.json.campaign_clock`. Verification must confirm that the completed clock exactly matches the approved Final Turn State.

## No secret time randomness

Time passage is arithmetic and established fiction, not a hidden roll.

When an explicit rule requires a random duration, ChatGPT states the roll and the player physically rolls it under `DICE_ROLLS_AND_REROLLS.md`.

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
