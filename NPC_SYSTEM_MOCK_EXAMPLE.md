# NPC System Mock / Example

> **EXAMPLE ONLY — NOT CAMPAIGN CANON**
>
> This file exists only to demonstrate the proposed NPC, shop, inventory, world-reference, quest, and turn-save structure.
>
> **Nothing in this file is part of Campaign 1 or any other campaign.** Do not import names, locations, items, prices, quests, relationships, statistics, shop stock, history, or other example information into a campaign unless the player explicitly chooses to adopt it.
>
> Example names such as Mara Stonehand, Greyford, Captain Veyra, and Bloodfang Longsword are placeholders only.

---

# 1. Example `world_state.md` NPC References

`world_state.md` should know which NPCs matter to a location, faction, quest, clue, or consequence, but should point to `NPC-state.md` for the full NPC record instead of duplicating it.

```md
## Important NPCs

### Greyford

- **Mara Stonehand**
  - Role: Blacksmith / shopkeeper
  - Location: Stonehand Smithy
  - See: `NPC-state.md#Mara-Stonehand`

- **Captain Veyra**
  - Role: City Watch Captain / quest contact
  - Location: Greyford Watch Headquarters
  - See: `NPC-state.md#Captain-Veyra`

### Ironwood Forest

- **Eldrin**
  - Role: Hunter / possible guide
  - Last known location: Northern Ironwood
  - See: `NPC-state.md#Eldrin`
```

### Example location record

```md
## Locations

### Greyford

Known information about Greyford itself.

### Stonehand Smithy

- Owner: Mara Stonehand
- Type: Blacksmith / weapon and armor shop
- District: Forge Quarter
- Known services: Weapons, armor, repairs, identification
- Relevant events: None
- See NPC: `NPC-state.md#Mara-Stonehand`
```

### Example quest record

`world_state.md` owns the overall quest state.

```md
## Active Quests / Goals

### Missing Caravan

- Status: Active
- Quest giver: Captain Veyra
- Objective: Locate the missing merchant caravan.
- Current progress: Investigation begun
- Known clues: Wagon tracks lead north
- Relevant NPCs:
  - Captain Veyra -> `NPC-state.md#Captain-Veyra`
  - Merchant Loran -> `NPC-state.md#Merchant-Loran`
- Relevant locations:
  - Greyford
  - North Road
- Reward: 200 gp
- Failure conditions: Not established
- Completion conditions: Caravan fate confirmed and report returned
```

---

# 2. Example `NPC-state.md` Master Record

`NPC-state.md` is the authoritative master database for persistent NPCs.

It may contain:

- identity
- appearance
- level / CR
- stats
- HP
- abilities
- conditions
- personality
- goals / wants / fears
- relationships
- knowledge and secrets
- party membership
- normal or current location when away from the party
- master personal-ownership list
- NPC-specific quest involvement
- shop / service information
- shop stock and prices
- NPC continuity history

Not every NPC needs every section. Populate only what is relevant.

```md
# NPC State — Example

## Current Party NPCs

- None.

## Important NPCs

- Mara Stonehand
- Captain Veyra

---

## Mara Stonehand

### Identity

- **Name:** Mara Stonehand
- **Age:** 34
- **Gender / pronouns:** Female, She/Her
- **Species / ancestry:** Human
- **Level / CR:** Level 3
- **Class / archetype:** Fighter / Smith
- **Role / occupation:** Blacksmith and shopkeeper
- **Faction / allegiance:** Greyford Crafts Guild
- **Status:** Alive
- **In party:** No

### Appearance

- **Height:** 5'10"
- **Build:** Broad-shouldered and muscular
- **Hair:** Dark brown, usually tied back
- **Eyes:** Hazel
- **Skin / scales / fur / etc.:** Weathered tan skin
- **Distinctive features:** Small burn scar on left forearm
- **Typical clothing:** Leather smithing apron over work clothes
- **Visible equipment:** Smithing hammer and utility knife
- **Scars / tattoos / markings:** Burn scar on left forearm
- **Other visual notes:** Usually smells faintly of coal smoke
- **Reference art:** None established

### Location

- **Normal location:** Stonehand Smithy, Greyford
- **Current known location:** Stonehand Smithy, Greyford
- **Last seen:** Stonehand Smithy
- **Can normally be found at:** Forge floor during business hours

If Mara joins the party:

- **In party:** Yes
- **Current location:** With party
- Live movement and combat position are tracked by `active_game.json` / `turn_save.md` rather than duplicated here.

### Personality / Motivations

