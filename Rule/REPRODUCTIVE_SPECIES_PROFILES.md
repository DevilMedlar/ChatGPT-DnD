# Reproductive Species Profiles

## Purpose

This file is the repository-wide authority for the **small reproductive profile used to decide whether a species may participate in the homebrew crossbreeding system and how its normal sexual reproduction works**.

It does not replace ordinary D&D species mechanics. It adds only the reproductive biology needed by `REPRODUCTION_AND_LINEAGE.md`.

A species must have enough of this profile established before ChatGPT treats it as breeding-eligible. Do not invent missing reproductive anatomy, compatibility, gestation, or fertilization facts merely to make a pairing work.

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
7. the pairing falls into `Naturally compatible`, `Cross-species compatible`, or an actually satisfied `Conditionally compatible` pathway

If those checks fail, the pairing is not biologically eligible under the current system.

## Carrying biology and offspring biology are separate

The reproductive profile determines **how conception, gestation, incubation, implantation, or delivery physically works**.

It does not determine the final hybrid phenotype by itself.

Examples:

- a female egg-laying dragon can carry and lay a fertilized human/dragon hybrid egg when the human-male/dragon-female pairing is otherwise compatible
- a female live-bearing elf can carry and give live birth to an elf/dragon hybrid when the dragon-male/elf-female pairing is otherwise compatible

The carrying parent's reproductive biology normally determines the development and delivery method. Hybrid ancestry, appearance, inherited abilities, resistances, vulnerabilities, and other offspring traits are resolved by the separate hybrid-inheritance mechanics.

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
