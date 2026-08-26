# Reproductive Species Profiles

## Purpose

This file is the repository-wide authority for the **small reproductive profile used to decide whether a species may participate in the homebrew crossbreeding system and how its normal sexual reproduction works**.

It does not replace ordinary D&D species mechanics. It adds only the reproductive biology needed by `REPRODUCTION_AND_LINEAGE.md`.

A species must have enough of this profile established before ChatGPT treats it as breeding-eligible. Do not invent missing reproductive anatomy, compatibility, gestation, fertilization, or delivery facts merely to make a pairing work.

## Initial global scope

The initial breeding pool is intentionally narrow.

A species is eligible for a reproductive profile used by the breeding system only when its normal established reproduction is **sexual reproduction**.

The following remain outside the initial breeding pool unless the player later establishes a broader global rule or a campaign-specific override:

- asexual-only species
- hermaphroditic species
- sequential-sex species
- species whose normal reproduction requires shapechanging or a temporary transformed body
- species whose normal reproduction is magical rather than biological sexual reproduction
- species whose biology cannot support any eligible pairing under the compatibility rules in `REPRODUCTION_AND_LINEAGE.md`

External fertilization and host-dependent or egg-implantation reproduction are allowed when they are genuine non-magical sexual reproductive methods and the required biology is actually supported.

## Required profile fields

Each breeding-eligible species should have one compact profile containing the following fields.

### Identity

- **Species:** canonical species name
- **Creature Type:** official or established D&D Creature Type
- **Profile Status:** `Complete`, `Partial`, or `Ineligible`

### Reproductive system

- **Reproductive Mode:** must be `Sexual` for the initial breeding pool
- **Male Reproductive Role:** what biological contribution a normal fertile male of the species provides
- **Female Reproductive Role:** what biological contribution a normal fertile female of the species provides
- **Fertilization Method:** `Internal`, `External`, or another specifically established non-magical sexual method
- **Development Method:** `Live-bearing`, `Egg-laying`, `Host-dependent / implanted`, or another specifically established biological method
- **Carrier / Host:** which sex or biological host normally carries, incubates, protects, or nourishes the developing offspring, if any
- **Special Biological Requirements:** environment, anatomy, reproductive structure, incubation requirement, host requirement, or other biological condition required for successful reproduction
- **Birth / Hatching Constraints:** anatomical or developmental limits relevant to successful delivery or hatching, including traits that normally must be small, soft, folded, immature, or otherwise incompletely developed at birth or hatching

### Crossbreeding information

- **General Crossbreeding Potential:** `Naturally compatible`, `Cross-species compatible`, `Conditionally compatible`, or `Incompatible by ordinary biology`
- **Known Compatible Groups / Species:** established pairings or broad biologically meaningful compatibility groups when known
- **Known Conditional Pairings:** pairings that work only when a specific non-magical biological condition is satisfied
- **Known Incompatibilities:** important pairings or biological limitations that cannot work under ordinary biology
- **Notes:** only additional reproductive facts required for consistent rulings

## Profile-status rules

### Complete

A `Complete` profile contains enough established information to resolve ordinary breeding compatibility for that species without inventing missing biology.

### Partial

A `Partial` profile is missing one or more facts that could matter to a proposed pairing.

A Partial species may not be treated as compatible merely by assumption. If a missing fact matters to the proposed pairing, research or explicitly establish that fact before resolving compatibility.

### Ineligible

An `Ineligible` profile records that the species falls outside the current global breeding pool.

Common reasons include:

- asexual-only reproduction
- hermaphroditic biology under the current restricted scope
- sequential-sex biology under the current restricted scope
- magical-only reproduction
- shapechanger-dependent reproduction
- no coherent ordinary biological sexual pathway

An Ineligible species is not available as a normal breeding selection unless the player later changes the applicable global rule or creates a campaign-specific override.

## Compatibility is pairing-specific

A species profile does **not** mean that every member of that species can reproduce with every other profiled species.

For each proposed pairing, ChatGPT must compare both species' profiles and verify that:

1. both species are eligible under the current breeding-pool scope
2. the pairing contains one biologically male contributor and one biologically female contributor capable of the required reproductive roles
3. the fertilization methods can actually interact
4. the required reproductive anatomy is present and functional
5. the embryo, fertilized egg, or equivalent offspring stage has a biologically viable development pathway
6. any required external environment, carrier, host, implantation pathway, incubation condition, or other biological requirement is satisfied
7. the carrying parent's Birth / Hatching Constraints can be satisfied by the developing hybrid, including delayed expression of inherited traits when needed
8. the pairing falls into `Naturally compatible`, `Cross-species compatible`, or an actually satisfied `Conditionally compatible` pathway

