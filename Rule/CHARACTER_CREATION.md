# Character Creation

## Required core PCs

Character creation must establish the required player-controlled PC and ChatGPT-controlled PC / co-protagonist before Campaign Turn 1 begins.

At minimum, establish for each required core PC:

- Name
- Age, explicitly 18+ for player characters participating in adult content
- Gender / pronouns, consistent with `CORE_PARTY_AND_CHARACTER_AGENCY.md` unless the player explicitly changes that rule for the campaign
- Species / ancestry
- Class or homebrew class
- Background
- Ability scores
- Skill proficiencies
- Starting HP
- Armor Class
- Speed
- Starting equipment
- Core class / ancestry features
- Appearance

Blank character fields are intentionally undecided until established during character creation. Do not fill those blanks by recovering or guessing prior-campaign information.

Optional adult-character details may include romantic interests, sexual interests, boundaries, relationship goals, fertility/reproductive details, or other mature themes when the player chooses to establish them. Adult-content boundaries are defined in `ADULT_CONTENT_AND_CONSENT.md`.

## Revision 0 is the full character-creation phase

`save_revision: 0` covers the campaign's entire pre-game character-creation and backstory phase.

This includes both the facts supplied when the campaign is first initialized and the additional character, relationship, family, history, starting-inventory, appearance, mechanical, and campaign-premise facts established while character creation continues.

All such explicitly established character-creation facts are canonical while `save_revision` remains `0`.

Revision 0 is therefore not limited to a small initialization snapshot and does not end when the first additional character detail is finalized. It continues until character creation and required starting state are fully complete and the player confirms the transition into the Campaign Turn 1 starting baseline.

During revision 0:

- `active_game.json.campaign_turn_number` remains `0`
- `active_game.json.character_created` remains `false` until final completion
- `active_game.json.save_revision` remains `0`
- `turn_save.md` remains prepared for Campaign Turn 1 and is not opened for character-creation activity
- `turn_save.md.Base save revision` remains `0` until the final character-creation transition
- finalized character-creation and backstory facts may be written to their proper permanent state owners as they are explicitly established
- discussion, previews, rejected options, and undecided fields are not canonical merely because they were mentioned
- no intermediate character-creation choice increments `save_revision`
- no intermediate character-creation choice creates a Campaign Turn Step
- no intermediate character-creation choice requires a completed `session_log.md` save checkpoint

Revision 0 must not be used to invent filler, resolve undecided fields without the player, import another campaign's state, recover facts from chat memory, or treat guesses as canon.

A transcription error in revision-0 state may be corrected directly. A genuine change to an already established character-creation fact should be treated as the player's newest explicit character-creation direction and kept internally consistent across the applicable state owners, still without incrementing `save_revision` while character creation remains open.

## Working during character creation

As character creation proceeds:

1. establish choices and backstory collaboratively
2. distinguish finalized player-established facts from discussion, examples, previews, and rejected options
3. write finalized facts to the correct state owners when persistence is useful or necessary
4. keep duplicated representations synchronized, including Level/XP mirrors in `character_sheet.md` and authoritative advancement state in `active_game.json`
5. keep starting equipment, currency, consumables, and other starting resources synchronized with `inventory.md` as they become established
6. leave required-but-undecided fields blank rather than inventing them
7. keep `save_revision: 0`, `campaign_turn_number: 0`, and `character_created: false`
8. keep `turn_save.md` ready for Campaign Turn 1 rather than using it as a character-creation ledger

Repository writes made during revision-0 character creation are persistence of the same pre-game baseline, not separate save revisions.

## Final character-creation review

Before revision 0 may end, verify that every required character-creation field above is established for both required core PCs.

Also verify at minimum:

- all explicitly established backstory and relationship canon is recorded in the correct owner
- no rejected option or undecided required fact was made canonical
- derived character values are internally consistent
- `character_sheet.md` Level/XP mirrors exactly match `active_game.json.character_advancement`
- each core PC's finalized starting equipment, starting currency, consumables, ammunition, charges, and other starting resources are recorded in `inventory.md`
- any equipment summary in `character_sheet.md` agrees with `inventory.md`
- required campaign-specific rules, when any were explicitly established, are recorded in the campaign's `Rules/Campaign-N_Rules.md`
- `active_game.json.campaign_turn_number` is still `0`
- `active_game.json.save_revision` is still `0`
- `turn_save.md` is still `ready` for Campaign Turn 1 and has no character-creation Steps

Then show the player the completed character-creation state and any exact final corrections needed for consistency and ask:

`Confirm character creation complete and establish the Campaign Turn 1 baseline? Yes / No / Corrections`

If the player says **No**, keep revision 0 open and make no transition to revision 1.

If the player gives **Corrections**, apply or stage the requested character-creation corrections, re-run the final review, and ask again.

## Transition from revision 0 to revision 1

If the player says **Yes** to the final character-creation review:

1. ensure every final character-creation fact is written to its proper permanent owner
2. synchronize all required duplicated representations
3. set `active_game.json.character_created` to `true`
4. keep `active_game.json.campaign_turn_number` at `0` because Campaign Turn 1 has not completed or begun merely from this transition
5. set `active_game.json.save_revision` from `0` to `1`
6. set `active_game.json.last_sync_note` to a compact statement that character creation is complete and revision 1 is the starting baseline for Campaign Turn 1
7. append one chronological `session_log.md` entry recording character creation completion and establishment of the revision-1 Campaign Turn 1 starting baseline; do not fabricate intermediate character-creation checkpoint entries
8. keep `turn_save.md.Campaign Turn` at `1`, keep `Status` as `ready`, keep `Current Step` at `0`, and set `Base save revision` from `0` to `1`
9. do not create a Campaign Turn Step and do not set `turn_save.md` to `in_progress` merely because character creation completed

Whenever tooling permits an atomic multi-file commit, the final synchronized character-creation state, the single completion entry in `session_log.md`, `active_game.json`, and the `turn_save.md` base-revision update should be committed together.

If writes must occur sequentially, update supporting permanent state first, then the session log and ready Turn ledger, and update `active_game.json` last as the authoritative completion marker. Verify the resulting revision-1 baseline before starting Campaign Turn 1.

## Campaign Turn 1 starting condition

Campaign Turn 1 starts from revision 1.

Immediately before Campaign Turn 1 begins, the expected baseline is:

- `active_game.json.campaign_turn_number: 0`
- `active_game.json.character_created: true`
- `active_game.json.save_revision: 1`
- `turn_save.md.Campaign Turn: 1`
- `turn_save.md.Status: ready`
- `turn_save.md.Current Step: 0`
- `turn_save.md.Base save revision: 1`

Starting Campaign Turn 1 changes the Turn ledger to `in_progress` but does not increment `save_revision`. Completing and permanently saving Campaign Turn 1 later advances `save_revision` from `1` to `2`.

Advancement authority is defined in `ADVANCEMENT_AND_XP.md`. General state ownership and save discipline are defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md` and `SAVES_VERIFICATION_AND_RECOVERY.md`.