- **Personality:** Direct, practical, dry sense of humor
- **Values:** Craftsmanship, honesty, keeping promises
- **Goals:** Expand the smithy and secure better ore suppliers
- **Wants:** Reliable trade routes
- **Needs:** A stable supply of quality iron
- **Fears:** Losing the smithy her family built
- **Likes:** Good steel, straightforward people
- **Dislikes:** Haggling without reason, wastefulness
- **Habits / mannerisms:** Taps metal objects with one knuckle while thinking
- **Current priorities:** Replace delayed ore shipment

### Relationship State

#### DevilMedlar

- **Disposition:** Friendly
- **Trust:** Moderate
- **Respect / fear:** Respects competence
- **Attraction / romantic tension:** None established
- **Relationship status:** Acquaintance
- **Debts / favors:** None
- **Promises / obligations:** None
- **Important boundaries:** None established
- **Important history:** First met at the smithy

#### Senpai

- **Disposition:** Friendly
- **Trust:** Moderate
- **Respect / fear:** Respects her directness
- **Attraction / romantic tension:** None established
- **Relationship status:** Acquaintance
- **Debts / favors:** None
- **Promises / obligations:** None
- **Important boundaries:** None established
- **Important history:** First met at the smithy

### Knowledge / Secrets

- **What the NPC knows:** A caravan carrying iron ore is overdue
- **What the NPC believes:** Bandits may be responsible
- **Information already shared with the party:** The caravan was expected three days ago
- **Information being withheld:** None established
- **Secrets known:** None established
- **Secrets personally held:** None established
- **False beliefs / misunderstandings:** Bandit involvement is only a suspicion

### Mechanical State

- **Level / CR:** Level 3
- **HP / Max HP:** 25 / 25
- **Temporary HP:** 0
- **Armor Class:** 15
- **Initiative:** +1
- **Speed:** 30 ft
- **Proficiency Bonus:** +2
- **Passive Perception:** 11

#### Ability Scores

- **Strength:** 16 (+3)
- **Dexterity:** 12 (+1)
- **Constitution:** 15 (+2)
- **Intelligence:** 11 (+0)
- **Wisdom:** 12 (+1)
- **Charisma:** 10 (+0)

#### Saving Throws

- Strength +5
- Constitution +4

#### Skills

- Athletics +5
- Insight +3
- Smithing-related checks +5 when applicable

#### Attacks

##### Longsword

- **Attack:** +5
- **Damage:** 1d8+3 slashing
- **Damage type:** Slashing
- **Range / reach:** 5 ft
- **Special effects:** None

#### Features / Abilities

##### Brace

- **Description:** Mara plants her stance and absorbs an incoming blow.
- **Mechanical effect:** +2 Defense against one qualifying melee attack.
- **Uses:** 1
- **Recharge:** Short rest
- **Duration:** One attack
- **Requirements:** Must be able to react

#### Conditions / Ongoing Effects

- None.

#### Resources

- **Brace uses:** 1 / 1

### Personal / Owned Items

This is the master ownership list. It remains here whether Mara is in the party or not.

#### Equipped

- Longsword
- Leather work armor
- Silver pendant

#### Carried

- Coin purse: 42 gp
- Shop keys
- Healing Potion x2
- Smithing tools

#### Stored / Elsewhere

- Family sword
- Travel chest
- Spare clothes

#### Important / Unique Items

- Enchanted sharpening stone
```

---

# 3. Example Shop / Services Record

Shop stock is **not** the same thing as the NPC's personal possessions.

```md
### Shop / Services

- **Business name:** Stonehand Smithy
- **Business type:** Weapons, armor, repairs
- **Owner:** Mara Stonehand
- **Location:** Greyford
- **Currency accepted:** gp
- **Typical opening hours:** Morning to early evening
- **Restock behavior:** Common goods weekly; rare goods when available
- **Special-order capability:** Yes
- **Buy-back policy:** Case by case
- **Base markup / discount rules:** Standard listed prices
- **Current party discount:** None
- **Reason for discount / markup:** None

#### Current Shop Stock

| Item | Price | Qty | Type | Mechanics | Description |
|---|---:|---:|---|---|---|
| Iron Longsword | 15 gp | 3 | Weapon | 1d8 slashing | Standard forged steel longsword |
| Bloodfang Longsword | 120 gp | 1 | Weapon | +2 attack; 1d8 slashing; bleed chance | Dark steel blade with a hooked crimson edge |
| Ironwall Plate | 300 gp | 1 | Heavy Armor | +5 Armor; +2 Defense; -1 Dexterity | Reinforced heavy plate |
| Healing Potion | 50 gp | 2 | Consumable | Restores 2d4+2 HP | Red restorative potion |
| Ember Ring | 175 gp | 1 | Accessory | +2 fire damage; grants Fire Ward | Brass ring with a glowing red crystal |
```

## Detailed Shop Item Example — Bloodfang Longsword

```md
#### Bloodfang Longsword

