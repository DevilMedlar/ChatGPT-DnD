# Reproduction and Lineage

## Purpose and authority

This is the repository's only dedicated global reproduction file. It owns:

- biological compatibility
- fertility and conception
- carrying-parent development
- offspring count at conception
- pregnancy, egg production, gestation, and incubation
- detection of reproductive state
- birth and hatching
- biological sex and visible appearance at birth or hatching
- post-birth hybrid trait development during aging
- adult hybrid fertility and later generations
- adoption separation
- reproductive-state persistence

`PLAYABLE_CHARACTER_OPTIONS.md` owns the thirteen approved standard species and their playable/species biology. `CORE_GAME_MECHANICS.md` owns the campaign clock and ordinary 5.5e mechanics. `DICE_ROLLS_AND_REROLLS.md` owns every random result.

All adult or reproductive content remains governed by `ADULT_CONTENT_AND_CONSENT.md`.

## Active global scope

The globally approved reproductive species are exactly the thirteen standard species in `PLAYABLE_CHARACTER_OPTIONS.md`:

1. Human
2. Elf
3. Dwarf
4. Gnome
5. Dragonborn
6. Dragonkin
7. True Dragon
8. Kitsune
9. Neko
10. Usagi
11. Inu
12. Ookami
13. Lizardfolk

An omitted species or nonstandard form is not restored by an official builder, sourcebook, deleted file, repository history, prior chat, or remembered context.

A new or nonstandard species requires:

1. the player's explicit global approval and a complete entry in `PLAYABLE_CHARACTER_OPTIONS.md`, or
2. an explicit campaign-specific override that defines its required biology.

## Global biological gate

Every active species has:

- stable biological males
- stable biological females
- physical male/female mating
- a male fertilizing contribution
- a female ovum-equivalent contribution
- internal biological fertilization
- viable live-bearing or egg-laying development

The global roster excludes reproduction based on asexual replication, fission, budding, spores, broadcast spawning, temporary reproductive sexes, hermaphroditic dual-role systems, construction, summoning, magical creation, or a temporary assumed body required for reproduction.

## Required biological pairing

Natural biological conception requires:

- one reproductively mature biological male
- one reproductively mature biological female
- functional reproductive anatomy
- physical mating that provides internal fertilization
- no active biological or preventative block
- a viable development route through the female partner

Male + male and female + female do not naturally create a biological child together under this system. Romance, marriage, gender identity, and family role remain separate from reproductive anatomy.

## Adoption is separate

Adoption does not require biological compatibility, fertility, different-sex parents, or any biological relationship.

Adoption creates real family and guardianship, but it does not change biological ancestry, conception, pregnancy, egg production, inherited traits, or genetic parentage.

# Compatibility

## Naturally compatible

The same approved standard species is `Naturally compatible`.

## Cross-species compatible

Every two different active-roster species are `Cross-species compatible` in both reproductive directions.

This is a deliberate homebrew rule. No active-roster pair has a genetic species barrier.

## Conditionally compatible

`Conditionally compatible` is reserved for:

- a future approved species whose biology requires a real condition
- an explicit campaign override
- a temporary injury, condition, or physical circumstance that prevents an otherwise compatible act

It is not the default for any current species pairing.

## Incompatible by ordinary biology

Use this only when an explicit current fact removes the required mating, fertilization, or development pathway.

Consent, attraction, intelligence, power, or narrative convenience cannot replace missing biology.

## Size and physical access

All active-roster species have mutually workable reproductive anatomy under this homebrew.

- Human, Elf, Dwarf, Gnome, Dragonborn, Dragonkin, Kemonomimi, and Lizardfolk size differences do not require a compatibility penalty.
- Every reproductively mature True Dragon can safely reduce to a compatible true-dragon size or assume functional Humanoid anatomy for mating.
- True Dragon form accommodation needs no roll, item, outside spell, or partner-provided transformation.
- The dragon remains biologically a True Dragon.

