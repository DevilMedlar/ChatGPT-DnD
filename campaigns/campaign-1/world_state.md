# World State — Campaign 1

Campaign 1 is active. Pre-game background canon remains established below.

## Important NPCs

None established. Persistent NPC records belong in `NPC-state.md`.

When an NPC matters to a location, faction, quest, clue, discovery, or world consequence, reference the NPC here with only enough context to explain why they matter and point to the full record in `NPC-state.md`.

Reference format:

```text
- **NPC Name** — role / world relevance; location if useful; see `NPC-state.md#NPC-Name`
```

Do not duplicate NPC stats, full appearance, full relationship state, personal inventory, shop stock, or full continuity history here.

## Relationships

- DevilMedlar and Senpai have loved one another since childhood.
- They married five years ago.
- Their relationship before both were 18 remained romantic and nonsexual.
- They are now both 20 and are consenting adult romantic and sexually active partners.
- Additional relationship and background details will be established during character creation.

## Locations

None established.

This section records persistent world locations and their established details. It does **not** track the party's current live location. The authoritative completed current location belongs in `active_game.json`; during an unfinished Campaign Turn, any temporary movement or position changes are staged in `turn_save.md` until Campaign Turn reconciliation.

Locations may reference relevant NPCs by name and point to their `NPC-state.md` records. A location record may include things such as ownership, services normally available there, faction control, known hazards, discovered features, access conditions, and important events without copying the NPC's full record.

## Factions / Organizations

None established.

Faction records may reference important NPC members or leaders and point to `NPC-state.md`, while this file remains authoritative for the faction's world-level status, goals, alliances, enemies, territory, reputation, and consequences.

## Active Quests / Goals

None established.

This section owns the **overall state of quests, missions, goals, investigations, and similar world objectives**.

When established, a quest or mission may track:

- status
- quest giver / relevant NPCs, with references to `NPC-state.md`
- objective
- current progress
- known clues
- relevant locations
- reward
- deadline or time pressure
- success conditions
- failure conditions
- consequences
- unresolved questions

`NPC-state.md` may record an NPC's personal involvement, promises, information, motives, rewards offered, or conditions, but the overall quest status remains here.

## Clues / Discoveries

None established.

Clues and discoveries may reference the NPC who supplied, hid, misunderstood, or is affected by them, but the NPC's knowledge and beliefs remain in `NPC-state.md`.

## Known Secrets

None established as player-known secrets.

Do not reveal a secret merely because it is stored elsewhere for GM continuity. This section contains secrets that have actually become player-known world information.

## World Changes / Consequences

- DevilMedlar and Senpai married five years ago.
- Family name: `(insert name here)` — to be replaced by the name Senpai and DevilMedlar choose together during character creation.

Persistent consequences may reference affected NPCs, locations, factions, shops, services, or quests without duplicating their full records.

## Unresolved Threads

- DevilMedlar and Senpai's family name will be decided during character creation.
- Remaining background-history details will be established during character creation.

## NPC / World Ownership Rule

- `world_state.md` owns locations, factions, overall quests/missions, clues, discoveries, player-known world secrets, and world consequences.
- `NPC-state.md` owns each persistent NPC's identity, appearance, stats, conditions, relationships and attractions, party membership, off-party location, master personal possessions, shop/services record, shop stock, knowledge/secrets, NPC-specific quest involvement, and continuity history.
- This file should point to `NPC-state.md` rather than duplicating full NPC records.
- A shop's **existence and location** may be referenced here. Its current stock, prices, services, and owner-specific business details belong in the relevant NPC record in `NPC-state.md`.
- `active_game.json` owns the last completed current party location.
- `turn_save.md` owns temporary Campaign Turn movement and position changes until full Campaign Turn reconciliation.

## Continuity Rule

Add new world information only when it is established during this campaign. Keep prior established facts unless they are explicitly corrected or superseded. Do not reconstruct world or story canon from deleted files, repository history, previous chats, memory, or other campaigns unless the player explicitly requests a specific import.

`NPC-state.md` owns persistent NPC identity, statistics, condition, relationships, party membership, master possessions, and NPC-specific continuity. This file should reference NPCs only where they matter to locations, factions, quests, clues, discoveries, or world consequences rather than duplicating their full records.

`active_game.json` owns the last completed current party location. `turn_save.md` owns temporary Campaign Turn movement and position changes until full Campaign Turn reconciliation. `world_state.md` owns the persistent facts about locations themselves.
