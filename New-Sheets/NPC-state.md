# NPC State

This file is the authoritative master record for persistent NPCs and persistent children in the campaign.

It owns NPC identity, appearance, mechanics, personality, relationships, revealed knowledge, party membership, location, personal possessions, reproductive and parent state, biological and adoptive family links, shops, NPC-specific quest involvement, and continuity.

- NPC rules: `../Rule/NPCS_AND_PARTY_MEMBERSHIP.md`
- Relationships: `../Rule/RELATIONSHIPS_AND_SOCIAL_INTERACTIONS.md`
- Reproduction and lineage: `../Rule/REPRODUCTION_AND_LINEAGE.md`
- Shops: `../Rule/SHOPS_PRICING_AND_TRANSACTIONS.md`
- State ownership: `../Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md`

`world_state.md` references persistent NPCs and scheduled milestones by stable ID. `inventory.md` expands the possessions of NPCs currently traveling with the party. `turn_save.md` temporarily overlays unfinished Campaign Turn changes.

## Stable NPC ID Convention

- Assign persistent NPC IDs in sequence: `NPC-0001`, `NPC-0002`, and so on.
- A newborn or hatchling receives the next unused ID at live birth or hatching.
- Do not create an individual child NPC record before live birth or hatching; before then, the female parent's record owns the aggregate pregnancy or clutch state.
- Never reuse or change an ID because a name, title, relationship, age, location, party state, or life status changes.
- Cross-file references include the stable ID. A current name may accompany it for readability.
- `NPC-####` is a template placeholder, not an actual NPC.
- Reconcile any duplicate or conflicting ID before another permanent save.

## Current Party NPCs

## Important NPC Index

Example format only:

```text
- **NPC-#### — NPC Name** — role / relevance
```

## NPC Record Template

Populate only established and relevant fields. A minor NPC does not need invented filler or a complete combat block.

Do not record an untold hidden answer merely to preserve GM secrets. Record only information revealed to or known by the core PCs, or the known fact that a question remains unanswered.

---

## NPC Name

### Identity

- **NPC ID:** NPC-####
- **Name:**
- **Age:**
- **Birth / hatching clock:**
- **Gender / pronouns:**
- **Biological reproductive role:** Male / Female / Not applicable / Unknown
- **Species / ancestry:**
- **Creature Type:**
- **Role / occupation:**
- **Faction / allegiance:**
- **Status:** Alive / Dead / Missing / Unknown
- **In party:** Yes / No

### Appearance

- **Height / Size:**
- **Build:**
- **Hair:**
- **Eyes:**
- **Skin / scales / other covering:**
- **Ears / tail / horns / wings / crest:**
- **Distinctive features:**
- **Typical clothing:**
- **Visible equipment:**
- **Scars / tattoos / markings:**
- **Other visual notes:**
- **Reference art:** See `art/art_log.md` when established

For a hybrid child, distinguish visible traits from delayed or potential traits whose mechanics remain TBD during aging.

### Location / Party State

- **Normal location:**
- **Current known location:**
- **Last seen:**
- **Can normally be found at:**
- **Joined party clock:**
- **Reason / expected duration:**
- **Last non-party location:**

When `In party: Yes`, moment-to-moment movement belongs in `turn_save.md`; the completed party location belongs in `active_game.json`.

### Personality / Motivations

- **Personality:**
- **Values:**
- **Goals known to the core PCs:**
- **Wants / needs known to the core PCs:**
- **Fears known to the core PCs:**
- **Likes / dislikes:**
- **Habits / mannerisms:**
- **Current priorities known to the core PCs:**

### Relationship / Attraction Overview

- **Relationship status:**
- **Current partner(s) / stable IDs:**
- **Romantic interest(s):**
- **Adult sexual interest(s):** Explicitly adult NPCs only
- **Attraction toward player-controlled PC:**
- **Attraction toward ChatGPT-controlled PC:**
- **Other known attractions:**
- **Jealousy / rivalry:**
- **Established boundaries:**
- **Consent / availability notes:**
- **Disposition / trust / obligations toward core PCs:**
- **Other important relationships:**

### Family, Reproductive, and Lineage State

Populate only established facts. A healthy reproductively mature adult defaults to `Fertile +0` under `REPRODUCTION_AND_LINEAGE.md`.

#### Parentage and Guardianship

- **Biological mother / stable ID:**
- **Biological father / stable ID:**
- **Adoptive parent(s) / stable IDs:**
- **Guardian(s) / stable IDs:**
- **Children / offspring / stable IDs after birth or hatching:**
- **Other family links:**

