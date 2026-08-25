## Equipment and special effects

Meaningful items may track quantity, equipped/carried/stored state, damage or armor values, charges, durability, attunement or bonding, magical effects, curses, and hidden or unidentified properties.

Owned inventory must preserve enough established mechanical detail to resolve meaningful item effects correctly. Hidden or unidentified properties must not be revealed merely because they are stored for continuity.

Persistent file ownership, NPC possession mirroring, shop-stock ownership, and acquisition-snapshot rules live in `campaigns/GAME_MASTER_RULES.md`.

## Equipment ownership and special-effect continuity

Do not forget an item's established special effect simply because several scenes pass. Check `inventory.md`, `character_sheet.md`, `NPC-state.md`, and `world_state.md` as relevant before resolving an item-dependent effect.

For persistent NPCs, `NPC-state.md` owns the master list of what the NPC owns. `inventory.md` expands mechanically relevant possessions only while that NPC is currently traveling with the party. Shop stock belongs in the shop NPC's `NPC-state.md` record as business inventory until a party member actually acquires an item.

Standard official items that are still vendor stock use the compact linked storefront architecture below rather than duplicating full official mechanics into the shop record.