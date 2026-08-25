## Character creation

Character creation must establish the required player-controlled PC and ChatGPT-controlled PC / co-protagonist before Campaign Turn 1 begins.

At character creation, establish at minimum for each required core PC:

- Name
- Age, explicitly 18+ for player characters participating in adult content
- Gender / pronouns, consistent with the required core-party roles above unless the player explicitly changes that repository-wide rule for the campaign
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

Optional adult-character details may include romantic interests, sexual interests, boundaries, relationship goals, fertility/reproductive details, or other mature themes when the player chooses to establish them.

## Character creation and Campaign Turns

Character creation occurs before Campaign Turn 1. It uses **character-creation checkpoint saves**, not the Campaign Turn ledger. `turn_save.md` remains prepared for Campaign Turn 1 and is not opened, reconciled, or reset merely because character-creation choices are saved.

A character-creation checkpoint is a logical group of finalized choices that the player is ready to make permanent. Discussion, previews, rejected options, and unfinished choices do not create a checkpoint or increment `save_revision`.

Before writing a character-creation checkpoint:

1. determine the exact finalized choices and every permanent file that must change
2. calculate any derived values that depend on those choices and verify them against the established rules
3. prepare the proposed `session_log.md` checkpoint entry and the new `active_game.json.save_revision`
4. keep `campaign_turn_number` at `0` because no gameplay Campaign Turn has completed
5. keep `turn_save.md` unchanged and `ready`
6. show the player the finalized checkpoint and exact planned permanent changes
7. ask: `Confirm character-creation checkpoint save? Yes / No / Corrections`

If the player says **No**, write nothing and do not increment `save_revision`.

If the player gives **Corrections**, revise the proposed character-creation state and planned permanent changes, show the corrected checkpoint again, and ask for confirmation again.

If the player says **Yes**:

1. write only the confirmed permanent character-creation changes to their proper owners
2. synchronize duplicated required representations, including the Level/XP mirrors in `character_sheet.md` and authoritative PC advancement state in `active_game.json` when advancement is affected
3. append one chronological character-creation checkpoint to `session_log.md` identifying the completed save revision and summarizing only what that checkpoint finalized
4. update `active_game.json` last as the completed-save marker with the new authoritative state, a `save_revision` increment of exactly `1`, and a compact `last_sync_note`
5. do not change `campaign_turn_number` from `0` and do not create a Campaign Turn Step

Whenever tooling permits an atomic multi-file commit, the affected permanent files, `session_log.md`, and `active_game.json` must be committed together as the character-creation checkpoint save. There is no second reset gate because character creation has no temporary source ledger to erase.

If permanent files must be written sequentially, update the supporting permanent files and `session_log.md` first and `active_game.json` last. Do not report the checkpoint as complete until all required files have been reread and verified. If an interruption or partial write occurs, treat the checkpoint as incomplete; inspect the affected files, `session_log.md`, and `active_game.json.save_revision`, reconcile them to one confirmed state, and only then continue character creation.

After every character-creation checkpoint, verify at minimum:

- every confirmed choice landed in the correct permanent owner
- no undecided field or rejected option was invented or made canonical
- derived character values are internally consistent
- when Level/XP is involved, `character_sheet.md` mirrors exactly match `active_game.json.character_advancement`
- starting equipment and `inventory.md` agree whenever inventory was part of that checkpoint
- `session_log.md` contains exactly one corresponding character-creation checkpoint for the completed `save_revision`
- `campaign_turn_number` remains `0`
- `turn_save.md` remains `ready` for Campaign Turn 1 and was not used as a character-creation ledger
- `save_revision` advanced exactly once
- `last_sync_note` accurately describes the completed checkpoint
- `character_created` remains `false` until the final character-creation checkpoint
- no unrelated campaign state changed

The final character-creation checkpoint must additionally verify that every required character-creation field listed in the repository-wide `Character creation` rules is established for both required core PCs. It must also verify that each core PC's finalized starting equipment, starting currency, and other starting consumable/resource inventory are recorded in `inventory.md`, and any equipment summary in `character_sheet.md` agrees with that inventory state. Only that confirmed and verified final checkpoint sets `active_game.json.character_created` to `true`. Until then it remains `false`. Before Campaign Turn 1 begins, `active_game.json.current_scene_name` may continue to identify the current pre-game character-creation context; no live Campaign Turn Step exists outside `turn_save.md`.

Finalized character-creation choices use the shared confirmed character-creation checkpoint workflow in `../GAME_MASTER_RULES.md`.

This file stores Campaign 1's core player-character detail and synchronized human-readable Level/XP mirrors.

Repository-wide character-creation requirements are owned by `../../GAME_MASTER_RULES.md`. Fresh-campaign isolation, character-creation checkpoint behavior, and completed advancement-state ownership are owned by `../GAME_MASTER_RULES.md`.

The blank fields below are intentional and remain undecided until established during current Campaign 1 character creation. Currently established canon includes the names, ages, pronouns, and shared relationship history below.
