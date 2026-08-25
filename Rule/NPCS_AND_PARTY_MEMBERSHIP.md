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