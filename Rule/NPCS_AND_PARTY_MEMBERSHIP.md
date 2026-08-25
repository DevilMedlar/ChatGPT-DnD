Within each campaign, persistent NPCs receive stable campaign-local IDs such as `NPC-0001` in that campaign's `NPC-state.md`. Cross-file references use the stable NPC ID plus the NPC's current name for readability; names and Markdown headings are not identity keys.

## Campaign-local identity

Each campaign assigns persistent NPCs stable campaign-local IDs such as `NPC-0001` in its own `NPC-state.md`. NPC IDs are never reused within that campaign, and cross-file references use the stable NPC ID plus the NPC's current name instead of relying on name-derived Markdown headings or anchors.

The two required core PCs are defined through that campaign's `character_sheet.md` and `active_game.json` advancement state under the repository-wide core-party rules. The ChatGPT-controlled core PC is a PC, not an NPC.

Detailed NPC ownership, party-membership reconciliation, vendor state, and cross-file behavior are defined in this directory's `GAME_MASTER_RULES.md`.

## NPC continuity and ownership

`NPC-state.md` is authoritative for persistent NPC stable IDs, identity, appearance, statistics, abilities, condition, personality, relationships and attractions, knowledge/secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC-specific continuity.

Every persistent NPC receives one stable campaign-local ID in the form `NPC-0001`, `NPC-0002`, and so on when first added to `NPC-state.md`. The ID never changes or gets reused for another NPC. Cross-file references must use the stable NPC ID; the current NPC name may accompany it for readability. Names and name-derived Markdown headings or anchors are display/navigation aids, not identity keys.

Important NPCs should track only fields that are relevant and established. When useful, this includes:

- stable NPC ID; name, age, gender/pronouns, species/ancestry, role, occupation, faction, and status
- appearance and verified visual-continuity references
- level, class/archetype, XP or advancement state when used, HP, temporary HP, AC, initiative, speed, proficiency, hit dice/recovery resources, ability scores, saves, skills, attacks, features, spells, conditions, and limited resources
- normal/current known location when not traveling with the party
- party membership and the last known non-party location
- personality, values, goals, wants, needs, fears, likes, dislikes, habits, and priorities
- factual knowledge, beliefs, information shared, information withheld, secrets known, secrets held, and false beliefs
- master personal ownership list
- NPC-specific involvement in quests or missions
- shop/services information, business pricing state, current stock, quantities, linked official-item storefront fields, and services when applicable
- compact NPC-specific continuity history

### NPC advancement

NPC advancement is not universal.

- Minor or background NPCs remain at their established mechanical state unless something in the fiction changes them.
- Important persistent NPCs may gain or lose Level, abilities, spells, features, equipment, resources, class/archetype, resistances, weaknesses, transformations, or other mechanical traits when justified by training, experience, story events, consequences, or other established causes.
- Long-term party NPCs should advance often enough to remain mechanically relevant, but they do **not** automatically use the core PCs' XP system unless that has been explicitly established for the NPC.
- NPC advancement may be level-based, ability-based, feature-based, or another established form appropriate to that NPC.
- Existing NPCs do **not** automatically scale merely because the core PCs became stronger. A previously established weaker NPC may remain weaker, while new or changed threats can become harder naturally through the world and story.
- Any NPC advancement caused during an active Campaign Turn is staged in `turn_save.md` and transferred to `NPC-state.md` only through the normal confirmed Campaign Turn save process.

### NPC inventory and party-membership flow

`NPC-state.md` keeps the master ownership list whether an NPC is in the party or not.

If an NPC joins or leaves during an active Campaign Turn, stage the party-membership change, location effect, and carried-possession bookkeeping in `turn_save.md`. Do **not** update `NPC-state.md` or `inventory.md` merely because the join or leave occurred in the fiction.

At approved Campaign Turn reconciliation, or when the change is established outside an active Campaign Turn through the normal completed-save workflow:

When an NPC joins the party:

1. mark party membership in `NPC-state.md`
2. keep the master ownership list there
3. add an expanded active inventory section in `inventory.md` for carried possessions that need detailed mechanical bookkeeping
4. reconcile any staged membership, location, item, resource, charge, ammunition, condition, or other relevant changes from `turn_save.md`

When an NPC leaves the party:

1. reconcile their final quantities, currency, equipment, charges, acquired items, lost items, and other relevant possessions back into the master ownership list in `NPC-state.md`
2. reconcile any staged Campaign Turn membership, location, condition, and possession changes
3. update the NPC's off-party location when known
4. only then remove or collapse their expanded section from `inventory.md`

Do not let possessions disappear merely because party membership changed.

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

When NPCs become persistent, list them here with their stable NPC ID, current name, and a short role or relevance note. Do not use a name-derived Markdown anchor as the NPC's identity.

When `In party: Yes`, do not duplicate moment-to-moment movement here. The last completed party location belongs in `active_game.json`; unfinished Campaign Turn movement and combat position belong in `turn_save.md` until Campaign Turn reconciliation.

Keep factual knowledge, beliefs, shared information, withheld information, and secrets separate when they differ.

Use when the NPC is mechanically relevant. A minor noncombat NPC does not need a complete combat block unless play establishes one.

`Level` and `Class / archetype` are mutable mechanical state and are tracked here rather than duplicated in Identity.

This is the NPC's **master ownership list**. It remains here whether the NPC is in the party or not.

When the NPC is currently in the party, `inventory.md` expands mechanically relevant carried possessions for active bookkeeping. The ownership list here remains the master list of what belongs to the NPC.

Use this optional section for quest givers, mission contacts, targets, witnesses, missing persons, suspects, guides, faction representatives, villains, or other story-linked NPCs.

`NPC-state.md` records **this NPC's involvement**. `world_state.md` remains authoritative for the overall quest or mission state.

Keep a compact NPC-specific history of events that explain the NPC's current state, behavior, relationships, obligations, or role. Do not duplicate the entire `session_log.md`.

## Shared Rule Authority

NPC party joins/leaves, possession reconciliation, cross-file ownership, stable cross-file references, NPC advancement, relationship-state semantics, shop/vendor behavior, fresh-start isolation, append-first preservation, and Campaign Turn staging are governed by `../GAME_MASTER_RULES.md`.

This file contains only Campaign 1's persistent NPC master state and the Campaign 1 NPC record schema.