- **Price:** 120 gp
- **Quantity:** 1
- **Type:** Weapon
- **Rarity:** Uncommon
- **Damage:** 1d8 slashing
- **Attack modifier:** +2
- **Damage modifier:** None
- **Damage type:** Slashing

##### Special Effect — Bleed

- **Trigger:** Successful qualifying hit
- **Chance:** 15%
- **Effect:** Target takes 1d4 bleed damage at the start of its turn
- **Duration:** 2 turns
- **Stacking:** No
- **Save:** None in this mock example
- **Immune targets:** Creatures without blood or another established immunity

##### Requirements

- None

##### Charges

- None

##### Attunement

- No

##### Description

Dark steel longsword with a hooked crimson edge.
```

## Detailed Shop Item Example — Ironwall Plate

```md
#### Ironwall Plate

- **Price:** 300 gp
- **Quantity:** 1
- **Type:** Heavy Armor

##### Mechanics

- **Armor:** +5
- **Defense:** +2
- **Dexterity / Agility:** -1
- **Movement penalty:** None in this mock example
- **Stealth penalty:** If applicable
- **Other effects:** None

##### Ability — Brace

- **Activation:** Reaction
- **Effect:** Gain +2 Defense against one incoming qualifying melee attack.
- **Uses:** 1 per short rest

##### Description

Massive reinforced plate built to absorb frontal attacks.
```

---

# 4. Known vs Hidden Item Properties

The player-facing information should include only properties the characters actually know.

Hidden properties may be stored for continuity but must be clearly marked so they are not revealed early.

```md
#### Strange Black Dagger

- **Price:** 75 gp
- **Damage:** 1d4 piercing
- **Known bonus:** +1 attack
- **Unidentified properties:** Yes
- **Description:** The blade remains unnaturally cold.

##### Hidden Properties — GM / Continuity Only

DO NOT reveal until identified, discovered, triggered, or otherwise legitimately learned.

- Critical hits drain 1d4 HP from the wielder.
- The dagger reacts to undead within 30 ft.
```

---

# 5. Services Example

```md
#### Services

##### Weapon Repair

- **Price:** 5 gp+
- **Time:** 1 hour
- **Effect:** Repairs ordinary weapon damage
- **Limitations:** Severe or magical damage may cost more

##### Armor Repair

- **Price:** 10 gp+
- **Time:** 2 hours
- **Effect:** Repairs ordinary armor damage

##### Enchantment

- **Available:** Yes
- **Price:** Depends on enchantment
- **Requirements:** Materials may be required
- **Time required:** Depends on effect

##### Identification

- **Price:** 25 gp
- **Effect:** Reveals ordinary identifiable magical properties of one item
```

---

# 6. Quest / Mission NPC Example

`NPC-state.md` records the NPC's personal role in a quest. `world_state.md` remains authoritative for the overall quest state.

```md
### Quest / Story Role

#### Associated Quests

- Missing Caravan
- Iron Road Bandits

#### Current Involvement

- **Role:** Quest contact
- **Current objective:** Recover the missing ore caravan
- **What they asked DevilMedlar/Senpai to do:** Find the caravan and determine what happened
- **Information provided:** Route, expected arrival date, caravan master's name
- **Information withheld:** None established
- **Reward promised:** Discount plus 50 gp
- **Special conditions:** Return surviving cargo if possible
- **Deadline:** None established
- **Consequences of success:** Better supplies and improved relationship
- **Consequences of failure:** Smithy shortages continue
```

---

# 7. NPC Continuity History Example

This should be a compact NPC-specific history, not a duplicate of the entire `session_log.md`.

```md
### Continuity History

- **Session 2:** First met DevilMedlar and Senpai at the Greyford smithy.
- **Session 3:** Asked the party to investigate the missing ore caravan.
- **Session 4:** DevilMedlar recovered part of the shipment.
- **Session 4:** Mara's trust toward DevilMedlar increased.
- **Session 5:** Mara temporarily joined the party.
```

---

# 8. Example NPC Joining the Party

When an NPC joins the party, `NPC-state.md` continues to own the NPC's identity, stats, HP, conditions, relationships, party membership, and master ownership list.

```md
### Party State

- **In party:** Yes
- **Joined:** Session 5
- **Reason:** Escorting party to Iron Mine
- **Expected duration:** Temporary
- **Current location:** With party
```

Moment-to-moment location and position changes belong to `turn_save.md` during an unfinished turn.

---

# 9. Example `inventory.md` Expansion for a Current Party NPC

`inventory.md` provides detailed mechanical bookkeeping for possessions of NPCs currently traveling with the party.

```md
# Current Party NPC Inventories

