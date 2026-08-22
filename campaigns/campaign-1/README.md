# Campaign 1

Fresh adult fantasy campaign. No prior campaign canon is imported.

## Live state authority

`active_game.json` is the authoritative **last completed live save** for Campaign 1.

It owns the current completed session, turn, scene, step, location, character-creation status, character levels, XP, save revision, and latest synchronization note. Do not duplicate changing completed live-state values in this README.

`turn_save.md` is the authoritative staging record for the **current unfinished gameplay turn**. While it is marked `in_progress`, its recorded in-turn changes overlay the last completed state until end-turn reconciliation is completed.

At initialization, Campaign 1 begins in character creation before the first resolved gameplay turn. Finalized character-creation choices may update their proper permanent files as completed save revisions without starting a gameplay turn.

## Canonical files

- `GAME_MASTER_RULES.md` — campaign rules, mechanics, adult-content rules, image workflow, file ownership, and persistence rules.
- `active_game.json` — authoritative last completed Campaign 1 live state and save revision.
- `turn_save.md` — temporary authoritative ledger for the current unfinished gameplay turn, step checkpoints, in-turn state, pending transfers, recovery, and end-turn reconciliation.
- `character_sheet.md` — DevilMedlar and Senpai statistics, abilities, traits, advancement, appearance, and personal state.
- `NPC-state.md` — authoritative NPC identity, statistics, abilities, traits, appearance, relationships, condition, and party-membership state.
- `inventory.md` — equipment, currency, consumables, evidence, and important carried items.
- `world_state.md` — locations, factions, quests, clues, discoveries, world consequences, and references to NPCs when relevant to world events.
- `session_log.md` — chronological resolved-turn checkpoints, rolls, choices, consequences, XP awards, and historical save checkpoints.
- `art/art_log.md` — canonical visual continuity and verified reference-art notes.

## Unfinished-turn rule

Before beginning or continuing gameplay, read `turn_save.md`.

- `ready` means no gameplay turn is currently unfinished.
- `in_progress` means resume that turn before starting another one.
- During an unfinished turn, use the last completed permanent state plus the changes recorded in `turn_save.md` as the effective current state.
- At end turn, reconcile only persistent or continuity-relevant results into their proper permanent files, verify the transfer, complete one save revision, and reset `turn_save.md` for the next turn.

## Fresh-start canon

Only information currently stored in this campaign or explicitly established by the player during this fresh campaign is canon.

Do not import character data, NPC data, items, locations, relationships, quests, story events, secrets, or visual canon from deleted material, previous chats, memory, other campaigns, or repository history.

Repository history may be used only for framework, mechanics, structure, templates, and instructions when the player explicitly permits it. Historical campaign content remains non-canonical.

When current records disagree, the player's newest explicit statement wins and the smallest necessary correction should be made.

## Image loop

Not every scene needs an image. When a scene genuinely deserves one, narration and choices come first and the response ends with `Make image? Yes / No`.

- `Yes` — generate the image first, then wait for the player's choice.
- `No` — skip the image and parse anything after `No` as the player's gameplay input, including replies such as `No, A, 1, E) ...`.
- Consult `art/art_log.md` before generating continuity-sensitive visuals.
