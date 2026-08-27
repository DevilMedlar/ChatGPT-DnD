# World State

This file owns persistent world context. The current completed clock itself belongs in `active_game.json`; an unfinished Turn's current clock belongs in `turn_save.md`.

## Calendar and Time Context

Populate setting-level calendar facts only when established.

- **Calendar name:**
- **Current named date corresponding to the authoritative campaign clock:**
- **Season:**
- **Day / night or local light context:**
- **Time-zone or planar-time notes:**
- **Calendar mapping notes:**

Do not duplicate the authoritative current clock as a competing mutable field. Use `active_game.json.campaign_clock` plus any open `turn_save.md` overlay.

## Scheduled Events, Deadlines, and Milestones

Record future events whose exact time matters.

| Event / milestone | Scheduled clock | Relevant people / stable IDs | Location | Status | Consequence or notes |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

Possible records include appointments, quest deadlines, travel arrivals, festivals, shop restocks, effect expirations, expected births, egg-laying dates, hatching dates, and developmental milestones.

When time advances across a scheduled clock, resolve or stage the event chronologically under `../Rule/CORE_GAME_MECHANICS.md` rather than silently skipping it.

## Important NPCs

Reference format:

```text
- **NPC-#### — NPC Name** — role / world relevance; location if useful; see the matching stable NPC ID in `NPC-state.md`
```

`NPC-####` is a format placeholder only. Actual persistent references use the NPC's assigned stable ID from `NPC-state.md`.

## Relationships

## Locations

## Factions / Organizations

## Active Quests / Goals

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

## Clues / Discoveries

Record only facts and clues that have actually been told to, witnessed by, or discovered by the core PCs. The two core PCs share all learned information.

## World Changes / Consequences

## Unresolved Questions / Mysteries

Record only questions, mysteries, suspected connections, or missing information that the core PCs know about.

- Phrase each unresolved matter as a question.
- Include only the known clues that created the question.
- Do not record an untold answer, hidden GM solution, secret perpetrator, or undiscovered fact.
- If neither core PC has been told or discovered something, it does not need a record.
- When an answer is revealed, move the discovered fact to the proper section and mark or remove the resolved question.
