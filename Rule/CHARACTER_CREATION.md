# Character Creation

## Required core PCs

Character creation must establish the required player-controlled PC and ChatGPT-controlled PC / co-protagonist before Campaign Turn 1 begins.

At minimum, establish for each required core PC:

- Name
- Age, explicitly 18+ for player characters participating in adult content
- Gender / pronouns, consistent with `CORE_PARTY_AND_CHARACTER_AGENCY.md` unless the player explicitly changes that rule for the campaign
- Species / ancestry, selected under `REPRODUCTIVE_SPECIES_CANDIDATE_CATALOG.md`
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

## Species / ancestry character-creation whitelist

`REPRODUCTIVE_SPECIES_CANDIDATE_CATALOG.md` is the repository-wide authority for the standard species / ancestry options available during character creation.

Under the global rules:

- the player-controlled PC must use one standard species listed in that catalog
- the ChatGPT-controlled PC / co-protagonist must use one standard species listed in that catalog
- any replacement PC, additional PC, or later-created core PC must use the same catalog
- ChatGPT must present only the current active-whitelist entries as ordinary species / ancestry choices
- an official character builder, sourcebook list, deleted file, Git history, prior chat, class, subclass, background, profession, title, transformation, disguise, or ancestry description cannot add another option by implication
- a subrace, regional form, setting variant, alternate lineage, third-party version, or hybrid lineage is unavailable unless explicitly approved

If the player requests a species or variation that is not in the active global whitelist, do not finalize it as character canon until one of the following occurs:

1. the player explicitly adds it to the global catalog and the corresponding reusable profile is established, or
2. the active campaign records an explicit campaign-specific species override in `campaigns/campaign-N/Rules/Campaign-N_Rules.md`.

A campaign-specific species option applies only to that campaign and must not be silently added to another campaign or promoted into the global catalog.

This restriction limits **PC character creation**, not the existence of creatures in the setting. Unlisted species may still appear as NPCs, monsters, wildlife, historical peoples, or world inhabitants when appropriate. They do not become globally selectable PCs or global crossbreeding participants merely because they appear in the fiction.

A hybrid child or adult hybrid does not automatically become a selectable character-creation lineage. It must be explicitly approved as a stable selectable lineage and receive the required biology before it can enter the global catalog or a campaign-specific roster.

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
2. validate each proposed PC species / ancestry against `REPRODUCTIVE_SPECIES_CANDIDATE_CATALOG.md` or an explicit applicable campaign-specific override before making it canonical
3. distinguish finalized player-established facts from discussion, examples, previews, and rejected options
4. write finalized facts to the correct state owners when persistence is useful or necessary
5. keep duplicated representations synchronized, including Level/XP mirrors in `character_sheet.md` and authoritative advancement state in `active_game.json`
6. keep starting equipment, currency, consumables, and other starting resources synchronized with `inventory.md` as they become established
7. leave required-but-undecided fields blank rather than inventing them
8. keep `save_revision: 0`, `campaign_turn_number: 0`, and `character_created: false`
9. keep `turn_save.md` ready for Campaign Turn 1 rather than using it as a character-creation ledger

Repository writes made during revision-0 character creation are persistence of the same pre-game baseline, not separate save revisions.

## Final character-creation review

Before revision 0 may end, verify that every required character-creation field above is established for both required core PCs.

Also verify at minimum:

- each required core PC's species / ancestry exactly matches an active standard entry in `REPRODUCTIVE_SPECIES_CANDIDATE_CATALOG.md` or an explicit applicable campaign-specific override
- no unapproved subrace, variation, alternate lineage, hybrid lineage, or unlisted species was made canonical
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

## GM-authored opening frame for revision 1

The player is not required to provide a title, destination, opening quest, opening location, or predetermined first-scene activity.

After the player confirms that character creation is complete, ChatGPT as GM/DM creates the campaign's opening narrative frame and uses that frame to establish the revision-1 starting scene and location.

The opening frame should be consistent with all completed character/backstory canon and any already-established world facts, but otherwise ChatGPT may freely create the initial situation, surroundings, time, atmosphere, nearby NPCs, hooks, complications, and other GM-controlled world details needed to begin play.

