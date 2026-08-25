# World, Quests, and Continuity

## World-state ownership

`world_state.md` owns persistent world-level state, including:

- locations
- factions and organizations
- overall quests, missions, goals, and investigations
- clues and discoveries
- player-known world secrets
- unresolved world threads
- persistent world changes and consequences

It does not replace the specialized owners for character, NPC, inventory, or active-turn state.

## Persistent NPC references

Persistent NPC records belong in `NPC-state.md`.

When an NPC matters to a location, faction, quest, clue, discovery, or world consequence, `world_state.md` may reference that NPC using the stable NPC ID from `NPC-state.md`, with the current NPC name for readability and only enough context to explain why the NPC matters.

The stable NPC ID is the cross-file identity key. Do not rely on a name-derived Markdown heading or anchor.

Do not duplicate NPC stats, full appearance, full relationship state, personal inventory, shop stock, or full continuity history in `world_state.md`.

## Relationships with world-level consequences

Core-PC relationship canon and continuity belong in `character_sheet.md`. Persistent NPC relationship state belongs in `NPC-state.md`.

Record relationship information in `world_state.md` only when it creates a persistent world-level consequence involving a location, faction, quest, organization, public status, or similar world state.

## Locations

Location records may include established details such as:

- ownership
- services normally available there
- faction control
- known hazards
- discovered features
- access conditions
- important events
- relevant NPCs by stable NPC ID and current name

`world_state.md` does **not** track the party's current live location.

The authoritative completed current location belongs in `active_game.json`. During an unfinished Campaign Turn, temporary movement or position changes belong in `turn_save.md` until reconciliation.

## Factions and organizations

Faction records may reference important NPC members or leaders by stable NPC ID and current name while `world_state.md` remains authoritative for world-level faction state such as goals, alliances, enemies, territory, reputation, and consequences.

## Quests, missions, and goals

`world_state.md` owns the **overall state** of quests, missions, goals, investigations, and similar world objectives.

When useful, a quest or mission may track:

- status
- quest giver or relevant NPCs by stable NPC ID and current name
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

`NPC-state.md` may record an NPC's personal involvement, promises, information, motives, rewards offered, or conditions, but the overall quest status remains in `world_state.md`.

## Clues and discoveries

Clues and discoveries may reference the NPC who supplied, hid, misunderstood, or is affected by them by stable NPC ID and current name, but the NPC's knowledge and beliefs remain in `NPC-state.md`.

## Known secrets

Do not reveal a secret merely because it is stored elsewhere for GM continuity.

The `Known Secrets` section of `world_state.md` contains secrets that have actually become player-known world information.

## World changes and consequences

Persistent consequences may reference affected NPCs, locations, factions, shops, services, quests, or player-character relationships without duplicating the full records owned elsewhere.

## Unresolved threads

Use unresolved world threads for persistent world-level questions or consequences that genuinely belong to world state.

Character-creation decisions and unfinished player-character background or relationship details remain with their character-creation owners until they produce persistent world-state information.

NPC/world identity boundaries are defined in `NPCS_AND_PARTY_MEMBERSHIP.md`. General state ownership and persistence are defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`.
