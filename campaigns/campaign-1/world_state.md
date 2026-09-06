# World State

This file owns persistent world context. The current completed clock itself belongs in `active_game.json`; an unfinished Turn's current clock belongs in `turn_save.md`.

## Calendar and Time Context

Populate setting-level calendar facts only when established.

- **Calendar name:** Campaign Day
- **Current named date corresponding to the authoritative campaign clock:** No separate named date established
- **Season:**
- **Day / night or local light context:** Morning daylight in the prepared opening frame
- **Time-zone or planar-time notes:**
- **Calendar mapping notes:**

Do not duplicate the authoritative current clock as a competing mutable field. Use `active_game.json.campaign_clock` plus any open `turn_save.md` overlay.

## Scheduled Events, Deadlines, and Milestones

Record future events whose exact time matters.

| Event / milestone | Scheduled clock | Relevant people / stable IDs | Location | Status | Consequence or notes |
|---|---|---|---|---|---|
|  |  |  |  |  |  |

No scheduled deadline, appointment, effect expiration, or other timed milestone is established at the revision-1 baseline. Real-world waiting does not advance the campaign clock.

Possible records include appointments, quest deadlines, travel arrivals, festivals, shop restocks, effect expirations, expected births, egg-laying dates, hatching dates, and developmental milestones.

When time advances across a scheduled clock, resolve or stage the event chronologically under `../../Rule/CORE_GAME_MECHANICS.md` rather than silently skipping it.

## Important NPCs

Reference format:

```text
- **NPC-#### — NPC Name** — role / world relevance; location if useful; see the matching stable NPC ID in `NPC-state.md`
```

`NPC-####` is a format placeholder only. Actual persistent references use the NPC's assigned stable ID from `NPC-state.md`.

The prepared frame has only unnamed background adult market vendors and a porter; no persistent NPC identity, conversation, relationship, or party recruit is established. Assign a stable ID if an individual becomes persistent during play.

## Relationships

Cutlor and Seren's established relationship remains authoritative in `character_sheet.md`. No new relationship is created by the opening setup.

## Locations

### Briarbridge, east market square

A small riverside market town is the GM-selected starting location. The east square has cobbled paving, a covered public noticeboard, canvas-covered stalls, and a road leading to the east gate. Naming this starting location does not establish it as either PC's birthplace, childhood hometown, property, or place of militia service.

### Old Mill bridge

A local road landmark named on the opening notice. Its exact distance, condition, history, and any connected people or events are not established by the notice. No unrevealed explanation is stored.

## Factions / Organizations

## Active Quests / Goals

No quest is accepted and no reward, contract, payment, or obligation has been granted at the baseline. The public road-work notice in the prepared frame is an optional opportunity only, not a selected objective for either PC.

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

No investigation, conversation, check, or discovery has been resolved. The visible starting environment below is a setup snapshot, not evidence that either PC has inspected an object or chosen an action.

## World Changes / Consequences

Revision 1 establishes the starting frame only. No travel, accident, combat, shopping, resource expenditure, quest progress, or elapsed campaign time has been played.

## Unresolved Questions / Mysteries

Record only questions, mysteries, suspected connections, or missing information that the core PCs know about.

- Phrase each unresolved matter as a question.
- Include only the known clues that created the question.
- Do not record an untold answer, hidden GM solution, secret perpetrator, or undiscovered fact.
- If neither core PC has been told or discovered something, it does not need a record.
- When an answer is revealed, move the discovered fact to the proper section and mark or remove the resolved question.

## Prepared Opening Frame: Morning at Briarbridge

**Status:** Established as the revision-1 starting baseline, but presentation and gameplay are on hold at the player's explicit request. Do not narrate this opening or advance its events until the player asks to begin play. This section contains immediate scene setup, not hidden GM answers or predetermined outcomes.

- **Opening location:** Briarbridge, east market square, beside the sheltered edge of the public noticeboard. Cutlor and Seren start together as the core party, carrying their already-recorded equipment. No new pose, dialogue, intention, or first action is assigned to Cutlor.
- **Clock:** Use the unchanged opening clock in `active_game.json`; preparing the scene consumes no time.
- **Atmosphere:** Soft morning daylight, damp cobbles, the smell of fresh bread, and canvas stall awnings. No extreme-weather effect or check applies.
- **Nearby people:** Unnamed adult stallholders at their stands and an adult porter beside a stationary handcart. They are background figures, not newly established companions or speakers. No conversation has occurred.
- **Optional public hook:** A notice reads, "Paid road work: reports requested from the Old Mill bridge. Enquire at the east gate." It states no sum, deadline, danger, or accepted contract. Reading or acting on it is not assigned to either PC.
- **Visible complication:** The porter's loaded handcart has a damaged wheel and partially obstructs the square's roadward exit; there is room to walk around it. No accident has been narrated, no injury is established, and neither PC is obliged to help.
- **Player agency:** The square, the road, and other approaches remain available. No mission, rescue, destination, conversation, or combat is preselected.
- **Hold point:** Before the opening narration and before Campaign Turn 1 Step 1. No event advances merely because this frame is saved or because the conversation pauses.