If those checks fail, the pairing is not biologically eligible under the current system.

## Carrying biology and offspring biology are separate

The reproductive profile determines **how conception, gestation, incubation, implantation, delivery, or hatching physically works**.

It does not determine the final hybrid phenotype by itself.

Examples:

- a female egg-laying dragon can carry and lay a fertilized human/dragon hybrid egg when the human-male/dragon-female pairing is otherwise compatible
- a female live-bearing elf can carry and give live birth to an elf/dragon hybrid when the dragon-male/elf-female pairing is otherwise compatible

The carrying parent's reproductive biology normally determines the development and delivery method. Hybrid ancestry, appearance, inherited abilities, resistances, vulnerabilities, and other offspring traits are resolved by the separate hybrid-inheritance mechanics.

A hybrid trait that would conflict with viable delivery or hatching does not have to be fully expressed at birth. The trait may remain developmentally immature and emerge later under `REPRODUCTION_AND_LINEAGE.md`.

## Birth / Hatching Constraints

Use this field to record only species-level constraints that matter to successful delivery or hatching.

Examples include:

- live-born young must remain sufficiently flexible for delivery
- rigid horns, antlers, plates, spines, or similar structures normally harden after birth
- large wings or crests normally begin folded, undersized, or immature
- egg-laying young may complete more external development after laying than a comparable live-born species
- a particular shell, membrane, birth canal, brood pouch, or exit structure imposes a meaningful maximum form or size at delivery

This field does not define the final hybrid inheritance result. It provides the biological constraints that the later hybrid-development system must respect.

When a hybrid inherits a feature that cannot reasonably be fully developed during the carrying parent's pregnancy or delivery method, delayed post-birth or post-hatching development is preferred over either deleting the inherited feature or forcing a biologically incoherent delivery.

## External fertilization profiles

For an externally fertilizing species, the profile must identify:

- what the male contribution is
- what the female contribution is
- where fertilization normally occurs
- what environment is required
- whether a cross-species partner's reproductive material can remain viable in that environment
- what happens after fertilization

Do not assume that ordinary internal-fertilization anatomy can participate successfully in external fertilization.

## Host-dependent and implanted development profiles

For a host-dependent species, the profile must distinguish between:

- a host that is also a genetic/reproductive contributor
- a host used only for incubation, nourishment, protection, or hatching

If fertilization occurs after implantation, the host must biologically support whatever reproductive role is required for that fertilization.

If the egg or embryo is already fertilized before implantation, a suitable host may serve only as a developmental host without becoming a genetic parent.

Any normal biological consequence of that species' host-dependent reproduction, including serious injury or death of the host at emergence, should be recorded in the profile when relevant.

## Source and research discipline

When a species has official D&D material, use official/current D&D information for the species' ordinary game identity and mechanics, but do not pretend official D&D provides reproductive biology when it does not.

For reproductive facts:

1. use explicit official lore when it clearly establishes the relevant biology
2. otherwise use well-supported biological inference only when the species is plainly modeled on a real reproductive organism and the inference does not conflict with established fantasy lore
3. otherwise leave the field unknown until the player establishes a homebrew answer or research provides enough support

Do not silently turn an unknown field into a convenient answer.

## Species Profile Template

Use this format for each species entered into the catalog:

```text
## SPECIES NAME

- Species:
- Creature Type:
- Profile Status: Complete / Partial / Ineligible
- Reproductive Mode: Sexual
- Male Reproductive Role:
- Female Reproductive Role:
- Fertilization Method: Internal / External / Other
- Development Method: Live-bearing / Egg-laying / Host-dependent / Other
- Carrier / Host:
- Special Biological Requirements:
- Birth / Hatching Constraints:
- General Crossbreeding Potential: Naturally compatible / Cross-species compatible / Conditionally compatible / Incompatible by ordinary biology
- Known Compatible Groups / Species:
- Known Conditional Pairings:
- Known Incompatibilities:
- Notes:
```

## Species profile catalog

Add one profile section here for every species that is researched for possible inclusion in the breeding pool.

Do not treat the absence of a profile as evidence of compatibility. An unprofiled species is **not yet cleared for breeding selection**.

Profiles may be added as the species catalog is researched. A completed profile becomes reusable repository-wide reproductive reference data unless a numbered campaign explicitly overrides it in that campaign's `Rules/Campaign-N_Rules.md`.

## Official D&D catalog scope

The default catalog is built from the current D&D Beyond Species index at:

`https://www.dndbeyond.com/species`

