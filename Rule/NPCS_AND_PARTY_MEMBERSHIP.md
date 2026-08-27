# NPCs and Party Membership

## Stable NPC identity

Within each campaign, every persistent NPC receives one stable campaign-local ID in the form `NPC-0001`, `NPC-0002`, and so on when first added to `NPC-state.md`.

- Assign the next unused numeric ID in sequence.
- A newborn or hatchling receives the next unused ID at live birth or hatching.
- Do not create an individual unborn-child or unhatched-child NPC record before live birth or hatching; the female parent's reproductive state owns the aggregate pregnancy or clutch before then.
- An NPC's canonical **Name** remains fixed once established, except when correcting a genuine transcription or data-entry mistake.
- Titles, ranks, honorifics, epithets, nicknames, aliases, disguises, roles, locations, relationships, party status, and life status are separate mutable facts and do not replace or rename the NPC's canonical Name.
- An NPC ID never changes because a title, role, location, relationship, party status, life status, or other mutable descriptive state changes.
- Never reuse an old NPC ID for a different NPC.
- Stable NPC IDs remain the cross-file identity keys even though canonical Names are fixed. This avoids ambiguity when different NPCs share the same or similar Names and keeps references reliable across files.
- Names and Markdown headings are human-readable display text, not identity keys.
- Cross-file references to a persistent NPC must use the stable NPC ID; the canonical NPC Name may accompany it for readability.
- If one NPC is found with multiple IDs, or two NPCs share one ID, stop and reconcile the identity conflict before completing another persistent save.

When useful, mutable titles, ranks, epithets, honorifics, aliases, or similar descriptors should be recorded separately in `NPC-state.md` rather than modifying the NPC's Name. They may later be added, changed, or removed as campaign state changes.

## NPC state ownership

`NPC-state.md` is authoritative for persistent NPC:

- stable ID and identity
- textual appearance canon
- statistics, abilities, conditions, and mechanical state
- personality, values, goals, fears, habits, and priorities that have been established or revealed
- relationships and attractions
- information told to, witnessed by, or discovered by the core PCs
- known NPC beliefs, lies, contradictions, misunderstandings, and unanswered questions
- party membership and off-party location
- master personal possessions
- reproductive cooldowns, parentage, pregnancy or egg state, and post-birth child development
- NPC-specific quest or mission involvement known to the core PCs
- shops, services, business state, and shop stock
- compact NPC-specific continuity history

Important NPCs should track only fields that are relevant and established. Do not invent filler merely because a template contains a field.

Do not store an untold hidden answer, unrevealed secret, undiscovered motive, or unknown solution merely for future GM use. If the core PCs know only that a question exists, record the question rather than its answer in the appropriate NPC or world record.

The required ChatGPT-controlled core PC is a PC, not an NPC, and is governed by `CORE_PARTY_AND_CHARACTER_AGENCY.md` and `ADVANCEMENT_AND_XP.md`.

## NPC advancement

NPC advancement is not universal.

- Minor or background NPCs remain at their established mechanical state unless something in the fiction changes them.
- Important persistent NPCs may gain or lose Level, abilities, spells, features, equipment, resources, class/archetype, resistances, weaknesses, transformations, or other mechanical traits when justified by training, experience, story events, consequences, or another established cause.
- Long-term party NPCs should advance often enough to remain mechanically relevant, but they do **not** automatically use the core PCs' XP system unless that has been explicitly established for the NPC.
- NPC advancement may be level-based, ability-based, feature-based, or another established form appropriate to that NPC.
- Existing NPCs do **not** automatically scale merely because the core PCs became stronger.
- Any NPC advancement caused during an active Campaign Turn is staged in `turn_save.md` and transferred to `NPC-state.md` only through the confirmed Campaign Turn save process.

## Party membership and possessions

`NPC-state.md` keeps the master ownership list whether an NPC is in the party or not.

If an NPC joins or leaves during an active Campaign Turn, stage the party-membership change, location effect, and carried-possession bookkeeping in `turn_save.md`. Do **not** update `NPC-state.md` or `inventory.md` merely because the join or leave occurred in the fiction.

At approved reconciliation:

### When an NPC joins the party

1. mark party membership in `NPC-state.md`
2. keep the master ownership list there
3. add an expanded active inventory section in `inventory.md` for carried possessions that need detailed mechanical bookkeeping
4. reconcile staged membership, location, item, resource, charge, ammunition, condition, and other relevant changes from `turn_save.md`

### When an NPC leaves the party

1. reconcile final quantities, currency, equipment, charges, acquired items, lost items, and other relevant possessions back into the master ownership list in `NPC-state.md`
2. reconcile staged membership, location, condition, and possession changes
3. update the NPC's off-party location when known
4. only then remove or collapse the expanded section from `inventory.md`

Do not let possessions disappear merely because party membership changed.

When `In party: Yes`, do not duplicate moment-to-moment movement in `NPC-state.md`. The last completed party location belongs in `active_game.json`; unfinished Campaign Turn movement and combat position belong in `turn_save.md` until reconciliation.

## Cross-file NPC references

`world_state.md` may reference persistent NPCs when they matter to locations, factions, quests, clues, discoveries, or world consequences, but must use the stable NPC ID and should not duplicate the full NPC record.

`NPC-state.md` owns an NPC's revealed personal quest involvement, promises, information, rewards offered, conditions, and related continuity. `world_state.md` owns the overall quest or mission state and unresolved questions known to the core PCs.

For merchant NPCs, `NPC-state.md` owns persistent business state, current shop stock, vendor-specific pricing state, storefront presentation fields, and services. Routine recurring Base Prices are owned separately by `routine_item_prices.md`.

Relationship-state semantics are defined in `RELATIONSHIPS_AND_SOCIAL_INTERACTIONS.md`, inventory detail in `INVENTORY_EQUIPMENT_AND_ITEMS.md`, reproduction in `REPRODUCTION_AND_LINEAGE.md`, and shop behavior in `SHOPS_PRICING_AND_TRANSACTIONS.md`.
