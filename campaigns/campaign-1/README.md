# Campaign 1

Fresh adult fantasy campaign. No prior campaign canon is imported.

## Live state authority

`active_game.json` is the authoritative **last completed live save** for Campaign 1.

It owns the current completed session, completed Campaign Turn, completed/pre-game scene label in `current_scene_name`, location, character-creation status, PC advancement state, save revision, and latest synchronization note. It does **not** own the live Campaign Turn Step. Completed PC advancement is stored through `xp_mode` and `character_advancement.<character>.level`, `xp_current`, and `xp_next_level`. Do not duplicate changing completed live-state values in this README.

`character_sheet.md` displays each PC's Level and XP as synchronized human-readable mirrors of the authoritative completed advancement state in `active_game.json`. During an active Campaign Turn, staged advancement in `turn_save.md` overlays both permanent representations until approved reconciliation.

`turn_save.md` is the authoritative temporary ledger for the **current unfinished Campaign Turn**. It owns the live Campaign Turn number, Current Step, and Current Scene while the Turn is active. While it is `in_progress`, its recorded in-turn changes overlay the last completed state. A Campaign Turn may contain multiple combat rounds, every combatant's individual D&D combat turns, scene changes, and post-combat or noncombat steps without resetting the ledger.

At initialization, Campaign 1 begins in character creation before the first Campaign Turn. Finalized character-creation choices are saved through confirmed **character-creation checkpoint saves** rather than through `turn_save.md`. Each completed checkpoint updates only the required permanent files, appends a chronological `session_log.md` checkpoint, increments `active_game.json.save_revision` exactly once, and is verified before being reported complete. The final character-creation checkpoint verifies the required creation fields before setting `character_created` to `true`. `campaign_turn_number` remains `0` until Campaign Turn 1 actually completes. Before Campaign Turn 1 begins, `active_game.json.current_scene_name` may describe the current pre-game character-creation context.

## Canonical files

- `GAME_MASTER_RULES.md` — campaign rules, mechanics, Campaign Turn lifecycle, character-creation checkpoint saves, save confirmations, recovery behavior, adult-content rules, image workflow, file ownership, advancement rules, and persistence rules.
- `active_game.json` — authoritative last completed Campaign 1 live state, including completed Campaign Turn, completed/pre-game `current_scene_name`, location, character-creation status, completed PC Level/XP advancement state, and save revision.
- `turn_save.md` — temporary authoritative ledger for the current unfinished Campaign Turn: Campaign Turn number, Current Step, Current Scene, numbered events, current in-turn state, pending transfers, final turn review, permanent-save verification, and reset approval. Character creation does not use this ledger before gameplay begins.
- `character_sheet.md` — DevilMedlar and Senpai statistics, abilities, traits, synchronized human-readable Level/XP mirrors, appearance, personal state, and established PC relationship continuity.
- `NPC-state.md` — authoritative master database for persistent NPC stable IDs, identity, appearance, stats, abilities, conditions, personality, relationship and attraction state, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, NPC knowledge/secrets, and NPC-specific continuity.
- `inventory.md` — detailed active mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by current party NPCs. For NPCs, `NPC-state.md` remains the master ownership list.
- `world_state.md` — locations, factions, overall quests/missions, clues, discoveries, world consequences, player-known world secrets, and lightweight references to persistent NPCs by stable NPC ID and current name where they matter to world state.
- `session_log.md` — chronological completed character-creation checkpoint saves and completed Campaign Turn checkpoints, including the completed save revision for each checkpoint.
- `art/art_log.md` — canonical visual continuity and verified reference-art notes.

## NPC / Inventory / World ownership

Persistent NPC information should be referenced rather than duplicated across multiple files. Every persistent Campaign 1 NPC receives one stable ID such as `NPC-0001` in `NPC-state.md`; the ID never changes or gets reused for another NPC. Cross-file references use that stable NPC ID plus the NPC's current name for readability rather than relying on name-derived Markdown headings or anchors.

- `world_state.md` answers **where and why an NPC matters to the world**, references persistent NPCs by stable NPC ID and current name, and points to `NPC-state.md` for the full record.
- `NPC-state.md` answers **who the NPC is**, owns the NPC's stable ID, persistent mechanical and relationship state, where they can be found when away from the party, what they own, their shop/services if applicable, and their personal role in quests or missions.
- `inventory.md` answers **what the active party is carrying and how those items currently work**, including expanded bookkeeping for current party NPC possessions.
- Shop stock stays in the relevant NPC's `NPC-state.md` record as business inventory until a party member actually acquires an item.
- `world_state.md` owns the overall quest/mission state; `NPC-state.md` owns each NPC's involvement in that quest or mission.
- `turn_save.md` temporarily overlays NPC HP, positions, item quantities, charges, ammunition, conditions, and similar changes during an unfinished Campaign Turn.

If an NPC joins or leaves during an active Campaign Turn, stage the party-membership, location, and inventory effects in `turn_save.md`; do not update the permanent NPC/inventory records merely because the transition occurred in the fiction.

At approved Campaign Turn reconciliation, when a current party NPC leaves, reconcile their final detailed party inventory back into that NPC's master ownership list in `NPC-state.md` before removing or collapsing the NPC's expanded inventory section.

## Relationship-state separation

For persistent NPCs, relationship status, current partners, romantic interests, sexual interests for explicitly adult NPCs, attraction, jealousy/rivalry, boundaries, and consent/availability are separate facts.

Do not infer romantic or sexual interest merely because an NPC is single, friendly, indebted to the party, traveling with the party, or has a positive relationship with DevilMedlar or Senpai.

## Campaign Turn rule

Before beginning or continuing gameplay, read `turn_save.md`.

- `ready` means no unfinished Campaign Turn exists and the next Campaign Turn may begin.
- `in_progress` means the Campaign Turn is active; use the last completed permanent state plus `turn_save.md` as the effective current state. `Current Step` and `Current Scene` in `turn_save.md` are the live gameplay position.
- `ending_review` means the full Campaign Turn end has been interpreted and the ledger is frozen for player review; no permanent writes or reset are allowed yet.
- `reconciling` means the player approved the final review and the permanent save is being written or verified.
- `saved_awaiting_reset` means the permanent Campaign Turn save is complete and verified; do not replay or resave it, and keep the ledger until the player confirms reset.

Ending a creature's Combat Turn, ending a combat round, or ending combat does not automatically end the Campaign Turn. The full Campaign Turn may continue into further combat rounds, dialogue, searching, movement, loot, discoveries, scene changes, or other connected steps.

At full Campaign Turn end, verify the complete final state and exact planned transfers and show them to the player. Permanent reconciliation requires explicit save confirmation. The final effective `Current Scene` becomes `active_game.json.current_scene_name` in the completed save. After the save is completed, re-check the affected permanent files and report success while the ledger remains intact. Reset requires a separate player confirmation.

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
- Visual continuity established or adopted during an active Campaign Turn is staged in `turn_save.md` and transferred to `art/art_log.md` only after Confirmation Gate 1 and approved Campaign Turn reconciliation.