Adult size therefore never lowers an active-roster pairing from Cross-species compatible.

## Directional development

Always distinguish:

- male Species A + female Species B
- male Species B + female Species A

The female partner determines the development route.

### Live-bearing female

A live-bearing female carries the developing offspring internally and gives live birth.

### Egg-laying female

An egg-laying female produces and lays a fertilized egg or clutch, after which development continues through incubation and hatching.

The other parent's route never replaces the female's route.

## Female development table

| Female species | Development route |
|---|---|
| Human | Live birth |
| Elf | Live birth |
| Dwarf | Live birth |
| Gnome | Live birth |
| Kitsune | Live birth |
| Neko | Live birth |
| Usagi | Live birth |
| Inu | Live birth |
| Ookami | Live birth |
| Dragonborn | Egg production, laying, and incubation |
| Dragonkin | Egg production, laying, and incubation |
| True Dragon | Egg production, laying, and incubation |
| Lizardfolk | Egg production, laying, and incubation |

## Carrying-parent size and birth safety

Prenatal or pre-laying development remains within the female parent's viable reproductive range rather than matching the offspring's eventual adult size.

Inherited horns, scales, plates, wings, claws, fangs, tails, breath structures, or unusual adult size may remain small, soft, folded, flexible, dormant, or otherwise immature until after birth or hatching.

Delayed expression changes timing, not ancestry.

# Fertility and conception

## Default fertility

A healthy reproductively mature adult defaults to:

- **Fertility Status:** `Fertile`
- **Fertility Modifier:** `+0`

Do not invent hidden infertility, ancestry penalties, age penalties, timing modifiers, disease, or pregnancy.

An explicit condition, injury, disease, item, treatment, curse, blessing, feature, or campaign rule may change the default.

## Fertility statuses

| Status | Modifier | Effect |
|---|---:|---|
| High Fertility | +5 | Conception remains possible with an increased target |
| Fertile | +0 | Normal default |
| Reduced Fertility | -5 | Conception remains possible with a reduced target |
| Very Low Fertility | -10 | Conception remains possible but is unlikely |
| Infertile | No roll | Natural conception cannot occur while this status applies |
| Temporarily Suppressed | No roll | Natural conception cannot occur until suppression ends |
| Unknown | No roll yet | Establish the fact before resolving conception |

Male and female modifiers stack additively.

## Conception opportunity

A conception check occurs only when:

1. the pairing is currently compatible
2. both participants are reproductively mature adults
3. neither participant has a no-roll fertility status
4. the female is not already pregnant, producing a fertilized egg or clutch, or in another blocking state
5. physical mating provides a valid internal-fertilization opportunity
6. no fully effective prevention method or explicit block applies
7. the canonical campaign clock is established
8. the same pair has not already received a conception check during the preceding 24 in-world hours

If any condition fails, do not roll.

## One check per pair per 24 hours

Each distinct male/female pairing receives at most one conception check during any 24 in-world hours.

Multiple qualifying acts in that period are folded into one opportunity. They do not add rolls or modifiers unless an explicit effect says so.

After every conception check, successful or unsuccessful, record for that exact pair:

- the other participant
- the check clock
- the outcome
- the next clock at which that pair may receive another conception check

The next eligible clock is exactly 24 in-world hours after the recorded check.

A failed check therefore remains current state until the pair becomes eligible again. Do not erase it merely because the Campaign Turn is saved or `turn_save.md` is reset.

Store the current cooldown with both participants' reproductive state in `character_sheet.md` or `NPC-state.md`. Once the next eligible clock has passed, the expired entry may be removed or replaced by a later check for the same pair.

Use the canonical `active_game.json.campaign_clock` plus the current `turn_save.md` clock overlay. Do not guess whether 24 hours passed.

## Base conception targets

| Compatibility | Base target |
|---|---:|
| Naturally compatible | 20 |
| Cross-species compatible | 15 |
| Conditionally compatible with every condition satisfied | 10 |
| Incompatible | No roll |

