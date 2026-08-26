# Session Log and History

## Chronological log behavior

`session_log.md` is chronological and append-first.

Character creation does **not** create a series of save-revision checkpoints. The entire pre-game character-creation and backstory phase remains `save_revision: 0`.

When character creation is fully complete and the player confirms the transition into the Campaign Turn 1 starting baseline, append one character-creation completion entry for `save_revision: 1`.

Each completed Campaign Turn should then be appended as a new checkpoint rather than replacing older checkpoints.

Every completed log entry should identify its entry type and completed `save_revision`. Campaign Turn checkpoints should also identify their completed Campaign Turn number.

## Character-creation completion entry

Do not append intermediate entries merely because individual character choices, backstory details, relationship facts, equipment choices, or other creation details were finalized during revision 0.

At the end of character creation, append one compact entry that records:

- character creation completed
- `save_revision: 1` established
- revision 1 is the starting permanent baseline for Campaign Turn 1
- both required core PCs are complete
- any especially important starting canon needed to understand later history

The full detailed current character and starting-state facts remain in their owning state files; the session log is not a duplicate character sheet.

## Completed Campaign Turns

For gameplay, record continuity-critical events such as:

- important rolls
- meaningful choices
- consequences
- XP awards
- scene transitions
- discoveries and clues
- relationship changes
- combat outcomes
- important transactions or possession changes
- other events needed to understand later campaign state

The session log summarizes completed Campaign Turns and does not need every granular Step already preserved during the temporary Turn ledger.

Campaign Turn 1 begins from `save_revision: 1`. Its completed permanent save therefore normally becomes `save_revision: 2`.

## Corrections and preservation

Do not rewrite or compress older chronological history merely for neatness.

When an older historical entry is factually wrong or explicitly corrected, preserve useful history whenever practical by marking it corrected or superseded rather than silently erasing why the current state changed.

Fresh-campaign isolation is defined in `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`. General append-first and correction behavior is defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`.
