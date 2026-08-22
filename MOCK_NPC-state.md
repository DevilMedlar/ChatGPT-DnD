# MOCK NPC State

> **MOCK ONLY — NOT CAMPAIGN CANON**
>
> This root-level file shows the proposed full shape of a campaign `NPC-state.md`. All people, places, items, stats, prices, relationships, quests, and events below are examples only.

# NPC State — Mock Campaign

This file is the authoritative master record for persistent NPCs.

It owns NPC identity, appearance, mechanical state, personality, relationships, knowledge, secrets, party membership, off-party location, personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC continuity.

`MOCK_world_state.md` references NPCs where they matter to the world.

`MOCK_inventory.md` expands the possessions of NPCs currently traveling with the party.

`MOCK_turn_save.md` temporarily overlays HP, position, resources, conditions, and other in-turn changes until end-turn reconciliation.

## Current Party NPCs

- **Mara Stonehand** — Temporary companion; see `#Mara-Stonehand`

## Important NPC Index

- **Mara Stonehand** — Blacksmith / temporary party companion
- **Captain Veyra** — Greyford Watch Captain / quest contact
- **Merchant Loran** — Missing caravan master
- **Eldrin** — Hunter / guide

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
- **In party:** Yes

### Appearance

- **Height:** 5'10"
- **Build:** Broad-shouldered and muscular
- **Hair:** Dark brown, tied back while working
- **Eyes:** Hazel
- **Skin:** Weathered tan skin
- **Distinctive features:** Small burn scar on left forearm
- **Typical clothing:** Leather smithing apron over work clothes
- **Visible equipment:** Longsword, smithing hammer, utility knife
- **Scars / tattoos / markings:** Burn scar on left forearm
- **Other visual notes:** Usually smells faintly of coal smoke
- **Reference art:** None established

### Location / Party State

- **Normal location:** Stonehand Smithy, Greyford
- **Current known location:** With party
- **In party:** Yes
- **Joined:** Session 5
- **Reason:** Escorting the party to Iron Mine
- **Expected duration:** Temporary
- **Last non-party location:** Stonehand Smithy, Greyford

When `In party: Yes`, live movement and battlefield position belong in `MOCK_turn_save.md` during an unfinished turn and in the campaign's completed live-state file after reconciliation.

When Mara leaves the party, replace `Current known location: With party` with the place where she can later be found.

### Personality / Motivations

- **Personality:** Direct, practical, dry sense of humor
- **Values:** Craftsmanship, honesty, keeping promises
- **Goals:** Expand the smithy and secure better ore suppliers
- **Wants:** Reliable trade routes
- **Needs:** Stable supply of quality iron
- **Fears:** Losing the smithy her family built
- **Likes:** Good steel, straightforward people
- **Dislikes:** Wastefulness, dishonest haggling
- **Habits / mannerisms:** Taps metal objects with one knuckle while thinking
- **Current priorities:** Help recover the missing ore shipment and return home safely

### Relationship State

#### DevilMedlar

- **Disposition:** Friendly
- **Trust:** Moderate
- **Respect / fear:** Respects competence
- **Attraction / romantic tension:** None established
- **Relationship status:** Ally / acquaintance
- **Debts / favors:** Owes a small favor for recovered ore
- **Promises / obligations:** Promised a discount if the caravan is recovered
- **Important boundaries:** None established
- **Important history:** First met at the smithy; later joined the party temporarily

#### Senpai

- **Disposition:** Friendly
- **Trust:** Moderate
- **Respect / fear:** Respects Senpai's decisiveness
- **Attraction / romantic tension:** None established
- **Relationship status:** Ally / acquaintance
- **Debts / favors:** None
- **Promises / obligations:** None
- **Important boundaries:** None established
- **Important history:** First met at the smithy; now traveling together temporarily

### Knowledge / Secrets

- **What Mara knows:** The missing caravan carried iron ore for her smithy
- **What Mara believes:** Bandits may be responsible
- **Information already shared:** Caravan route and expected arrival date
- **Information being withheld:** None established
- **Secrets known:** Knows the Crafts Guild has been quietly buying emergency iron
- **Secrets personally held:** None established
- **False beliefs / misunderstandings:** Bandit involvement is still only suspicion

### Mechanical State

- **Level / CR:** Level 3
- **HP / Max HP:** 25 / 25 at last completed save
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
- **Reach:** 5 ft
- **Special effects:** None

#### Features / Abilities

##### Brace

- **Description:** Mara plants her stance and absorbs an incoming blow.
- **Mechanical effect:** +2 Defense against one qualifying melee attack.
- **Activation:** Reaction
- **Uses:** 1 / 1 at last completed save
- **Recharge:** Short rest
- **Duration:** One attack
- **Requirements:** Must be able to react

#### Conditions / Ongoing Effects

- None at last completed save.

### Personal / Owned Items

