# Reproduction and Lineage

## Homebrew fantasy framework

Campaigns in this repository use a homebrew fantasy crossbreeding framework layered on top of the normal D&D 5.5e rules baseline.

Species, ancestry, lineage, or Creature Type difference does **not by itself** make reproduction impossible. However, crossbreeding must still have a biologically plausible reproductive pathway under the species involved. The game does not use "anything can breed with anything" as a rule.

All participating characters must satisfy the age and consent requirements in `ADULT_CONTENT_AND_CONSENT.md`.

Species-level reproductive biology and breeding-pool eligibility are owned by `REPRODUCTIVE_SPECIES_PROFILES.md`. This file governs pairing compatibility, crossbreeding behavior, gestation logic, lineage, and later hybrid mechanics using those profiles.

## Initial breeding-pool scope

For the initial global crossbreeding system, selectable breeding species are limited to species whose normal established reproduction is **sexual reproduction**.

The following are outside the initial breeding pool unless the player later establishes a broader global rule or a campaign-specific override:

- asexual-only species
- hermaphroditic species
- sequential-sex species
- reproduction that depends on shapechanging or a temporary transformed body
- magical reproduction as the species' normal reproductive method
- species that are incompatible by ordinary biology with the proposed partner

A species being intelligent, humanoid-shaped, or a particular D&D Creature Type does not by itself establish reproductive compatibility.

## Required male/female reproductive pairing

Under the initial global system, ordinary biological conception between two partners requires:

- one biologically male partner capable of supplying the fertilizing reproductive contribution required by the reproductive pathway
- one biologically female partner capable of supplying the egg or equivalent reproductive contribution required by the reproductive pathway
- reproductive anatomy and physiology that can actually participate in the applicable fertilization method
- a viable biological method for the resulting embryo, egg, or equivalent offspring stage to develop

Therefore:

- male + female may be capable of producing a biological child when the rest of the compatibility rules are satisfied
- male + male does not naturally produce a biological child together under this initial system
- female + female does not naturally produce a biological child together under this initial system

Gender identity, romance, attraction, partnership, marriage, and parenthood are separate from biological reproductive capability. The breeding check uses the actual reproductive biology relevant to conception rather than assuming that relationship status alone creates reproductive compatibility.

## Adoption is separate from reproductive compatibility

Adoption is a separate parenthood path and does **not** require biological reproductive compatibility.

A couple, family, or individual may adopt when the campaign circumstances and applicable character-agency rules allow it, regardless of whether the prospective parents:

- are the same sex
- are different species
- are reproductively incompatible
- are infertile
- are outside one another's natural crossbreeding range
- could biologically reproduce together but simply choose adoption instead

Being unable to produce a biological child together does not make characters ineligible to become parents through adoption.

Adoption does not create biological ancestry, genetic inheritance, pregnancy, gestation, or reproductive parentage. Adoptive family relationships and biological lineage remain distinct facts even when both are equally important socially and emotionally.

## Compatibility categories

Only the following reproductive-compatibility categories are eligible for the initial breeding system.

### Naturally compatible

The two species have reproductive biology sufficiently compatible that ordinary sexual reproduction can produce viable offspring without an exceptional biological workaround.

### Cross-species compatible

The two species are meaningfully different but still possess a workable sexual-reproduction pathway that can produce a viable hybrid under this setting's homebrew biology.

Cross-species compatibility may result in unusual gestation, delivery, egg development, or offspring anatomy, but there must still be a coherent biological pathway.

### Conditionally compatible

The two species can reproduce only when a specific **non-magical biological condition** required by their established reproduction is satisfied.

Examples can include:

- fertilization must occur in water or another required environment
- eggs require a particular incubation environment
- both partners must possess anatomy compatible with an unusual transfer or fertilization method
- a species-specific reproductive structure must be present and functional

The required condition must follow the established biology of the species. ChatGPT must not invent an arbitrary condition merely to force an otherwise incompatible pairing to work.

### Incompatible by ordinary biology

A pairing with no coherent ordinary biological reproductive pathway is **not eligible** for the initial breeding system.

Do not override biological incompatibility merely because the species are fantasy creatures, intelligent, consenting, romantically involved, or different Creature Types.

Biological incompatibility affects biological reproduction only. It does not block adoption or other non-biological family relationships.

## External fertilization

Sexually reproducing species that use external fertilization are allowed in the initial breeding pool.

For external fertilization to work:

- the male partner must be biologically capable of providing the fertilizing contribution required by that species' reproductive process
- the female partner must be biologically capable of providing the egg or equivalent contribution
- the required external environment and procedure must be biologically compatible with both contributors

Ordinary internal-fertilization anatomy is not automatically treated as compatible with an external-fertilization species.

## Egg implantation and host-dependent development

