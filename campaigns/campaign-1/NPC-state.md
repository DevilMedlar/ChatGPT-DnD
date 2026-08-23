# NPC State — Campaign 1

This file is the authoritative master record for persistent NPCs in Campaign 1.

It owns NPC identity, appearance, mechanical state, personality, relationship and attraction state, knowledge, secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC continuity.

`world_state.md` references NPCs where they matter to locations, factions, quests, clues, discoveries, or world consequences without duplicating their full records. `inventory.md` expands the possessions of NPCs currently traveling with the party. `turn_save.md` temporarily overlays unfinished Campaign Turn changes.

Shared NPC ownership, relationship semantics, advancement, party-membership reconciliation, vendor/shop behavior, fresh-start isolation, and persistence rules are owned by `../GAME_MASTER_RULES.md`. Repository-wide adult-content boundaries are owned by `../../GAME_MASTER_RULES.md`.

## Stable NPC ID Convention

Every persistent NPC receives one stable Campaign 1 ID when the NPC is first added to this file.

- Use the form `NPC-0001`, `NPC-0002`, `NPC-0003`, and so on.
- Assign the next unused numeric ID in sequence.
- An NPC ID never changes because the NPC's name, title, role, location, relationship, party status, or life status changes.
- Never reuse an old NPC ID for a different NPC, even if the original NPC later dies, disappears, is retired from active play, or has their record corrected.
- Names and Markdown headings are human-readable display text; they are not the cross-file identity key.
- Cross-file references to a persistent NPC must include the stable NPC ID. The current NPC name may be included beside it for readability.
- If one NPC is ever found with multiple IDs, or two NPCs share one ID, stop and reconcile the identity conflict before completing another persistent save.

## Relationship / Attraction Field Convention

The shared meaning and separation of relationship status, partners, romantic interest, adult sexual interest, attraction, jealousy/rivalry, boundaries, consent/availability, disposition, trust, obligations, and related state are defined in `../GAME_MASTER_RULES.md`.

Campaign 1's template below keeps explicit target-specific fields for DevilMedlar and Senpai where useful. NPCs below 18 follow the repository-wide adult-content rules in `../../GAME_MASTER_RULES.md`.

## Current Party NPCs

None established.

## Important NPC Index

None established.

When NPCs become persistent, list them here with their stable NPC ID, current name, and a short role or relevance note. Do not use a name-derived Markdown anchor as the NPC's identity.

Example format only:

```text
- **NPC-0001 — NPC Name** — role / relevance
```

## NPC Record Template

Use the sections below when an NPC becomes important enough to track persistently. Not every NPC needs every optional section. Populate what is relevant and established rather than inventing filler.

Replace the placeholder NPC ID with the next unused stable ID when the persistent record is first created.

---

## NPC Name

### Identity

- **NPC ID:** NPC-0001
- **Name:**
- **Age:**
- **Gender / pronouns:**
- **Species / ancestry:**
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

When `In party: Yes`, do not duplicate moment-to-moment movement here. The last completed party location belongs in `active_game.json`; unfinished Campaign Turn movement and combat position belong in `turn_save.md` until Campaign Turn reconciliation.

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

`Level` and `Class / archetype` are mutable mechanical state and are tracked here rather than duplicated in Identity.

- **Level:**
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

This section owns the persistent business-level vendor state, current shop stock, and services for this NPC's business. Shared official-item sourcing, pricing, transaction, acquisition, and Campaign Turn rules are defined in `../GAME_MASTER_RULES.md`. Recurring Base Prices for routine/basic repeat goods are owned by `routine_item_prices.md`.

Shop stock is **business inventory**, not the NPC's personal ownership list and not current-party inventory.

#### Business-Level State

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
- **Reason for discount / markup:** Business / relationship cause such as shop policy, relationship, reputation, faction standing, or negotiation

#### Current Shop Stock

For normal standard vendor stock, the **item name itself is the direct official link** to the freely viewable official item page.

| Item | Base Price | Qty | Category | Key Mechanics | Short Description |
|---|---:|---:|---|---|---|
|  |  |  |  |  |  |

For this table:

- current availability and quantity are vendor-owned state here
- routine/basic Base Price mirrors `routine_item_prices.md` when that item is classified there
- non-routine official items may use the shared GM-established Base Price procedure
- `Category` and `Key Mechanics` are compact storefront fields derived from the current official reference
- `Short Description` is compact generated storefront text rather than an independent mechanical authority

Full official-stock, pricing-factor, no-double-counting, external-reference, homebrew/custom-item boundary, and purchase-staging rules remain in `../GAME_MASTER_RULES.md`.

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

- **Session / Campaign Turn:** Event or continuity change

## Shared Rule Authority

NPC party joins/leaves, possession reconciliation, cross-file ownership, stable cross-file references, NPC advancement, relationship-state semantics, shop/vendor behavior, fresh-start isolation, append-first preservation, and Campaign Turn staging are governed by `../GAME_MASTER_RULES.md`.

This file contains only Campaign 1's persistent NPC master state and the Campaign 1 NPC record schema.