## Conception formula

`Final Conception Target = Base Target + Male Fertility Modifier + Female Fertility Modifier + Explicit Effect Modifiers`

- Modifiers stack additively.
- Every modifier must have an explicit source.
- Clamp an otherwise possible target to 1–95.
- A truly guaranteed effect can override the clamp.
- ChatGPT may not invent a modifier to steer the story.

## Percentile roll with one d10

Use the player's d10 twice:

1. first roll = tens digit
2. second roll = ones digit
3. a `0`, or `10` on a die numbered 1–10, is digit zero
4. combine the digits
5. `00` = `100`

Examples:

- `4`, then `7` = `47`
- `0`, then `8` = `08`
- `0`, then `0` = `100`

Do not add or multiply the dice.

## Resolution

- Result equal to or below the Final Conception Target: conception succeeds.
- Result above the target: no conception.
- There are no critical effects on 1 or 100.
- Failure causes no automatic injury, infertility, or relationship consequence.
- ChatGPT never rolls, substitutes, changes, or secretly rerolls either die.

## Successful conception

Success immediately establishes:

- a live-bearing female is pregnant, or an egg-laying female is producing a fertilized egg or clutch
- the male and female participants are the biological parents
- the offspring or fertilized-egg count under the female species' table below
- the conception clock
- the due date or laying date
- the hatching date when applicable
- the 24-hour pair cooldown record, even though further checks are already blocked by the pregnancy or egg-production state

Success does **not** establish at conception:

- each offspring's biological sex
- each offspring's exact visible appearance
- each offspring's final mechanical inherited traits
- the exact dependencies, settings, or later functionality of hybrid traits
- an individual child NPC record

Those individual details are resolved later under Birth, Hatching, and Aging.

No second hidden implantation or establishment roll occurs.

## Multiple possible fathers

Resolve qualifying opportunities in chronological order.

- The first successful conception establishes the biological father.
- Stop later checks after conception succeeds.
- If chronology is genuinely unknown, the player rolls an impartial ordering before conception checks.
- The default permits one male and one female genetic contributor.
- Multi-sire reproduction requires an explicit override.

## Contraception and prevention

A fully effective established method blocks the opportunity.

For a method with an established failure chance:

1. the player rolls the method's failure check
2. only on failure does the conception check occur

Do not invent effectiveness percentages.

# Offspring or fertilized-egg count at conception

Resolve only the number immediately after successful conception.

## Live-bearing count

For Human, Elf, Dwarf, Gnome, Kitsune, Neko, Usagi, Inu, or Ookami females, roll `1d20`:

| d20 | Offspring |
|---:|---:|
| 1–17 | 1 |
| 18–19 | 2 |
| 20 | 3 |

## Dragonborn or Dragonkin clutch

Roll `1d4`:

| d4 | Fertilized eggs |
|---:|---:|
| 1–2 | 1 |
| 3 | 2 |
| 4 | 3 |

## True Dragon clutch

Roll `1d4`:

| d4 | Fertilized eggs |
|---:|---:|
| 1–2 | 1 |
| 3 | 2 |
| 4 | 3 |

## Lizardfolk clutch

Roll `1d4`. The result is the number of fertilized eggs: 1–4.

The female species controls the count table. The male species does not change it unless an explicit effect says otherwise.

Every established offspring is viable by default. Do not add a hidden viability roll.

# Pregnancy, egg production, and incubation

## Fixed schedule rule

Development schedules are fixed, not secretly randomized.

Calculate each date from the exact conception clock. A campaign override or explicit effect may change a schedule, but ChatGPT does not add unexplained early or late variation.

## Live-bearing schedules