For the global D&D baseline, include current Wizards of the Coast species entries that are not marked `Legacy`. Do not silently import third-party/partner species merely because D&D Beyond hosts them. Legacy species may be researched later when the player explicitly wants them, but they are not part of the default 5.5e breeding catalog.

Variants that are biologically the same species may point to a shared reproductive profile rather than duplicating identical biology. Legacy Half-Elf and Half-Orc are not used as default 5.5e species selections; mixed ancestry is handled by this repository's hybrid system instead.

### First-pass status legend

- `Candidate`: biology strongly suggests ordinary male/female sexual reproduction, but the full crossbreeding profile is still Partial.
- `Hold`: sexual reproduction or the required development method is not yet established strongly enough to clear the species.
- `No`: outside the initial breeding pool under the current global rules.
- `Inferred` means a biological inference from an obvious real-organism or ordinary humanoid body model, not an invented official D&D fact.

A `Candidate` is **not automatically compatible with every other Candidate**. Pairing compatibility is established later from the completed profiles.

## First-pass current official species catalog

Snapshot: 2026-08-26. This is a research queue, not a declaration that every Candidate is already crossbreeding-compatible.

| Species | Source | Creature Type | Sexual? | Breeding Selection | Development Method | Profile Status |
|---|---|---|---|---|---|---|
| Aasimar | Player's Handbook | Humanoid | Likely | Candidate | Live-bearing, inferred from mortal humanoid biology | Partial |
| Dragonborn | Player's Handbook | Humanoid | Yes, lore-supported | Candidate | Egg-laying | Partial |
| Dwarf | Player's Handbook | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Elf | Player's Handbook | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Gnome | Player's Handbook | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Goliath | Player's Handbook | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Halfling | Player's Handbook | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Human | Player's Handbook | Humanoid | Yes | Candidate | Live-bearing | Partial |
| Orc | Player's Handbook | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Tiefling | Player's Handbook | Humanoid | Likely | Candidate | Live-bearing, inferred from mortal humanoid biology | Partial |
| Dhampir | Ravenloft: The Horrors Within | Humanoid | Unknown | Hold | Unknown | Partial |
| Hexblood | Ravenloft: The Horrors Within | Fey | Not cleared; magically derived | No | Unknown | Ineligible |
| Lupin | Ravenloft: The Horrors Within | Humanoid | Likely, mammalian inference | Candidate | Live-bearing | Partial |
| Reborn | Ravenloft: The Horrors Within | Humanoid | Not a normally born species under current scope | No | Not established as sexual reproduction | Ineligible |
| Boggart | Lorwyn: First Light | Humanoid | Likely, goblinoid inference | Candidate | Live-bearing | Partial |
| Faerie | Lorwyn: First Light | Fey | Unknown | Hold | Unknown | Partial |
| Flamekin | Lorwyn: First Light | Humanoid | Unknown | Hold | Unknown | Partial |
| Kithkin | Lorwyn: First Light | Humanoid | Likely | Candidate | Live-bearing, inferred | Partial |
| Lorwyn Changeling | Lorwyn: First Light | Humanoid | Restricted by current shapechanger rule | No | Not used under initial scope | Ineligible |
| Lorwyn-Shadowmoor Elf | Lorwyn: First Light | Humanoid | Yes, inferred from Elf biology | Candidate | Live-bearing | Partial |
| Rimekin | Lorwyn: First Light | Humanoid | Unknown | Hold | Unknown | Partial |
| Changeling | Eberron: Forge of the Artificer | Fey | Restricted by current shapechanger rule | No | Not used under initial scope | Ineligible |
| Kalashtar | Eberron: Forge of the Artificer | Aberration | Likely; needs Eberron-specific confirmation | Candidate | Likely live-bearing | Partial |
| Khoravar | Eberron: Forge of the Artificer | Humanoid | Yes, lineage-supported | Candidate | Live-bearing | Partial |
| Shifter | Eberron: Forge of the Artificer | Humanoid | Likely | Candidate | Live-bearing, inferred | Partial |
| Warforged | Eberron: Forge of the Artificer | Construct | No ordinary biological reproduction | No | Constructed | Ineligible |
| Aarakocra | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, avian inference | Candidate | Egg-laying | Partial |
| Air Genasi | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Likely | Candidate | Live-bearing, inferred from humanoid lineage | Partial |
| Bugbear | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Centaur | Mordenkainen Presents: Monsters of the Multiverse | Fey | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Deep Gnome | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred from Gnome biology | Candidate | Live-bearing | Partial |
| Duergar | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred from Dwarf biology | Candidate | Live-bearing | Partial |
| Earth Genasi | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Likely | Candidate | Live-bearing, inferred from humanoid lineage | Partial |
| Eladrin | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred from Elf biology | Candidate | Live-bearing | Partial |
| Fairy | Mordenkainen Presents: Monsters of the Multiverse | Fey | Unknown | Hold | Unknown | Partial |
| Firbolg | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Fire Genasi | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Likely | Candidate | Live-bearing, inferred from humanoid lineage | Partial |
| Githyanki | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes; egg-laying lore requires confirmation | Candidate | Egg-laying, provisional | Partial |
| Githzerai | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Likely | Candidate | Needs confirmation | Partial |
| Goblin | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Harengon | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Hobgoblin | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Kenku | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, avian inference | Candidate | Egg-laying | Partial |
| Kobold | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, reptilian/draconic inference | Candidate | Egg-laying | Partial |
| Lizardfolk | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, reptilian inference | Candidate | Egg-laying | Partial |
| Minotaur | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Satyr | Mordenkainen Presents: Monsters of the Multiverse | Fey | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Sea Elf | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred from Elf biology | Candidate | Live-bearing | Partial |
| Shadar-kai | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, inferred from Elf biology | Candidate | Live-bearing | Partial |
| Tabaxi | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Tortle | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Yes, reptilian inference | Candidate | Egg-laying | Partial |
| Triton | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Likely | Candidate | Needs aquatic-humanoid confirmation | Partial |
| Water Genasi | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Likely | Candidate | Live-bearing, inferred from humanoid lineage | Partial |
| Yuan-ti | Mordenkainen Presents: Monsters of the Multiverse | Humanoid | Likely | Candidate | Needs serpentine-lineage confirmation | Partial |
| Kender | Dragonlance: Shadow of the Dragon Queen | Humanoid | Yes, inferred | Candidate | Live-bearing | Partial |
| Astral Elf | Spelljammer: Adventures in Space | Humanoid | Yes, inferred from Elf biology | Candidate | Live-bearing | Partial |
| Autognome | Spelljammer: Adventures in Space | Construct | No ordinary biological reproduction | No | Constructed | Ineligible |
| Giff | Spelljammer: Adventures in Space | Humanoid | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Hadozee | Spelljammer: Adventures in Space | Humanoid | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Plasmoid | Spelljammer: Adventures in Space | Ooze | Unknown; sexual reproduction not established | Hold | Unknown | Partial |
| Thri-kreen | Spelljammer: Adventures in Space | Monstrosity | Yes, insectoid inference | Candidate | Egg-laying | Partial |
| Owlin | Strixhaven: A Curriculum of Chaos | Humanoid | Yes, avian inference | Candidate | Egg-laying | Partial |
| Leonin | Mythic Odysseys of Theros | Humanoid | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Loxodon | Guildmasters' Guide to Ravnica | Humanoid | Yes, mammalian inference | Candidate | Live-bearing | Partial |
| Simic Hybrid | Guildmasters' Guide to Ravnica | Humanoid | Reproduction of magically altered form not established | No | Underlying base-species biology is insufficient to establish heritable hybrid biology | Ineligible |
| Vedalken | Guildmasters' Guide to Ravnica | Humanoid | Likely | Candidate | Live-bearing, inferred | Partial |
| Feral Tiefling | Sword Coast Adventurer's Guide | Humanoid | Same reproductive profile as Tiefling unless later evidence differs | Candidate | Live-bearing, inferred | Partial |
| Locathah | Locathah Rising | Humanoid | Yes, fish-like inference | Candidate | External fertilization / egg development, provisional | Partial |
| Grung | One Grung Above | Humanoid | Yes, amphibian inference | Candidate | External fertilization / egg and larval development, provisional | Partial |

## First-pass exclusions and holds

The current automatic `No` entries are deliberately conservative:

- **Warforged** and **Autognome** are Constructs rather than ordinary sexually reproducing biological species.
- **Changeling** and **Lorwyn Changeling** are excluded under the current global decision not to use shapechanger reproductive edge cases.
- **Hexblood** is excluded under the current restricted scope because the current species is magically derived rather than established here as a normal biological sexual species.
- **Reborn** is excluded because becoming Reborn is not established as an ordinary sexual reproductive lifecycle.
- **Simic Hybrid** is excluded because magical alteration creates the form and the heritability of that altered biology is not established.

`Hold` entries remain unselectable for breeding until research establishes a qualifying ordinary sexual reproductive pathway. A Hold is not a permanent declaration of incompatibility.

The next research pass should convert Candidates and Holds into full individual profiles, beginning with core Player's Handbook species and then obvious biological families such as elves, dwarves, goblinoids, avian species, reptilian species, mammalian beastfolk, aquatic species, and unusual planar lineages.