For that opening frame:

- set `active_game.json.current_scene_name` to a concise scene label chosen by ChatGPT that describes where the fiction currently is and/or what is presently happening
- replace the pre-game `Character creation` scene label; do not carry that label into the completed revision-1 gameplay baseline
- set `active_game.json.current_location` to the actual starting location established by the opening narration
- record persistent world facts introduced by the opening frame in their proper owners when needed for continuity
- keep the scene name descriptive rather than prescriptive
- do not ask the player to invent or approve a scene title merely to start the campaign
- do not interpret the scene name as requiring the player-controlled PC to remain there, perform the activity named by the scene, follow a particular quest, or make a predetermined decision

A scene label may later change whenever the fiction changes. The current story determines the label; the label never determines what the story is allowed to become.

Creating this opening frame establishes the revision-1 starting situation but does not choose the player-controlled PC's first action or dialogue and does not itself create a Campaign Turn Step. Campaign Turn 1 gameplay begins only after the revision-1 baseline is complete and the Turn ledger changes from `ready` to `in_progress`.

GM authorship and player-agency boundaries are defined in `GM_BEHAVIOR_AND_PRIORITY.md` and `CORE_PARTY_AND_CHARACTER_AGENCY.md`.

## Transition from revision 0 to revision 1

If the player says **Yes** to the final character-creation review:

1. ensure every final character-creation fact is written to its proper permanent owner
2. synchronize all required duplicated representations
3. have ChatGPT create the GM-authored opening frame described above
4. replace `active_game.json.current_scene_name` with ChatGPT's concise scene label for that opening frame
5. set `active_game.json.current_location` to the actual starting location established by that opening frame
6. persist any continuity-relevant opening world facts to their proper owners
7. set `active_game.json.character_created` to `true`
8. keep `active_game.json.campaign_turn_number` at `0` because Campaign Turn 1 has not completed or begun merely from this transition
9. set `active_game.json.save_revision` from `0` to `1`
10. set `active_game.json.last_sync_note` to a compact statement that character creation is complete and revision 1 is the starting baseline for Campaign Turn 1
11. append one chronological `session_log.md` entry recording character creation completion and establishment of the revision-1 Campaign Turn 1 starting baseline; do not fabricate intermediate character-creation checkpoint entries
12. keep `turn_save.md.Campaign Turn` at `1`, keep `Status` as `ready`, keep `Current Step` at `0`, set `Current Scene` to the same opening scene label stored in `active_game.json.current_scene_name`, and set `Base save revision` from `0` to `1`
13. do not create a Campaign Turn Step and do not set `turn_save.md` to `in_progress` merely because character creation completed

Whenever tooling permits an atomic multi-file commit, the final synchronized character-creation state, opening-frame persistent state, the single completion entry in `session_log.md`, `active_game.json`, and the `turn_save.md` baseline update should be committed together.

If writes must occur sequentially, update supporting permanent state first, then the session log and ready Turn ledger, and update `active_game.json` last as the authoritative completion marker. Verify the resulting revision-1 baseline before starting Campaign Turn 1.

## Campaign Turn 1 starting condition

Campaign Turn 1 starts from revision 1.

Immediately before Campaign Turn 1 begins, the expected baseline is:

- `active_game.json.campaign_turn_number: 0`
- `active_game.json.character_created: true`
- `active_game.json.save_revision: 1`
- `active_game.json.current_scene_name`: ChatGPT's current descriptive opening-scene label, not `Character creation`
- `active_game.json.current_location`: the actual opening location established by ChatGPT's opening narration
- `turn_save.md.Campaign Turn: 1`
- `turn_save.md.Status: ready`
- `turn_save.md.Current Step: 0`
- `turn_save.md.Current Scene`: matches the revision-1 opening scene label
- `turn_save.md.Base save revision: 1`

Starting Campaign Turn 1 changes the Turn ledger to `in_progress` but does not increment `save_revision`. Completing and permanently saving Campaign Turn 1 later advances `save_revision` from `1` to `2`.

Advancement authority is defined in `ADVANCEMENT_AND_XP.md`. General state ownership and save discipline are defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md` and `SAVES_VERIFICATION_AND_RECOVERY.md`.
