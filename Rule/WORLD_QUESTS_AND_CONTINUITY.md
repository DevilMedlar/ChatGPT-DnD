### NPCs in world state and quests

`world_state.md` may reference NPCs when they matter to locations, factions, quests, clues, discoveries, or consequences, but each persistent NPC reference must use the stable NPC ID and may include the current NPC name for readability. Do not rely on a name-derived Markdown heading or anchor as the identity key, and do not duplicate the full persistent NPC record.

`world_state.md` owns overall quest/mission state. `NPC-state.md` owns the NPC's personal involvement, motives, promises, information, rewards offered, conditions, and related continuity.

A shop's existence and location may be referenced in `world_state.md`, while the shop owner/operator's `NPC-state.md` record owns persistent business state, current shop stock, vendor pricing state, storefront presentation fields, and services. `routine_item_prices.md` separately owns the recurring Base Price authority for items explicitly classified there as routine/basic repeat goods.

## Important NPCs

Persistent NPC records belong in `NPC-state.md`.

When an NPC matters to a location, faction, quest, clue, discovery, or world consequence, reference the NPC here with the stable NPC ID from `NPC-state.md`, the current NPC name for readability, and only enough context to explain why they matter.

The stable NPC ID is the cross-file identity key. Do not rely on a name-derived Markdown heading or anchor, because an NPC's name may change while the NPC ID does not.

Do not duplicate NPC stats, full appearance, full relationship state, personal inventory, shop stock, or full continuity history here.

## Relationships

Player-character relationship canon and continuity belong in `character_sheet.md` and any applicable Campaign 1-specific rule overlay. Record relationship information here only when it creates a persistent world-level consequence involving a location, faction, quest, organization, public status, or similar world state.

## Locations

This section records persistent world locations and their established details.

Locations may reference relevant NPCs by stable NPC ID and current name and point to their `NPC-state.md` records. A location record may include things such as ownership, services normally available there, faction control, known hazards, discovered features, access conditions, and important events without copying the NPC's full record.

## Factions / Organizations

Faction records may reference important NPC members or leaders by stable NPC ID and current name and point to `NPC-state.md`, while this file remains authoritative for the faction's world-level status, goals, alliances, enemies, territory, reputation, and consequences.

## Active Quests / Goals

This section owns the **overall state of quests, missions, goals, investigations, and similar world objectives**.

`NPC-state.md` may record an NPC's personal involvement, promises, information, motives, rewards offered, or conditions, but the overall quest status remains here.

## Clues / Discoveries

Clues and discoveries may reference the NPC who supplied, hid, misunderstood, or is affected by them by stable NPC ID and current name, but the NPC's knowledge and beliefs remain in `NPC-state.md`.

## Known Secrets

Do not reveal a secret merely because it is stored elsewhere for GM continuity. This section contains secrets that have actually become player-known world information.

## World Changes / Consequences

Persistent consequences may reference affected NPCs, locations, factions, shops, services, quests, or player-character relationships when those relationships create a world-level consequence, without duplicating the full records owned elsewhere.

## Unresolved Threads

Character-creation decisions and unfinished player-character background or relationship details remain with their character-creation owners until they produce persistent world-state information.
