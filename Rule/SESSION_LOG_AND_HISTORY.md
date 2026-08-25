# Session Log and History

## Chronological log behavior

`session_log.md` is chronological and append-first.

Each completed character-creation checkpoint save and each completed Campaign Turn should be appended as a new checkpoint rather than replacing older checkpoints.

Every checkpoint should identify its checkpoint type and completed `save_revision`. Campaign Turn checkpoints should also identify their completed Campaign Turn number.

## Character-creation checkpoints

For character creation, record only the choices and derived state actually finalized by that confirmed checkpoint.

Do not log every option discussed, previewed, or rejected.

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

## Corrections and preservation

Do not rewrite or compress older chronological history merely for neatness.

When an older historical entry is factually wrong or explicitly corrected, preserve useful history whenever practical by marking it corrected or superseded rather than silently erasing why the current state changed.

Fresh-campaign isolation is defined in `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`. General append-first and correction behavior is defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`.