Egg implantation or host-dependent development is allowed **only when it is part of an established sexual reproductive pathway and the biology makes sense for the participants involved**.

If fertilization is expected to occur after implantation, the implanted host must biologically support the fertilization process. A host that merely carries an implanted egg does not automatically gain the anatomy needed to fertilize it.

Example: a human male carrying an unfertilized implanted egg cannot fertilize that egg merely because it was implanted in him if his biology does not provide the required fertilization pathway.

A pre-fertilized egg may be implanted into a biologically suitable host when the species' established reproductive process uses the host only for incubation, nourishment, protection, or hatching. The host does not need to be one of the genetic parents unless the species' biology requires it.

If a species' established host-dependent reproduction normally kills or seriously harms the host when the offspring hatches or emerges, that consequence may occur in play when the biological pathway is otherwise valid and the applicable character-agency and content rules permit the scenario.

## Gestation and delivery follow the carrying biology

When a viable sexually reproduced hybrid develops inside or is carried by one parent, the carrying parent's established reproductive biology normally determines the physical development and delivery method.

Examples:

- male human + female egg-laying dragon: if the pairing is otherwise compatible, the dragon may lay a fertilized hybrid egg, which later hatches into a human/dragon hybrid
- male dragon + female live-bearing elf: if the pairing is otherwise compatible, the elf may carry the hybrid through pregnancy and give live birth to an elf/dragon hybrid

Gestation or delivery method does **not** by itself determine how much of either ancestry the offspring ultimately expresses. Hybrid inheritance is a separate mechanic.

## Birth-safe hybrid development

A hybrid's **final inherited form does not have to be fully expressed at birth or hatching**.

The developing offspring must remain physically compatible enough with the carrying parent's gestation and delivery biology for the pregnancy, egg formation, laying, birth, implantation, or hatching pathway to make biological sense.

When a fully developed inherited feature would create an unreasonable or needlessly dangerous gestational or delivery problem, that feature may be present genetically or developmentally but remain immature, soft, folded, vestigial, internal, unformed, or otherwise not fully expressed until after birth or hatching.

Examples can include:

- horns beginning as soft or absent neonatal structures and hardening or growing later
- wings existing as small folded buds or developing during childhood rather than being full-sized at live birth
- heavy scales beginning as softer skin or light scale patches and becoming more pronounced with growth
- claws, fangs, spines, crests, plates, tails, or similar structures developing progressively when full neonatal expression would conflict with the carrying parent's delivery biology
- supernatural-looking coloration, markings, or other harmless traits appearing at birth when they create no biological conflict

This rule does **not** erase the inherited trait. It changes the trait's **developmental expression timeline** when needed to preserve a coherent gestation and delivery pathway.

The later hybrid-inheritance system should therefore distinguish at minimum between:

- the trait the offspring inherits
- whether the trait is expressed at birth or hatching
- the age or developmental stage at which a delayed trait first appears
- the age or developmental stage at which the trait becomes mechanically functional, if different

A carrying parent does not force the hybrid to permanently resemble that parent's species. The child may grow into features inherited from either ancestry over time.

## Reproductive profile requirement

Before a species is used for breeding, it must have enough reproductive biology recorded in `REPRODUCTIVE_SPECIES_PROFILES.md` to determine compatibility consistently.

That profile file owns the reusable species-level facts, including when relevant:

- sexual reproductive method
- male reproductive role
- female reproductive role
- internal or external fertilization
- live-bearing, egg-laying, implanted, host-dependent, or other non-magical development method
- carrier or host requirements
- special biological conditions required for fertilization, gestation, incubation, or hatching
- neonatal or delivery constraints that matter to safe hybrid development
- known cross-species compatibility and incompatibility information

Do not duplicate a full species reproductive profile in this file or ordinary campaign state.

Do not infer missing reproductive anatomy merely to make a pairing work. If a required fact is genuinely unknown or the species profile is Partial, establish or research that fact before resolving the pairing.

An unprofiled species is not yet cleared for breeding selection.

## Hybrid offspring

A valid compatible pairing may produce hybrid offspring that combine ancestry and biologically or mechanically appropriate traits from both parents.

Inherited traits may be expressed immediately or may develop later under the Birth-safe hybrid development rule.

Exact fertility chances, conception checks, gestation timing, multiple-offspring rules, inheritance probabilities, offspring trait selection, hybrid balance, mutations, later-generation genetics, offspring fertility, and detailed developmental milestones are defined by the later crossbreeding mechanics rather than improvised case by case.

Until those mechanics are established, do not invent permanent probabilities or inheritance formulas merely to resolve an undecided system question.

## Agency and consent

These compatibility rules establish only whether a biological reproductive pathway is possible.

They do not create automatic attraction, romance, consent, mating, conception, pregnancy, reproduction, adoption, or parenthood. Those remain dependent on adult character agency, consent, established circumstances, and choices made during play.
