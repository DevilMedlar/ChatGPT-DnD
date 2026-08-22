# NPC State — Campaign 1

This file is the authoritative master record for persistent NPCs in Campaign 1.

It owns NPC identity, appearance, mechanical state, personality, relationship and attraction state, knowledge, secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC continuity.

`world_state.md` references NPCs where they matter to locations, factions, quests, clues, discoveries, or world consequences without duplicating their full records.

`inventory.md` expands the possessions of NPCs currently traveling with the party.

`turn_save.md` temporarily overlays NPC HP, position, resources, conditions, consumed items, charges, and other in-turn changes until end-turn reconciliation.

## Relationship / Attraction Field Convention

Relationship information is split into separate facts so that one label does not silently imply another.

- **Relationship status** records the NPC's general partnership state, such as single, dating, married, widowed, complicated, or another established status.
- **Current partner(s)** records established current partners.
- **Romantic interest(s)** records characters the NPC is romantically interested in when that interest has actually been established.
- **Sexual interest(s)** records established sexual interest for explicitly adult NPCs only.
- **Attraction toward DevilMedlar** and **Attraction toward Senpai** record target-specific attraction when relevant.
- **Other known attractions** records established attraction toward other characters.
- **Jealousy / rivalry** records relationship-linked jealousy, rivalry, or tension when established.
- **Established boundaries** records important romantic, social, or intimate boundaries.
- **Consent / availability notes** records relevant established facts without treating attraction, partnership status, friendship, favors, or a successful social roll as automatic consent.

`Single` does **not** mean romantically or sexually interested. `Married` does **not** mean uninterested in everyone else. Attraction, relationship status, boundaries, and consent are separate state facts and must not be inferred from one another.

For an NPC below 18, omit sexual-interest fields entirely. Age-appropriate nonsexual crush or romantic information may be recorded when relevant and must follow `GAME_MASTER_RULES.md`.

## Current Party NPCs

None established.

## Important NPC Index

None established.

When NPCs become persistent, list them here with a short role and a link to their record below.

Example format only:

```text
- **NPC Name** — role / relevance; see `#NPC-Name`
```

## NPC Record Template

Use the sections below when an NPC becomes important enough to track persistently. Not every NPC needs every optional section. Populate what is relevant and established rather than inventing filler.

---

## NPC Name

### Identity

- **Name:**
- **Age:**
- **Gender / pronouns:**
- **Species / ancestry:**
- **Level / CR:**
- **Class / archetype:**
- **Role / occupation:**
- **Faction / allegiance:**
- **Status:** Alive / Dead / Missing / Unknown
- **In party:** Yes / No

### Appearance

- **Height:**
- **Build:**
- **Hair:**
- **Eyes:**
- **Skin / scales / fur / etc.:**
- **Distinctive features:**
- **Typical clothing:**
- **Visible equipment:**
- **Scars / tattoos / markings:**
- **Other visual notes:**
- **Reference art:** See `art/art_log.md` when established

### Location / Party State

If the NPC is not currently traveling with the party, track where they can later be found when known:

- **Normal location:**
- **Current known location:**
- **Last seen:**
- **Can normally be found at:**

If the NPC is currently traveling with the party:

- **Current known location:** With party
- **In party:** Yes
- **Joined:**
- **Reason:**
- **Expected duration:**
- **Last non-party location:**

When `In party: Yes`, do not duplicate moment-to-moment movement here. The last completed party location belongs in `active_game.json`; unfinished-turn movement and combat position belong in `turn_save.md` until end-turn reconciliation.

When an NPC leaves the party, update this section with the place where they can later be found if known.

### Personality / Motivations

- **Personality:**
- **Values:**
- **Goals:**
- **Wants:**
- **Needs:**
- **Fears:**
- **Likes:**
- **Dislikes:**
- **Habits / mannerisms:**
- **Current priorities:**

### Relationship / Attraction Overview

- **Relationship status:**
- **Current partner(s):**
- **Romantic interest(s):**
- **Sexual interest(s):** Explicitly adult NPCs only
- **Attraction toward DevilMedlar:**
- **Attraction toward Senpai:**
- **Other known attractions:**
- **Jealousy / rivalry:**
- **Established boundaries:**
- **Consent / availability notes:**

#### Relationship with DevilMedlar

- **Disposition:**
- **Trust:**
- **Respect / fear:**
- **Attraction / romantic tension:**
- **Relationship role:**
- **Debts / favors:**
- **Promises / obligations:**
- **Important history:**

#### Relationship with Senpai

- **Disposition:**
- **Trust:**
- **Respect / fear:**
- **Attraction / romantic tension:**
- **Relationship role:**
- **Debts / favors:**
- **Promises / obligations:**
- **Important history:**

#### Other Important Relationships

Record other established partners, family, friends, rivals, employers, enemies, dependents, or other relationship ties when they matter.

### Knowledge / Secrets

Keep factual knowledge, beliefs, shared information, withheld information, and secrets separate when they differ.

- **What the NPC knows:**
- **What the NPC believes:**
- **Information already shared with the party:**
- **Information being withheld:**
- **Secrets known:**
- **Secrets personally held:**
- **False beliefs / misunderstandings:**

### Mechanical State

Use when the NPC is mechanically relevant. A minor noncombat NPC does not need a complete combat block unless play establishes one.

- **Level / CR:**
- **Class / archetype:**
- **XP / advancement state:** If this NPC uses individual advancement
- **HP / Max HP:**
- **Temporary HP:**
- **Armor Class:**
- **Initiative:**
- **Speed:**
- **Proficiency Bonus:**
- **Hit Dice / recovery resource:**
- **Passive Perception:**
- **Exhaustion / long-term strain:**

#### Ability Scores

- **Strength:**
- **Dexterity:**
- **Constitution:**
- **Intelligence:**
- **Wisdom:**
- **Charisma:**

#### Saving Throws

- 

#### Skills

- 

#### Attacks

##### Attack Name

- **Attack modifier:**
- **Damage:**
- **Damage type:**
- **Range / reach:**
- **Special effects:**

#### Features / Abilities / Spells

##### Feature or Ability Name

- **Description:**
- **Mechanical effect:**
- **Activation:**
- **Uses / charges:**
- **Recharge:**
- **Duration:**
- **Requirements:**
- **Stacking / exclusivity:**

#### Conditions / Ongoing Effects

- 

#### Resources

- **Spell slots:**
- **Class resources:**
- **Limited-use abilities:**
- **Other tracked resources:**

### Personal / Owned Items

This is the NPC's **master ownership list**. It remains here whether the NPC is in the party or not.

When the NPC is currently in the party, `inventory.md` expands mechanically relevant carried possessions for active bookkeeping. The ownership list here remains the master list of what belongs to the NPC.

#### Equipped

- 

#### Carried

- 

#### Stored / Elsewhere

- 

#### Important / Unique Items

- 

### Shop / Services

Use this optional section for merchants, smiths, healers, trainers, innkeepers, enchanters, information brokers, or other service NPCs.

Shop stock is **business inventory**, not the NPC's personal ownership list and not current-party inventory.

- **Business name:**
- **Business type:**
- **Owner / operator:**
- **Location:**
- **Currency accepted:**
- **Typical opening hours:**
- **Restock behavior:**
- **Special-order capability:**
- **Buy-back policy:**
- **Base markup / discount rules:**
- **Current party discount / markup:**
- **Reason for discount / markup:**

#### Current Shop Stock

| Item | Price | Qty | Type | Mechanics | Description |
|---|---:|---:|---|---|---|
|  |  |  |  |  |  |

For simple items, the table may be enough. For complicated weapons, armor, magical items, consumables, tools, cursed items, charged items, or items that grant abilities, add a detailed record below.

#### Detailed Shop Item Template

- **Item name:**
- **Price:**
- **Quantity:**
- **Type:**
- **Rarity:**
- **Damage / armor / defense:**
- **Attack modifier:**
- **Damage modifier:**
- **Damage type:**
- **Stat bonuses / penalties:**
- **Requirements:**
- **Charges / uses:**
- **Recharge:**
- **Attunement / bonding:**
- **Durability / condition:**
- **Known properties:**
- **Unidentified properties:** Yes / No
- **Description:**

##### Special Effect / Ability Template

- **Name:**
- **Description:**
- **Trigger / activation:**
- **Chance:** If random
- **Mechanical effect:**
- **Duration:**
- **Save / resistance:**
- **Stacking:**
- **Uses / charges:**
- **Recharge:**
- **Requirements:**
- **Immunities / limitations:**

##### Hidden Properties — GM / Continuity Only

Use only when an item actually has hidden, cursed, unidentified, or secret properties.

**Do not reveal hidden properties until identified, discovered, triggered, or otherwise legitimately learned in play.**

- 

#### Services

##### Service Name

- **Price:**
- **Time:**
- **Effect:**
- **Requirements:**
- **Limitations:**

### Quest / Story Role

Use this optional section for quest givers, mission contacts, targets, witnesses, missing persons, suspects, guides, faction representatives, villains, or other story-linked NPCs.

`NPC-state.md` records **this NPC's involvement**. `world_state.md` remains authoritative for the overall quest or mission state.

#### Associated Quests / Missions

- 

#### Current Involvement

- **Role:**
- **Current objective:**
- **What they asked DevilMedlar / Senpai to do:**
- **Information provided:**
- **Information withheld:**
- **Reward promised:**
- **Special conditions:**
- **Deadline:**
- **Consequences of success:**
- **Consequences of failure:**

### Continuity History

Keep a compact NPC-specific history of events that explain the NPC's current state, behavior, relationships, obligations, or role. Do not duplicate the entire `session_log.md`.

- **Session / turn:** Event or continuity change

## NPC Inventory Transfer Rule

When an NPC joins the party:

1. Keep the NPC's master ownership list in this file.
2. Add an expanded active inventory section for that NPC in `inventory.md` when their carried possessions need detailed bookkeeping.
3. During an unfinished turn, stage HP, item use, charges, ammunition, conditions, movement, and similar changes in `turn_save.md`.

When an NPC leaves the party:

1. Reconcile the NPC's final carried possessions and quantities from `inventory.md` and any unfinished-turn state into the master ownership list here.
2. Confirm the transfer is complete.
3. Update the NPC's off-party location when known.
4. Only then remove or collapse that NPC's expanded party-inventory section from `inventory.md`.

Do not let items disappear merely because party membership changed.

## Ownership Rule

- `NPC-state.md` owns NPC identity, appearance, stats, HP at the last completed save, abilities, conditions, relationship and attraction state, off-party location, party membership, master personal possessions, NPC-specific story involvement, shops, shop stock, services, and NPC-specific continuity.
- Relationship status, current partners, romantic interests, sexual interests, attraction, boundaries, jealousy, and consent / availability are separate facts and must not be inferred from one another.
- `inventory.md` owns expanded mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by **current party NPCs**. For NPCs, it does not replace the master ownership list here.
- Shop stock remains in the shop NPC's record here as business inventory and does not belong in `inventory.md` unless an item is actually acquired by a party member.
- `world_state.md` may reference NPCs for locations, factions, quests, clues, discoveries, and consequences without duplicating their full records.
- `world_state.md` owns overall quest and mission state; this file owns each NPC's involvement in those quests or missions.
- `session_log.md` records chronological events involving NPCs without replacing their current persistent state here.
- `turn_save.md` overlays this file and `inventory.md` during an unfinished gameplay turn.

## Fresh-Start Rule

Do not recover or reconstruct NPC canon from deleted files, repository history, previous chats, memory, or another campaign unless the player explicitly requests a specific import.