| Female species | Gestation |
|---|---:|
| Human | 40 weeks / 280 days |
| Elf | 48 weeks / 336 days |
| Dwarf | 44 weeks / 308 days |
| Gnome | 36 weeks / 252 days |
| Kitsune | 40 weeks / 280 days |
| Neko | 40 weeks / 280 days |
| Usagi | 40 weeks / 280 days |
| Inu | 40 weeks / 280 days |
| Ookami | 40 weeks / 280 days |

## Egg-laying schedules

| Female species | Conception to laying | Incubation after laying | Total conception to hatching |
|---|---:|---:|---:|
| Dragonborn | 8 weeks / 56 days | 16 weeks / 112 days | 24 weeks / 168 days |
| Dragonkin | 10 weeks / 70 days | 20 weeks / 140 days | 30 weeks / 210 days |
| True Dragon | 12 weeks / 84 days | 40 weeks / 280 days | 52 weeks / 364 days |
| Lizardfolk | 6 weeks / 42 days | 12 weeks / 84 days | 18 weeks / 126 days |

The conception time of day carries through to the calculated due, laying, and hatching times unless an explicit event changes it.

Multiple offspring share the same scheduled date by default. Delivery or hatching may take several in-world minutes or hours, recorded through the campaign clock.

## Healthy-state default

A healthy pregnancy or egg-development state does not automatically impose a game condition, ability penalty, Speed penalty, Exhaustion, or combat disadvantage.

Mechanical effects arise only from:

- an explicit rule
- an established injury, illness, deprivation, or environmental risk
- a spell, item, treatment, curse, blessing, or feature
- a player-approved campaign rule

## Incubation baseline

A laid egg requires:

- protection from breaking or violent impact
- a stable environment appropriate to the female species
- ordinary access to required warmth, moisture, air, and care
- no prolonged extreme condition that its biology cannot tolerate

Normal competent care succeeds automatically. Risk checks occur only when a real adverse condition is established.

# Detection and shared core-PC knowledge

The actual biological state exists from conception. Detection establishes when the characters know it.

The two core PCs share everything they learn under `CORE_PARTY_AND_CHARACTER_AGENCY.md`. If either core PC detects or learns the reproductive state, both core PCs know it.

## Live-bearing mundane detection

| Time since conception | Mundane detection |
|---|---|
| Days 0–13 | No ordinary check can confirm |
| Days 14–27 | DC 15 Wisdom (Medicine) |
| Day 28 onward | DC 10 Wisdom (Medicine) |
| Day 42 onward | The pregnant character normally recognizes the state automatically unless an explicit effect masks it |

## Egg-producing mundane detection

Use the female species' conception-to-laying interval.

| Progress toward laying | Mundane detection |
|---|---|
| First quarter | No ordinary check can confirm |
| After first quarter | DC 15 Wisdom (Medicine) |
| Halfway onward | DC 10 Wisdom (Medicine) |
| Three-quarters onward | The egg-producing character normally recognizes the state automatically unless an explicit effect masks it |

## One mundane detection attempt per 24 hours

After a mundane detection check fails, the same reproductive state cannot receive another mundane detection check until exactly 24 in-world hours later.

This applies regardless of who would make the next check. A different examiner does not create another immediate attempt.

Record with the female's reproductive state:

- last mundane detection check clock
- outcome
- next eligible detection clock

Do not erase that current cooldown merely because the Campaign Turn is saved or `turn_save.md` is reset. Once the next eligible clock has passed, the expired entry may be removed or replaced.

## Magical, item, and treatment detection

A spell, item, examination, or treatment detects only what its established mechanics say it detects. Do not invent detection powers or certainty.

A specific established magical, item, or treatment effect may bypass the mundane-attempt cooldown only when its own mechanics explicitly permit that result.

The player physically rolls all required checks, even when the characters do not know the purpose of the roll.

# Birth, hatching, and individual child records

## Healthy default

When the due, laying, or hatching clock is reached and normal care conditions are satisfied:

- labor, laying, or hatching succeeds without a random complication roll
- the parent and offspring are stable
- no automatic damage, Exhaustion, permanent injury, or death occurs

