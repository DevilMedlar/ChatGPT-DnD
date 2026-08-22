# MOCK World State

> **MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file shows the proposed full shape of a campaign `world_state.md`. None of the names, places, quests, prices, items, or events below belong to any campaign unless explicitly adopted.

# World State — Mock Campaign

## Important NPCs

### Greyford

- **Mara Stonehand**
  - Role: Blacksmith / shopkeeper
  - Location: Stonehand Smithy
  - See: `MOCK_NPC-state.md#Mara-Stonehand`

- **Captain Veyra**
  - Role: City Watch Captain / quest contact
  - Location: Greyford Watch Headquarters
  - See: `MOCK_NPC-state.md#Captain-Veyra`

### Ironwood Forest

- **Eldrin**
  - Role: Hunter / possible guide
  - Last known location: Northern Ironwood
  - See: `MOCK_NPC-state.md#Eldrin`

## Locations

### Greyford

- **Type:** Walled trade town
- **Region:** Western March
- **Known for:** Smithing, caravan trade, iron shipments
- **Current state:** Stable but suffering delayed trade deliveries
- **Important NPCs:** Mara Stonehand, Captain Veyra
- **Important businesses:** Stonehand Smithy
- **Known dangers:** Bandit activity on the North Road
- **Relevant quests:** Missing Caravan

### Stonehand Smithy

- **Owner:** Mara Stonehand
- **Type:** Blacksmith / weapons and armor shop
- **District:** Forge Quarter
- **Known services:** Weapons, armor, repairs, identification
- **Typical hours:** Morning to early evening
- **Relevant events:** Ore shipment overdue
- **See NPC:** `MOCK_NPC-state.md#Mara-Stonehand`

### North Road

- **Type:** Trade road
- **Connects:** Greyford to northern settlements
- **Known danger:** Recent bandit reports
- **Current relevance:** Missing Caravan quest

## Factions / Organizations

### Greyford Watch

- **Leader:** Captain Veyra
- **Headquarters:** Greyford Watch Headquarters
- **Purpose:** Town defense and law enforcement
- **Current goal:** Investigate trade-route attacks
- **Relationship with party:** Neutral / cooperative
- **See NPC:** `MOCK_NPC-state.md#Captain-Veyra`

### Greyford Crafts Guild

- **Notable member:** Mara Stonehand
- **Purpose:** Regulate local craftsmen and trade standards
- **Current concerns:** Iron shortage and rising material costs

## Active Quests / Goals

### Missing Caravan

- **Status:** Active
- **Quest giver:** Captain Veyra
- **Objective:** Locate the missing merchant caravan and determine what happened.
- **Current progress:** Investigation begun
- **Known clues:** Wagon tracks leave the North Road near Ironwood Forest
- **Relevant NPCs:**
  - Captain Veyra -> `MOCK_NPC-state.md#Captain-Veyra`
  - Mara Stonehand -> `MOCK_NPC-state.md#Mara-Stonehand`
  - Merchant Loran -> `MOCK_NPC-state.md#Merchant-Loran`
- **Relevant locations:** Greyford, North Road, Ironwood Forest
- **Reward:** 200 gp from the Watch; possible shop discount from Mara
- **Failure conditions:** Not yet established
- **Completion conditions:** Caravan fate confirmed and findings reported

## Clues / Discoveries

- The missing caravan was carrying iron ore for Stonehand Smithy.
- Wagon tracks leave the North Road before the usual checkpoint.
- Bandit involvement is suspected but not confirmed.

## Known Secrets

- None established as player-known secrets.

## World Changes / Consequences

- Delayed iron shipments have increased local weapon and armor prices.
- Stonehand Smithy may run out of common stock if the caravan is not recovered.

## Unresolved Threads

- Fate of the missing caravan
- Identity of whoever attacked or diverted it
- Whether the current trade disruption is connected to a larger faction

## Continuity Rule

This file owns world-facing facts: locations, factions, quests, discoveries, clues, and world consequences.

It references NPC names where relevant but does not duplicate full NPC identity, statistics, relationships, personal possessions, shop stock, or conditions. Those belong in `MOCK_NPC-state.md`.

The completed current party location would belong in a campaign's `active_game.json`; temporary in-turn movement would belong in `turn_save.md`.