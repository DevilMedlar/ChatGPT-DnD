# World, Quests, and Continuity

## World-state ownership

`world_state.md` owns persistent world-level state, including:

- calendar name, seasons, named-date mapping, and planar/time-zone context
- scheduled events, appointments, deadlines, restocks, due dates, laying dates, hatching dates, and developmental milestones
- locations
- factions and organizations
- overall quests, missions, goals, and investigations
- clues and discoveries
- unresolved questions and mysteries known to the core PCs
- persistent world changes and consequences

It does not own the authoritative current clock, current party location, complete NPC records, character state, inventory, or unfinished-Turn state.

## Current clock and schedule separation

- `active_game.json.campaign_clock` owns the last completed current time.
- `turn_save.md` owns the unfinished Turn's live clock overlay.
- `world_state.md` owns the calendar's meaning and future scheduled timestamps.

Do not duplicate the current clock as a competing mutable field in `world_state.md`.

When time advances, compare the effective current clock against every relevant scheduled record. Resolve or stage crossed events chronologically. Do not silently skip an event because a time jump passed its timestamp.

## Calendar context

Until a named setting calendar is established, `Campaign Day` provides neutral sequential bookkeeping.

A later calendar may define:

- month and weekday names
- seasons
- holidays and festivals
- sunrise, sunset, tides, moons, or planar cycles
- mapping from named dates to Campaign Day numbers
- local time differences

Adding calendar lore does not reset elapsed time.

## Scheduled events and milestones

Every schedule record should include, when applicable:

- event or milestone name
- exact scheduled clock
- relevant people or stable NPC IDs
- location
- status
- consequence or notes

Possible records include:

- appointments and meetings
- quest deadlines
- travel arrivals
- shop openings or restocks
- effect expirations
- expected births
- egg-laying dates
- hatching dates
- developmental milestones

A scheduled event changes only through established play, an explicit effect, an approved correction, or a rule that genuinely changes its time.

## Persistent NPC references

Persistent NPC and child records belong in `NPC-state.md`.

When an NPC matters to a location, faction, schedule, quest, clue, discovery, or world consequence, `world_state.md` may reference the stable NPC ID and current name with only enough context to explain relevance.

Do not duplicate full NPC statistics, appearance, relationships, family record, inventory, shop stock, reproductive state, hybrid package, or continuity history.

## Relationships with world consequences

Core-PC relationships belong in `character_sheet.md`. Persistent NPC and family relationships belong in `NPC-state.md`.

Record relationship information in `world_state.md` only when it creates a persistent public, factional, legal, political, location, quest, or other world-level consequence.

## Locations

Location records may include:

- ownership
- services
- faction control
- hazards
- discovered features
- access conditions
- important events and schedules
- relevant NPCs by stable ID

Completed current party location belongs in `active_game.json`. Unfinished movement belongs in `turn_save.md`.

## Factions and organizations

Faction records may include goals, alliances, enemies, territory, reputation, scheduled plans, and persistent consequences while referencing NPC members by stable ID.

## Quests, missions, and goals

`world_state.md` owns overall objective state.

A quest may track:

- status
- quest giver and relevant NPCs by stable ID
- objective and progress
- known clues
- relevant locations
- reward
- exact deadline or time pressure
- success and failure conditions
- consequences
- unresolved questions

`NPC-state.md` may record an NPC's revealed personal involvement, motives, promises, information, or reward offer, but not the overall quest authority.

## Clues and discoveries

Record only facts, clues, and discoveries that have actually been told to, witnessed by, or discovered by the core PCs.

The two core PCs share all learned information under `CORE_PARTY_AND_CHARACTER_AGENCY.md`, so a separate knowledge split between them is unnecessary.

## Unresolved questions and mysteries

Questions, mysteries, suspected connections, and missing information known to the core PCs belong in `world_state.md` as questions.

Examples:

- `Who hired the attackers?`
- `Why was the northern gate left open?`
- `Is the old map genuine?`

Rules:

- Record the question and the known clues that created it.
- Do not record an untold answer, hidden GM solution, secret perpetrator, or undiscovered fact.
- If neither core PC has been told or discovered something, it does not need a persistent record.
- When the answer is revealed, record the discovered fact in the proper clue, discovery, quest, NPC, location, or consequence section and mark or remove the resolved question as appropriate.

## World changes and consequences

Persistent consequences may reference affected locations, factions, NPCs, families, shops, schedules, quests, or relationships without duplicating their full specialized records.

## Unfinished character creation

Unfinished character-creation choices remain with character creation until they create established world state.

General ownership is defined in `STATE_OWNERSHIP_AND_PERSISTENCE.md`. Time operation is defined in `CORE_GAME_MECHANICS.md`.