Laying creates persistent egg state and schedules but does not yet resolve the hatchling's biological sex, visible appearance, or individual child record. Those are resolved at hatching.

## Biological sex at birth or hatching

For each child at live birth or each hatchling when the egg hatches, roll `1d20`:

- odd result = male
- even result = female

A campaign-specific rule may replace this table, but ChatGPT never selects the result for narrative convenience.

## Visible appearance at birth or hatching

Resolve the newborn or hatchling's visible appearance only when that individual is born or hatches.

For each meaningful visible category, roll `1d6`:

- 1–2 = female-parent expression
- 3–4 = blended expression
- 5–6 = male-parent expression

Possible categories include:

- general newborn body framework
- skin, scales, or other covering
- ears
- tail
- eyes and markings
- horns, crest, or facial structure
- visible wings
- hands, feet, claws, or teeth
- coloration

Do not roll a category when neither parent has a meaningful difference.

Features that would make birth unsafe may be absent, soft, small, folded, dormant, or only faintly visible. Their later development is handled during aging.

## Mechanical hybrid traits are deferred

Do not determine a hybrid's final mechanical species-trait package at conception.

At birth or hatching, record ancestry, visible features, and potential delayed features. Exact mechanical inherited traits, their dependencies, damage types, skill choices, spellcasting settings, movement effects, Creature Type interactions, and other mechanical details remain **TBD after birth during aging**.

When a feature reaches a relevant developmental milestone:

1. identify the parent traits that could reasonably produce it
2. use only a player-approved rule that exists at that time
3. state every required roll before the player rolls
4. record the resolved trait and its exact dependencies in the child's persistent record
5. do not grant every mechanic from both parents
6. do not let ChatGPT choose a result merely because it fits the narrative

Until the applicable post-birth aging rule is approved, ChatGPT may describe only established visible development and may not invent a new mechanical benefit.

## Risk checks

A check occurs only when a documented risk exists.

Before the player rolls, ChatGPT must state:

- the exact risk
- the actor making the check
- the ability or skill
- the DC
- the possible success and failure outcomes

Default risk DCs:

| Risk | DC |
|---|---:|
| Minor | 10 |
| Serious | 15 |
| Severe | 20 |

Use an appropriate Constitution saving throw, Wisdom (Medicine) check, or another explicitly justified check.

Do not invent catastrophic stakes after seeing the roll.

## Newborn or hatchling record

At birth or hatching, create one persistent NPC record for each individual containing:

- stable NPC ID
- name or temporary identifier
- birth or hatching clock
- biological sex
- biological mother and father with their stable references
- adoptive parents or guardians, separately
- ancestry
- development route used before birth or hatching
- visible traits
- delayed or potential traits
- unresolved post-birth mechanical-trait status
- health and current location
- future developmental milestones as they become established
- adult fertility and female route when later established

No individual child NPC record is required before live birth or hatching. Before then, the parent record owns the aggregate pregnancy or clutch count and schedule.

# Childhood and trait development

## Universal stages

| Stage | Age |
|---|---|
| Newborn / newly hatched | Birth to 1 month |
| Infant | 1–12 months |
| Early childhood | 1–5 years |
| Childhood | 6–11 years |
| Adolescence | 12–17 years |
| Physical adulthood | 18+ |

Long-lived species may have different cultural expectations, but all active species can be physically mature by 18 under this homebrew.

## Default visible-development milestones

These are descriptive timing guides. They do not automatically grant an undefined mechanical trait.

