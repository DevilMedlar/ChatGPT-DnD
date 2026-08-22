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
- `character_sheet.md` — DevilMedlar and Senpai statistics, abilities, traits, advancement, appearance, personal state, and established PC relationship continuity.
- `NPC-state.md` — authoritative master database for persistent NPC identity, appearance, stats, abilities, conditions, personality, relationship and attraction state, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, NPC knowledge/secrets, and NPC-specific continuity.
- `inventory.md` — detailed active mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by current party NPCs. For NPCs, `NPC-state.md` remains the master ownership list.
- `world_state.md` — locations, factions, overall quests/missions, clues, discoveries, world consequences, player-known world secrets, and lightweight references to NPCs where they matter to world state.
- `session_log.md` — chronological resolved-turn checkpoints, rolls, choices, consequences, XP awards, and historical save checkpoints.
- `art/art_log.md` — canonical visual continuity and verified reference-art notes.

## NPC / Inventory / World ownership

Persistent NPC information should be referenced rather than duplicated across multiple files.

- `world_state.md` answers **where and why an NPC matters to the world** and points to `NPC-state.md` for the full record.
- `NPC-state.md` answers **who the NPC is**, their persistent mechanical and relationship state, where they can be found when away from the party, what they own, their shop/services if applicable, and their personal role in quests or missions.
- `inventory.md` answers **what the active party is carrying and how those items currently work**, including expanded bookkeeping for current party NPC possessions.
- Shop stock stays in the relevant NPC's `NPC-state.md` record as business inventory until a party member actually acquires an item.
- `world_state.md` owns the overall quest/mission state; `NPC-state.md` owns each NPC's involvement in that quest or mission.
- `turn_save.md` temporarily overlays NPC HP, positions, item quantities, charges, ammunition, conditions, and similar changes during an unfinished gameplay turn.

When a current party NPC leaves, reconcile their final detailed party inventory back into that NPC's master ownership list in `NPC-state.md` before removing or collapsing the NPC's expanded inventory section.

## Relationship-state separation

For persistent NPCs, relationship status, current partners, romantic interests, sexual interests for explicitly adult NPCs, attraction, jealousy/rivalry, boundaries, and consent/availability are separate facts.

Do not infer romantic or sexual interest merely because an NPC is single, friendly, indebted to the party, traveling with the party, or has a positive relationship with DevilMedlar or Senpai.

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
