# World State — Campaign 1

Campaign 1 is active. Pre-game background canon remains established below.

## Important NPCs

None established. Persistent NPC records belong in `NPC-state.md`.

When an NPC matters to a location, faction, quest, clue, discovery, or world consequence, reference the NPC here with the stable NPC ID from `NPC-state.md`, the current NPC name for readability, and only enough context to explain why they matter.

Reference format:

```text
- **NPC-0001 — NPC Name** — role / world relevance; location if useful; see `NPC-0001` in `NPC-state.md`
```

The stable NPC ID is the cross-file identity key. Do not rely on a name-derived Markdown heading or anchor, because an NPC's name may change while the NPC ID does not.

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

Locations may reference relevant NPCs by stable NPC ID and current name and point to their `NPC-state.md` records. A location record may include things such as ownership, services normally available there, faction control, known hazards, discovered features, access conditions, and important events without copying the NPC's full record.

## Factions / Organizations

None established.

Faction records may reference important NPC members or leaders by stable NPC ID and current name and point to `NPC-state.md`, while this file remains authoritative for the faction's world-level status, goals, alliances, enemies, territory, reputation, and consequences.

## Active Quests / Goals

None established.

This section owns the **overall state of quests, missions, goals, investigations, and similar world objectives**.

When established, a quest or mission may track:

- status
- quest giver / relevant NPCs, using stable NPC IDs and current names with references to `NPC-state.md`
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

Clues and discoveries may reference the NPC who supplied, hid, misunderstood, or is affected by them by stable NPC ID and current name, but the NPC's knowledge and beliefs remain in `NPC-state.md`.

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

## Shared Rule Authority

Cross-file NPC identity, NPC/world ownership boundaries, shop/world ownership boundaries, completed-vs-in-turn location authority, fresh-campaign isolation, and persistence behavior are owned by `../GAME_MASTER_RULES.md`.

This file stores only Campaign 1's world-level canon and world-state schemas. `NPC-state.md` remains the persistent NPC master; `active_game.json` owns the last completed party location; `turn_save.md` owns temporary Campaign Turn movement and position changes.