This is the **master ownership list**. It remains authoritative whether Mara is in the party or not.

Because Mara is currently in the party, detailed active bookkeeping for these possessions also appears in `MOCK_inventory.md`.

#### Equipped

- Longsword x1
- Leather work armor x1
- Silver pendant x1

#### Carried

- Coin purse: 42 gp
- Shop keys x1 set
- Healing Potion x2
- Smithing tools x1 set

#### Stored / Elsewhere

- Family sword x1 — stored at Stonehand Smithy
- Travel chest x1 — stored at Stonehand Smithy
- Spare clothes

#### Important / Unique Items

- Enchanted sharpening stone x1 — stored at Stonehand Smithy

### Shop / Services

The shop belongs to Mara's NPC record because it is part of her persistent role and can be found again later.

Shop stock is **business inventory**, not Mara's personal carried inventory.

- **Business name:** Stonehand Smithy
- **Business type:** Weapons, armor, repairs
- **Owner:** Mara Stonehand
- **Location:** Greyford
- **Currency accepted:** gp
- **Typical opening hours:** Morning to early evening
- **Restock behavior:** Common goods weekly; rare goods when acquired
- **Special-order capability:** Yes
- **Buy-back policy:** Case by case
- **Base markup / discount rules:** Listed prices unless relationship or scarcity changes them
- **Current party discount:** 5% after partial ore recovery
- **Reason for discount:** Favor owed to party

#### Current Shop Stock

| Item | Price | Qty | Type | Mechanics | Description |
|---|---:|---:|---|---|---|
| Iron Longsword | 15 gp | 3 | Weapon | 1d8 slashing | Standard forged steel longsword |
| Bloodfang Longsword | 120 gp | 1 | Weapon | +2 attack; 1d8 slashing; 15% bleed trigger | Dark steel blade with hooked crimson edge |
| Ironwall Plate | 300 gp | 1 | Heavy Armor | +5 Armor; +2 Defense; -1 Dexterity | Reinforced heavy plate |
| Healing Potion | 50 gp | 2 | Consumable | Restores 2d4+2 HP | Red restorative potion |
| Ember Ring | 175 gp | 1 | Accessory | +2 fire damage; grants Fire Ward | Brass ring with glowing red crystal |
| Strange Black Dagger | 75 gp | 1 | Weapon | 1d4 piercing; +1 attack; unidentified properties | Unnaturally cold black dagger |

#### Detailed Item — Bloodfang Longsword

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
- **Save:** None in this mock
- **Immunity:** Creatures without blood or another established immunity

##### Requirements

- None

##### Charges

- None

##### Attunement

- No

##### Description

Dark steel longsword with a hooked crimson edge.

#### Detailed Item — Ironwall Plate

- **Price:** 300 gp
- **Quantity:** 1
- **Type:** Heavy Armor
- **Armor:** +5
- **Defense:** +2
- **Dexterity / Agility modifier:** -1
- **Movement penalty:** None in this mock
- **Stealth penalty:** Disadvantage if using official-rule interpretation

##### Ability — Brace

- **Activation:** Reaction
- **Effect:** Gain +2 Defense against one qualifying incoming melee attack
- **Uses:** 1 per short rest

##### Description

Massive reinforced plate built to absorb frontal attacks.

#### Detailed Item — Ember Ring

- **Price:** 175 gp
- **Quantity:** 1
- **Type:** Accessory
- **Passive effect:** +2 fire damage when a qualifying damaging attack deals fire damage

##### Ability — Fire Ward

- **Activation:** Reaction
- **Effect:** Gain fire resistance for 3 turns
- **Uses:** 1 per long rest
- **Requirements:** Ring must be worn

##### Description

Brass ring set with a crystal that remains pleasantly warm.

#### Detailed Item — Strange Black Dagger

##### Player-Known Properties

- **Price:** 75 gp
- **Quantity:** 1
- **Type:** Weapon
- **Damage:** 1d4 piercing
- **Known attack bonus:** +1
- **Unidentified properties:** Yes
- **Description:** The blade remains unnaturally cold.

##### Hidden Properties — GM / Continuity Only

**Do not reveal until identified, discovered, triggered, or otherwise legitimately learned.**

- Critical hits drain 1d4 HP from the wielder.
- The dagger reacts to undead within 30 ft.

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
- **Requirements:** Special materials may be required
- **Time required:** Depends on effect

##### Identification

- **Price:** 25 gp
- **Effect:** Reveals ordinary identifiable magical properties of one item

### Quest / Story Role

#### Associated Quests

- Missing Caravan
- Iron Road Bandits

#### Current Involvement

- **Role:** Supporting quest contact / temporary companion
- **Current objective:** Recover the missing ore caravan
- **What she asked the party to do:** Find the caravan and recover surviving cargo if possible
- **Information provided:** Route, shipment contents, caravan master's name
- **Information withheld:** None established
- **Reward promised:** 50 gp plus shop discount
- **Special conditions:** Recover usable ore if possible
- **Deadline:** None established
- **Consequences of success:** Improved shop stock and relationship
- **Consequences of failure:** Smithy shortages continue