| Trait | Visible / begins | Mechanical resolution |
|---|---|---|
| Ears, tail, harmless markings | Birth or hatching | Resolve only if a mechanic later matters |
| Darkvision or keen senses | Infancy | TBD through approved aging mechanics |
| Scales, natural armor, claws, fangs | Soft or small at birth | TBD through approved aging mechanics |
| Horns, crests, plates | Buds or soft structures at birth | TBD through approved aging mechanics |
| Gliding wings | Folded buds or small wings | TBD through approved aging mechanics |
| Breath structure | Develops in childhood | TBD through approved aging mechanics |
| Form accommodation | Signs may appear in childhood | TBD through approved aging mechanics |
| Full flight | Wings mature through adolescence | TBD through approved aging mechanics |
| Full adult size and species maturity | Progressive | Resolve by physical adulthood |

For a future PC, both the age milestone and any character-level gate eventually established for the trait must be satisfied.

# Adult hybrid fertility and later generations

## Fertile hybrid default

Every viable hybrid produced by two active-roster species defaults at reproductive maturity to:

- **Fertility Status:** `Fertile`
- **Fertility Modifier:** `+0`
- compatibility with every active-roster species
- compatibility with other viable active-roster hybrids

This is an explicit homebrew rule. Do not add hidden hybrid sterility.

An explicit injury, condition, item, treatment, curse, blessing, feature, or campaign rule may alter an individual's fertility.

## Female hybrid development route

When a female hybrid reaches reproductive maturity:

- if both parent species use the same route, she uses that route
- if the routes differ, roll `1d20`
  - 1–10 = her biological mother's species route and schedule
  - 11–20 = her biological father's species' female route and schedule

Record the selected source species and schedule. This roll is made once and becomes permanent personal biology.

## Later-generation inheritance

When a hybrid becomes a biological parent:

- use the hybrid's recorded ancestry, visible body plan, and resolved post-birth mechanical traits
- use the hybrid female's recorded development route and source-species schedule when she is the female parent
- apply the same conception, count, birth or hatching, and aging procedures
- do not invent missing mechanical inheritance rules

## Stable lineage status

A hybrid or later-generation family does not automatically become a globally selectable PC species.

The player may approve a stable lineage after defining:

- a lineage name
- standard body plan
- standard Creature Type, Size, Speed, and lifespan
- a balanced playable species package
- male and female reproductive roles
- female development route and schedule
- fertility and compatibility
- which traits reliably breed true

Add the approved lineage to `PLAYABLE_CHARACTER_OPTIONS.md` globally or to a campaign-local rule file.

# Persistence

## Temporary Turn ownership

During an active Campaign Turn, `turn_save.md` owns:

- conception opportunities and percentile rolls
- exact clock and 24-hour next-eligible clock for each pair
- offspring or fertilized-egg count rolls
- detection checks and their 24-hour next-eligible clock
- temporary pregnancy or egg-production state
- due, laying, and hatching calculations
- laying, birth, hatching, or complication checks
- biological-sex and visible-appearance rolls at birth or hatching
- post-birth developmental rolls when an approved aging mechanic later exists
- pending permanent transfers

## Permanent ownership

At approved reconciliation:

- each participant's current conception-check cooldown belongs in that participant's reproductive state in `character_sheet.md` or `NPC-state.md`
- the female's current mundane-detection cooldown belongs in her reproductive state
- aggregate pregnancy or clutch count, parents, conception clock, route, due date, laying date, and hatching date belong in the female parent's state
- no individual child record is created before live birth or hatching
- at birth or hatching, each individual child's persistent record belongs in `NPC-state.md`
- exact current completed time belongs in `active_game.json.campaign_clock`
- due dates, laying dates, hatching dates, and established developmental milestones belong in `world_state.md`
- continuity-important conceptions, births, hatchings, and lineage changes belong in `session_log.md`

An unsuccessful conception check normally needs no historical session-log entry, but its 24-hour current cooldown must remain in the participants' state until it expires.

Do not store graphic scene detail merely to prove a mechanical event occurred.

# Dice ownership

ChatGPT states the exact roll and resolves only the player's supplied dice.

ChatGPT never generates, chooses, substitutes, alters, or secretly rerolls a conception, offspring-count, sex, appearance, detection, complication, or developmental result.
