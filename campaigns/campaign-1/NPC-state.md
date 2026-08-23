# NPC State — Campaign 1

This file is the authoritative master record for persistent NPCs in Campaign 1.

It owns NPC identity, appearance, mechanical state, personality, relationship and attraction state, knowledge, secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC continuity.

`world_state.md` references NPCs where they matter to locations, factions, quests, clues, discoveries, or world consequences without duplicating their full records.

`inventory.md` expands the possessions of NPCs currently traveling with the party.

`turn_save.md` temporarily overlays NPC HP, position, resources, conditions, consumed items, charges, party-membership transitions, and other in-turn changes until Campaign Turn reconciliation.

If an NPC joins or leaves during an active Campaign Turn, this file remains the last completed master state until Confirmation Gate 1 is approved and the transition is reconciled. Stage the temporary membership, location, condition, and possession effects in `turn_save.md` first.

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

For an NPC below 18, omit sexual-interest fields entirely. Age-appropriate nonsexual crush or romantic information may be recorded when relevant and must follow `../../GAME_MASTER_RULES.md`.

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

When an NPC leaves during an active Campaign Turn, stage the departure and intended off-party location in `turn_save.md`. Update this permanent section only during approved Campaign Turn reconciliation, or through the normal completed-save workflow when no Campaign Turn is active.

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

This section owns the persistent business-level vendor state, current shop stock, and services for this NPC's business. Detailed standard official item mechanics are not duplicated here. The sourcing, pricing, transaction, and acquisition rules are defined in `../GAME_MASTER_RULES.md`; recurring Base Prices for routine/basic repeat goods are owned by `routine_item_prices.md`.

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

Contextual market factors such as scarcity, shortages, unusual demand, or temporary events are separate from merchant markup/discount reasons. Record them only when they are established and relevant.

#### Current Shop Stock

For normal standard vendor stock, the **item name itself is the direct official link** to the freely viewable official item page.

| Item | Base Price | Qty | Category | Key Mechanics | Short Description |
|---|---:|---:|---|---|---|
|  |  |  |  |  |  |

For standard official shop items:

- current availability and quantity are vendor-owned state here
- the row records the Base Price being used for this stock listing
- when an item is classified as a routine/basic repeat good in `routine_item_prices.md`, this row **mirrors that file's current recurring Base Price** and must not independently redefine it
- non-routine official items may use a reasonable GM-established Base Price for that stock appearance
- `Category` and `Key Mechanics` are compact storefront fields derived from the current official reference
- `Short Description` is compact generated storefront text, not a second mechanical definition
- the freely viewable official source owns the standard published mechanics while the item remains shop stock; it does **not** own Campaign 1 vendor pricing
- do not add a separate official-reference column, duplicate official-item catalog, or locally maintained detailed official-item record

Homebrew, custom, unique, campaign-created, or mechanically modified items are outside this standard official vendor-item schema. Do not force them into this table as though they were ordinary official catalog items.

During an active Campaign Turn, purchases and other persistent shop changes remain staged in `turn_save.md`; do not immediately rewrite this permanent stock table.

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

## NPC Inventory Transfer Rule

If an NPC joins or leaves during an active Campaign Turn, stage the membership, location, and possession effects in `turn_save.md` first. The permanent steps below occur only after Confirmation Gate 1 during approved Campaign Turn reconciliation. They are not immediate mid-Turn writes.

### When an NPC joins the party

1. Mark the NPC as `In party: Yes` in this file.
2. Keep the NPC's master ownership list in this file.
3. Add an expanded active inventory section for that NPC in `inventory.md` when their carried possessions need detailed bookkeeping.
4. Reconcile any staged carried-item, resource, charge, ammunition, condition, location, or other relevant changes from `turn_save.md`.

### When an NPC leaves the party

1. Reconcile the NPC's final carried possessions and quantities from `inventory.md` and any staged Campaign Turn state into the master ownership list here.
2. Mark the NPC as no longer in the party and confirm the transfer is complete.
3. Update the NPC's off-party location when known.
4. Only then remove or collapse that NPC's expanded party-inventory section from `inventory.md`.

Do not let items disappear merely because party membership changed.

## Ownership Rule

- `NPC-state.md` owns each persistent NPC's stable NPC ID as part of NPC identity. Cross-file references use that ID rather than relying on a name-derived Markdown anchor.
- `NPC-state.md` owns NPC identity, appearance, stats, HP at the last completed save, abilities, conditions, relationship and attraction state, off-party location, party membership, master personal possessions, NPC-specific story involvement, business-level shop state, current shop stock, services, and NPC-specific continuity.
- `routine_item_prices.md` owns the routine/basic repeat-good classification and recurring Base Price used by every vendor row for those items; vendor rows here mirror that Base Price rather than redefining it.
- Relationship status, current partners, romantic interests, sexual interests, attraction, boundaries, jealousy, and consent / availability are separate facts and must not be inferred from one another.
- `inventory.md` owns expanded mechanical bookkeeping for DevilMedlar, Senpai, and possessions carried by **current party NPCs**. For NPCs, it does not replace the master ownership list here.
- Shop stock remains in the shop NPC's record here as business inventory and does not belong in `inventory.md` unless an item is actually acquired by a party member.
- `world_state.md` may reference NPCs for locations, factions, quests, clues, discoveries, and consequences without duplicating their full records.
- `world_state.md` owns overall quest and mission state; this file owns each NPC's involvement in those quests or missions.
- `session_log.md` records chronological events involving NPCs without replacing their current persistent state here.
- `turn_save.md` overlays this file, `routine_item_prices.md`, and `inventory.md` during an unfinished Campaign Turn when relevant changes are staged.

## Fresh-Start Rule

Do not recover or reconstruct NPC canon from deleted files, repository history, previous chats, memory, or another campaign unless the player explicitly requests a specific import.
