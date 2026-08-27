# Session Log and History

## Chronological log behavior

`session_log.md` is chronological and append-first.

The full pre-game character-creation and backstory phase remains `save_revision: 0` and does not create a series of checkpoint entries.

When character creation is complete and the player confirms the Campaign Turn 1 baseline, append one revision-1 completion entry.

Each completed Campaign Turn then receives one new checkpoint rather than replacing an older entry.

Every completed entry identifies:

- entry type
- completed `save_revision`
- Campaign Turn number when applicable
- relevant clock or clock range

## Character-creation completion entry

Do not append intermediate entries for individual character choices.

The single revision-1 entry records:

- character creation completed
- `save_revision: 1` established
- both required core PCs completed
- opening scene and location
- opening campaign clock
- especially important starting relationship, family, equipment, and world canon

Detailed current state remains in its owning files. The session log is not a duplicate character sheet or inventory.

## Completed Campaign Turns

Record a compact chronology of continuity-critical results, including when applicable:

- Start Clock, End Clock, and elapsed time
- material time jumps and scheduled events crossed
- important rolls and choices
- combat outcomes
- scene and location transitions
- discoveries, clues, quests, and consequences
- relationship changes
- conceptions, births, hatchings, family changes, or developmental milestones
- NPC and party changes
- important transactions or possession changes
- XP and advancement
- other facts needed to understand later state

The session log does not repeat every granular Step preserved in the temporary Turn ledger.

Campaign Turn 1 begins from revision 1. Its completed permanent save normally becomes revision 2.

## Clock chronology

Use the approved completed clock from `active_game.json` and the verified Turn clock range.

Do not reconstruct a clock from prose when the completed state provides the value. Do not omit a material time jump that affects deadlines, rests, durations, pregnancy, egg production, incubation, hatching, aging, or scheduled events.

## Corrections and preservation

Do not rewrite or compress useful older chronology merely for neatness.

When an entry is factually wrong or explicitly corrected, preserve useful history where practical by marking it corrected or superseded instead of silently erasing why current state changed.

Fresh-campaign isolation is governed by `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`. Append-first and correction behavior is governed by `STATE_OWNERSHIP_AND_PERSISTENCE.md`.