### Continuity History

- **Session 2:** First met DevilMedlar and Senpai at Stonehand Smithy.
- **Session 3:** Explained that the ore caravan was overdue.
- **Session 4:** Party recovered part of a lost shipment; trust increased.
- **Session 5:** Mara temporarily joined the party to reach Iron Mine.

---

## Captain Veyra

### Identity

- **Name:** Captain Veyra
- **Age:** 41
- **Gender / pronouns:** Female, She/Her
- **Species / ancestry:** Human
- **Level / CR:** Level 5 equivalent
- **Role / occupation:** Captain of the Greyford Watch
- **Faction / allegiance:** Greyford Watch
- **Status:** Alive
- **In party:** No

### Appearance

- **Build:** Lean and athletic
- **Hair:** Black with grey at the temples
- **Eyes:** Dark brown
- **Typical clothing:** Watch uniform and half-plate
- **Distinctive feature:** Silver captain's badge

### Location

- **Normal location:** Greyford Watch Headquarters
- **Current known location:** Greyford Watch Headquarters
- **Can normally be found at:** Command office during daytime or city patrol routes

### Personality / Motivations

- **Personality:** Controlled, observant, difficult to impress
- **Goals:** Keep Greyford safe and reopen the North Road
- **Current priority:** Missing Caravan investigation

### Relationship State

#### DevilMedlar

- **Disposition:** Professional
- **Trust:** Low to moderate
- **Relationship status:** Hired adventurer / contact

#### Senpai

- **Disposition:** Professional
- **Trust:** Moderate
- **Relationship status:** Hired adventurer / contact

### Knowledge / Secrets

- **Knows:** Two previous caravans reported suspicious riders on the North Road
- **Believes:** Attacks may be coordinated
- **Shared:** Basic missing-caravan information
- **Withheld:** Previous reports, pending confirmation

### Personal / Owned Items

- Watch uniform
- Half-plate
- Longsword
- Captain's badge
- Office keys
- Coin purse: 18 gp

### Quest / Story Role

#### Missing Caravan

- **Role:** Primary quest giver
- **Reward promised:** 200 gp
- **Requested result:** Locate caravan, survivors, cargo, and attackers
- **Information provided:** Route and last checkpoint
- **Information withheld:** Two prior suspicious-rider reports

### Continuity History

- **Session 4:** Hired the party to investigate the missing caravan.

---

## Merchant Loran

### Identity

- **Name:** Loran Vale
- **Age:** 52
- **Gender / pronouns:** Male, He/Him
- **Species / ancestry:** Human
- **Role / occupation:** Caravan master
- **Status:** Missing
- **In party:** No

### Appearance

- **Build:** Heavyset
- **Hair:** Grey
- **Eyes:** Blue
- **Distinctive features:** Brass-rimmed spectacles

### Location

- **Normal location:** Greyford trade district
- **Current known location:** Unknown; last seen on North Road
- **Last seen:** Departing northern checkpoint with caravan

### Personal / Owned Items

- Trade ledger
- Merchant signet
- Coin purse: amount unknown
- Caravan cargo records

### Quest / Story Role

- **Associated quest:** Missing Caravan
- **Role:** Missing person / caravan master

---

## Eldrin

### Identity

- **Name:** Eldrin
- **Age:** 29
- **Gender / pronouns:** Male, He/Him
- **Species / ancestry:** Elf
- **Role / occupation:** Hunter / guide
- **Status:** Alive
- **In party:** No

### Appearance

- **Build:** Lean
- **Hair:** Auburn
- **Eyes:** Green
- **Typical equipment:** Longbow, hunting knife, travel cloak

### Location

- **Normal location:** Northern Ironwood Forest
- **Current known location:** Northern Ironwood hunting camp
- **Can normally be found at:** Camp or nearby hunting trails

### Personality / Motivations

- **Personality:** Quiet, cautious, dry humor
- **Goals:** Keep outsiders from damaging Ironwood

### Personal / Owned Items

- Longbow
- Arrows x24
- Hunting knife
- Bedroll
- Rope
- Herbal salve x2

### Quest / Story Role

- **Possible role:** Guide through Ironwood
- **Associated quest:** Missing Caravan

## Ownership Rule

- This file owns NPC identity, stats, HP at last completed save, abilities, conditions, relationships, off-party location, party membership, and master personal possessions.
- `MOCK_inventory.md` owns expanded mechanical bookkeeping for possessions of current party NPCs.
- Shop stock remains here as business inventory, separate from personal possessions.
- `MOCK_world_state.md` may reference NPCs for locations, factions, quests, and world consequences without duplicating full records.
- `MOCK_turn_save.md` overlays this file during an unfinished turn.