Party membership itself is authoritative in `NPC-state.md`.

Only NPCs currently traveling with the party receive expanded active inventory records here.

## Mara Stonehand

See master NPC record:

`NPC-state.md#Mara-Stonehand`

### Equipped

#### Longsword

- **Quantity:** 1
- **Equipped:** Yes
- **Damage:** 1d8 slashing
- **Attack modifier:** +1
- **Condition:** Good
- **Durability:** Normal
- **Charges:** None
- **Special effects:** None

#### Leather Work Armor

- **Equipped:** Yes
- **Armor:** +2
- **Condition:** Good
- **Special effects:** None

### Consumables

#### Healing Potion

- **Quantity:** 2
- **Effect:** Restores 2d4+2 HP
- **Consumed on use:** Yes

### Currency

- **Gold:** 42 gp

### Tools / Utility

#### Smithing Tools

- **Quantity:** 1 set
- **Condition:** Good
- **Uses:** Normal smithing and repair tasks

### Important Items

- Enchanted sharpening stone
```

---

# 10. Example NPC Leaving the Party

Before removing the expanded NPC section from `inventory.md`, reconcile the NPC's final possessions back into the master ownership list in `NPC-state.md`.

Example before travel:

```text
Healing Potions: 2
Gold: 42 gp
```

Example after travel:

```text
Healing Potions: 1
Gold: 36 gp
Strange Ruby: 1
```

Then `NPC-state.md` should contain the final ownership state:

```md
### Personal / Owned Items

- Longsword
- Leather work armor
- Healing Potion x1
- Coin purse: 36 gp
- Smithing tools
- Strange Ruby x1
```

And party state becomes:

```md
### Party State

- **In party:** No
- **Current known location:** Stonehand Smithy, Greyford
```

Only after that reconciliation is confirmed should the expanded NPC inventory section be removed or collapsed from `inventory.md`.

---

# 11. Example `turn_save.md` NPC Changes

During an unfinished gameplay turn, ordinary in-turn changes should be staged in `turn_save.md` instead of immediately rewriting the permanent files.

```md
## Turn Events

### Step 2

Actor: Mara Stonehand

Action:
Bandit struck Mara.

Result:
- HP: 25 -> 20
- Change: -5 HP

### Step 4

Actor: Mara Stonehand

Action:
Used Healing Potion.

Result:
- HP: 20 -> 24
- Change: +4 HP
- Healing Potion: 2 -> 1
- Change: -1 Healing Potion

## Current In-Turn State

### Mara Stonehand

- HP: 24/25
- Healing Potion: 1
- Position: Behind western barricade

## Pending End-Turn Transfers

### `NPC-state.md`

Mara:
- HP -> 24/25

### `inventory.md`

Mara:
- Healing Potion -> 1
```

At end turn, those changes are reconciled into their permanent owner files before the completed save revision is finalized.

---

# 12. Example Ownership Hierarchy

```text
active_game.json
    Last completed live campaign state
    Session / turn / scene / current completed location
    Character levels / XP / save revision / sync state

turn_save.md
    Current unfinished turn
    Step-by-step actions
    HP changes
    movement / positions
    resource changes
    item use
    conditions
    temporary effects
    pending end-turn transfers

character_sheet.md
    DevilMedlar and Senpai
    Full player/co-protagonist character records

NPC-state.md
    All persistent NPC master records
    identity
    appearance
    mechanical stats
    HP
    abilities
    conditions
    relationships
    normal/current location when away from party
    party membership
    master personal-ownership list
    NPC-specific quest involvement
    shops
    shop stock
    services
    NPC continuity history

inventory.md
    Detailed possessions for:
    DevilMedlar
    Senpai
    current party NPCs

world_state.md
    World locations
    factions
    quests
    discoveries
    clues
    world consequences
    lightweight NPC references pointing to NPC-state.md

session_log.md
    Full chronological completed-turn campaign history

art/art_log.md
    Visual canon and reference-art continuity
```

## Core ownership rule

**Reference instead of duplicate whenever practical.**

- `world_state.md` says an NPC exists and why they matter to the world.
- `NPC-state.md` says who that NPC is and owns the NPC's master persistent state.
- `inventory.md` expands active mechanical inventory for NPCs currently traveling with the party.
- `turn_save.md` owns temporary changes during the current unfinished turn.
- `session_log.md` owns completed chronological campaign history.

---

# 13. Example-Only Rule

Everything in this root-level file is mock data used to evaluate structure.

Do **not** treat any example NPC, item, location, price, quest, stat, relationship, shop, or event above as campaign canon.

When the final NPC system is approved, campaign files should receive only the approved **structure and rules**, not this mock/example data.