Biological and adoptive relationships remain distinct fields.

#### Current Reproductive State

- **Reproductive maturity:** Mature / Not mature / Not established
- **Fertility status / modifier:**
- **Female development route, when applicable:** Live-bearing / Egg-laying / Not established
- **Source-species schedule for a hybrid female:**
- **Prevention / contraception state:**
- **Current state:** None / Pregnant / Producing fertilized egg or clutch / Incubating or caring for egg(s) / Other
- **Biological co-parent / stable reference:**
- **Conception clock:**
- **Compatibility:**
- **Offspring / fertilized-egg count:**
- **Due date or laying date:**
- **Hatching date:**
- **Individual sex / appearance / mechanical traits:** Not resolved until birth, hatching, or later aging as applicable
- **What the core PCs know:**
- **Ongoing reproductive effects / treatment / notes:**

##### Current Conception-Check Cooldowns

Keep each exact pair's latest check until its 24-hour next-eligible clock passes.

| Other participant / stable reference | Last check clock | Outcome | Next eligible clock |
|---|---|---|---|
|  |  |  |  |

##### Current Mundane-Detection Cooldown

- **Last mundane detection check clock:**
- **Outcome:**
- **Next eligible detection clock:**

#### Hybrid and Developmental State

Use only after live birth or hatching.

- **Ancestry / biological parents:**
- **Visible traits at birth or hatching:**
- **Delayed or potential traits:**
- **Resolved mechanical traits developed during aging:**
- **Unresolved mechanical traits / dependencies:** TBD after birth during aging
- **Scheduled developmental milestones:**
- **Current Size:**
- **Expected adult size / lifespan:** Not established until later aging unless explicitly resolved
- **Adult fertility:** Not yet established / Fertile +0 / Other explicit state
- **Female development route at maturity:** Not yet established / Live-bearing / Egg-laying
- **Stable-lineage status:** Individual hybrid / Campaign-local lineage / Global approved lineage

Do not invent a mechanical hybrid benefit before an applicable player-approved aging rule resolves it.

### Revealed Information and Known Questions

Record only information that has been told to, witnessed by, or discovered by the core PCs.

- **What the NPC has told or shown the core PCs:**
- **What the core PCs know the NPC believes:**
- **Information the core PCs know was shared with someone else:**
- **Known lies, contradictions, or misunderstandings:**
- **Known unanswered questions involving this NPC:**

Do not record the untold answer to a mystery, the content of an unrevealed secret, or undiscovered information. If the core PCs know only that something is being withheld, record the unanswered question rather than the hidden answer.

### Mechanical State

Use only when mechanically relevant.

- **Level:**
- **Class / archetype:**
- **XP / advancement:**
- **HP / Max HP:**
- **Temporary HP:**
- **Armor Class / calculation:**
- **Initiative:**
- **Speed / special movement:**
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

#### Saving Throws / Skills

#### Attacks

For each attack record modifier, damage, damage type, range or reach, and special effects.

#### Features / Abilities / Spells

For each feature record its mechanics, activation, uses, recharge, duration, requirements, and stacking rules.

#### Conditions / Ongoing Effects

#### Resources

### Personal / Owned Items

This is the NPC's master ownership list whether or not the NPC is currently in the party.

#### Equipped

#### Carried

#### Stored / Elsewhere

#### Important / Unique Items

When the NPC is in the party, keep mechanically detailed active bookkeeping in `inventory.md` synchronized with this master list.

### Shop / Services

Use for persistent vendors or service providers.

#### Business-Level State

- **Business name / type:**
- **Owner / operator:**
- **Location:**
- **Currency accepted:**
- **Opening hours:**
- **Restock behavior / next scheduled restock:**
- **Special orders / buy-back policy:**
- **Base markup / discount rules:**
- **Current party modifier and reason:**

#### Current Shop Stock

| Item | Base Price | Qty | Category | Key Mechanics | Short Description |
|---|---:|---:|---|---|---|
|  |  |  |  |  |  |

#### Services

For each service record price, time, effect, requirements, and limitations.

### Quest / Story Role

- **Associated quests / missions:**
- **Current involvement known to the core PCs:**
- **Objective / request:**
- **Information provided:**
- **Known unanswered questions:**
- **Reward / conditions / deadline:**
- **Consequences:**

`world_state.md` owns overall quest state; this section owns the NPC's revealed involvement.

### Continuity History

Append compact NPC-specific changes that explain current known state.

```text
- Campaign Turn / clock: event or continuity change
```
