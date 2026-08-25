### NPCs in world state and quests

`world_state.md` may reference NPCs when they matter to locations, factions, quests, clues, discoveries, or consequences, but each persistent NPC reference must use the stable NPC ID and may include the current NPC name for readability. Do not rely on a name-derived Markdown heading or anchor as the identity key, and do not duplicate the full persistent NPC record.

`world_state.md` owns overall quest/mission state. `NPC-state.md` owns the NPC's personal involvement, motives, promises, information, rewards offered, conditions, and related continuity.

A shop's existence and location may be referenced in `world_state.md`, while the shop owner/operator's `NPC-state.md` record owns persistent business state, current shop stock, vendor pricing state, storefront presentation fields, and services. `routine_item_prices.md` separately owns the recurring Base Price authority for items explicitly classified there as routine/basic repeat goods.