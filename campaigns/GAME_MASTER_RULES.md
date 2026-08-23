# Shared Campaign Rules

These rules apply to every numbered campaign under `campaigns/` unless that campaign explicitly establishes a narrower local override.

Repository-wide gameplay mechanics and behavioral rules live in `../GAME_MASTER_RULES.md`. Each numbered campaign owns its own canon and mutable state. A campaign-local `GAME_MASTER_RULES.md`, when present, should contain only campaign-specific canon, exceptions, or overrides rather than duplicating these shared rules.

Throughout this file, references such as `active_game.json`, `turn_save.md`, `character_sheet.md`, `NPC-state.md`, `routine_item_prices.md`, `inventory.md`, `world_state.md`, `session_log.md`, and `art/art_log.md` mean the corresponding files inside the active numbered campaign folder.

## Fresh-start canon

1. A numbered campaign begins from the files on the repository's current branch plus facts explicitly established by the player for that campaign.
2. Do **not** recover, infer, reconstruct, or borrow character data, NPC data, items, locations, factions, relationships, quests, story events, secrets, rolls, consequences, visual canon, or any other campaign content from deleted files, repository history, previous chats, memory, or another campaign.
3. Repository history may be consulted only for reusable **framework, file structure, mechanics, templates, and operating instructions**, and only when the player explicitly allows that use.
4. Historical framework is never evidence that any historical character, NPC, item, location, relationship, quest, or story fact exists in the current campaign.
5. Prior chats are non-canonical unless the player explicitly imports a specific fact from them.
6. The player's newest explicit statement overrides conflicting assistant-created material.
7. Never silently overwrite established canon.

## Append-first preservation

Campaign-state files are historical records as well as current state.

- Add new Campaign Turn information instead of rewriting, compressing, summarizing away, reorganizing, or deleting older information merely for neatness or brevity.
- Rewrite or delete established material only when it is factually wrong, contradicts a newer explicit player choice, is an accidental duplicate/error, makes current mechanics incorrect, or the player explicitly requests the change.
- When a correction is needed, make the smallest practical edit and preserve useful history whenever possible by marking old information as corrected or superseded.
- Static documentation and shared rule files may be updated when the rules themselves change.

## PC advancement authority

The repository-wide gameplay rulebook owns **how** PC advancement works: XP mode, default thresholds, award logic, rounding, and level-up behavior.

Within each numbered campaign:

- `active_game.json` owns the authoritative **completed PC advancement state** through campaign-wide `xp_mode` and `character_advancement.<character>.level`, `xp_current`, and `xp_next_level`.
- `character_sheet.md` displays each PC's Level and XP as synchronized human-readable mirrors of that completed state. Those mirror values do not override `active_game.json`.
- During an active Campaign Turn, staged XP awards, threshold changes, and level changes belong in `turn_save.md` and temporarily overlay the completed permanent representations until approved reconciliation.
- After any completed save that changes PC advancement, the Level/XP mirrors in `character_sheet.md` must exactly match the authoritative values in `active_game.json`.

## Campaign Turn terminology and lifecycle

### Campaign Turn

A **Campaign Turn** is a numbered campaign's complete persistence/gameplay unit. It begins from one completed permanent save state and remains open until the whole connected gameplay unit is intentionally completed.

A Campaign Turn may contain any number of numbered Steps, including:

- scene setup and narration
- dialogue and decisions
- exploration and movement
- requested rolls and their results
- initiative setup
- multiple combat rounds
- every creature's individual combat turn
- attacks, damage, healing, conditions, item use, charges, ammunition, spell slots, class resources, and other changing state
- combat ending
- post-combat searching, dialogue, loot, clues, discoveries, movement, and other directly connected actions

Ending a creature's normal D&D combat turn does **not** end the Campaign Turn.

Ending a combat round does **not** end the Campaign Turn.

Combat itself ending does **not automatically** end the Campaign Turn if the connected gameplay sequence continues.

During active combat, an unqualified phrase such as `end turn` means the current creature's **Combat Turn** ends. It does not trigger Campaign Turn reconciliation. The persistence workflow is entered only when the full Campaign Turn is intentionally interpreted as complete.

### Combat Turn and Combat Round

A **Combat Turn** is one creature's activation within initiative order.

A **Combat Round** is one initiative cycle through the active combatants.

Combat Turns and Combat Rounds exist inside a Campaign Turn and never cause `turn_save.md` to reset merely because they end.

### Scene and Step authority

- `active_game.json.campaign_turn_number` is the last completed Campaign Turn number. It is not the active unfinished Turn number.
- `active_game.json.current_scene_name` is the scene-name label at the last completed save. Before Campaign Turn 1 begins, it may also describe the current pre-game character-creation context.
- `active_game.json` does **not** store a live Campaign Turn Step.
- `turn_save.md` owns the current/next Campaign Turn number, `Current Step`, and `Current Scene` for the unfinished Turn.
- While a Campaign Turn is `in_progress`, its `Current Scene` and `Current Step` are the authoritative live gameplay position. They overlay the completed scene label in `active_game.json` until approved reconciliation.
- `current_scene_name` is a compact scene label, not a duplicate scene record; detailed location/world facts remain in their owning files.

### Starting a Campaign Turn

Before starting a Campaign Turn:

1. Read the current completed canonical campaign files required for the scene.
2. Confirm `turn_save.md` is `ready` and no older Campaign Turn requires recovery, review, verification, or reset.
3. Use the current permanent files as the starting state rather than copying every starting value into `turn_save.md`.
4. Set `Campaign Turn` to the next Campaign Turn number.
5. Set `Status` to `in_progress`.
6. Set `Current Step` to `0`.
7. Set `Current Scene` to the completed `active_game.json.current_scene_name`, unless the opening gameplay explicitly establishes a different scene before Step 0 is recorded.
8. Set `Base save revision` to the current `save_revision` in `active_game.json`.

The effective state while the Campaign Turn is open is:

`last completed permanent state + turn_save.md overlay`

### Recording Campaign Turn Steps

A Campaign Turn may contain as many numbered Steps as needed.

After each resolved Step:

1. append the relevant action/event, roll calculation when applicable, immediate result, and state deltas to `Turn Events`
2. update `Current Scene` whenever the effective scene changes
3. update `Current In-Turn State` with the compact latest effective values needed to continue or recover the Campaign Turn
4. update `Pending Permanent Transfers` when a result may need persistent reconciliation
5. when a shop transaction occurs, update `Pending Shop Transactions` with the connected vendor-stock, currency, inventory, pricing, and acquisition-snapshot state needed for reconciliation
6. do not repeatedly rewrite permanent campaign files for ordinary changing state inside the Campaign Turn
7. do not increment `save_revision`
8. stage every gameplay-caused persistent change in `turn_save.md` until Confirmation Gate 1, including NPC party joins/leaves, permanent possession or shop changes, routine-item Base Price changes, and visual-continuity changes; another file's ownership workflow must not bypass the Campaign Turn save gates

`Current In-Turn State` is a maintained recovery snapshot, not a full copy of every permanent file and not a full state block repeated after every Step.

Whenever Git repository writing is available, a resolved Step may be checkpointed with a small Git commit for interruption recovery. Step/lifecycle checkpoint commits do **not** increment `save_revision` and are not completed campaign saves.

### Compact roll recording in `turn_save.md`

When recording rolls in Campaign Turn Steps, keep the calculation on one line whenever practical while preserving enough information to reconstruct it.

General pattern:

`**Actor rolls Roll Name:** dice/results + bonuses - penalties ×/÷ other effects = **final total**`

Attack pattern:

`**Attack — Attack Name:** dice/results + modifiers = **total** vs AC/target = **Hit/Miss**`

Damage/healing pattern:

`**Damage/Healing — Source:** dice/results + modifiers ×/÷ effects = **final amount**`

Preserve the dice expression and individual die results when useful, especially for multiple dice, advantage/disadvantage, critical hits, resistance, vulnerability, rerolls, or other effects. Initiative order should record each combatant's final initiative total beside the name.

### Full Campaign Turn end interpretation

When gameplay reaches what may be the end of the full Campaign Turn, first interpret what ended.

A creature's Combat Turn, a Combat Round, or a combat encounter ending is not enough by itself.

When the gameplay flow explicitly means **end the full Campaign Turn**:

1. set `Status` to `ending_review`
2. freeze the Turn ledger
3. stop adding new gameplay actions
4. do **not** write permanent campaign files yet
5. do **not** reset `turn_save.md`

At this point `Current In-Turn State`, together with the final `Current Scene`, becomes the proposed **Final Turn State** for review.

### Confirmation Gate 1: save approval

Before any permanent transfer:

1. review every recorded Step and verify the proposed Final Turn State is fully consistent with the recorded actions, rolls, damage, healing, resource use, movement, scene changes, discoveries, and results
2. resolve any missing, contradictory, uncertain, or unresolved state in the temporary ledger first
3. determine the **Exact Planned Permanent Transfers** to the owning files
4. show the player both the Final Turn State and Exact Planned Permanent Transfers
5. ask: `Confirm Campaign Turn N save? Yes / No / Corrections`

If the player says **No**:

- remain `ending_review`
- change no permanent campaign files
- do not reset the ledger

If the player gives **Corrections**:

- correct the temporary Turn record first
- recalculate the Final Turn State and planned transfers
- show the revised review again
- ask for save confirmation again

If the player says **Yes**:

- record the approval
- set `Status` to `reconciling`
- begin permanent reconciliation

No permanent Campaign Turn save may begin without this confirmation.

### Reconciliation after save approval

After Confirmation Gate 1 is approved:

1. transfer only the approved persistent, continuity-relevant, or historically important results to their proper permanent owners
2. synchronize master/detail representations when one fact must exist in multiple bookkeeping locations, including current-party NPC possession changes in both `NPC-state.md` and `inventory.md`
3. when PC advancement changed, synchronize the Level/XP mirrors in `character_sheet.md` with the approved `level`, `xp_current`, and `xp_next_level` values that will be stored authoritatively in `active_game.json.character_advancement`
4. when a shop purchase occurred, reconcile the connected transaction together: update the shop business stock in `NPC-state.md`, decrease the buyer's currency by the approved Final Transaction Price, add the acquired item to the buyer's `inventory.md` record, preserve the acquisition-time mechanics snapshot, apply the approved compatible/separate stack result, and update the buyer's `NPC-state.md` master ownership too when the buyer is a current-party persistent NPC; do not permanently apply only one side of the transaction
5. when a routine/basic recurring Base Price changed, update `routine_item_prices.md` and every currently stocked vendor row that mirrors that item's Base Price in the same completed save
6. append the completed Campaign Turn checkpoint to `session_log.md`
7. prepare `active_game.json` as the completed-state marker using the completed `campaign_turn_number`, the approved final `Current Scene` as `current_scene_name`, the completed location, and the authoritative completed PC advancement state
8. increment `save_revision` exactly once for the completed permanent save
9. do **not** reset the Turn ledger as part of this permanent save

Whenever tooling permits an atomic multi-file commit, commit the supporting permanent-state updates, `session_log.md`, and completed `active_game.json` revision together in one permanent-save commit. The complete temporary ledger remains intact.

If permanent files must be written sequentially, update supporting permanent files first and update `active_game.json` last.

### Permanent save verification

After the permanent writes land, do not assume the save succeeded merely because the writes returned successfully.

Read/check the affected permanent files again and compare them with the player-approved Final Turn State and Exact Planned Permanent Transfers.

Verify at minimum:

- expected character-state changes landed correctly
- when PC advancement changed, every `character_sheet.md` Level/XP mirror exactly matches the authoritative `active_game.json.character_advancement` values
- expected inventory/resource changes landed correctly
- when a shop purchase occurred, vendor quantity, buyer currency, acquired inventory, acquisition snapshot, and stack result all match the approved transaction
- when a routine/basic item is stocked or its recurring Base Price changes, the vendor row's Base Price exactly matches the authoritative current value in `routine_item_prices.md`
- required NPC master/detail records agree when applicable
- when persistent NPCs are created or cross-referenced, stable NPC IDs are unique, unchanged, and agree across every affected file
- required world/clue changes landed correctly
- `session_log.md` contains the completed Campaign Turn checkpoint
- `active_game.json` contains the completed `campaign_turn_number`
- `active_game.json.current_scene_name` matches the approved final `Current Scene`
- `save_revision` advanced exactly once
- every approved planned transfer is accounted for
- no unrelated campaign state was changed
- no unresolved result remains stranded only in the temporary ledger

If verification fails, keep the Turn ledger intact, do not request reset, and reconcile the permanent state until it matches the approved final state.

When verification passes:

1. set `Status` to `saved_awaiting_reset`
2. preserve the full completed Turn ledger as a safety copy
3. send the player a compact save-completion report confirming the completed Campaign Turn, save revision, important final state, and successful verification
4. explicitly state that `turn_save.md` has **not** been reset
5. ask: `Confirm reset for Campaign Turn N+1? Yes / No`

A checkpoint commit that only records the verified `saved_awaiting_reset` ledger state does not increment `save_revision`.

### Confirmation Gate 2: reset approval

The successful permanent save does **not** automatically erase its temporary source ledger.

If the player says **No**:

- remain `saved_awaiting_reset`
- keep the completed Turn events, Final Turn State, planned transfers, and verification information intact
- do not replay or resave the completed Campaign Turn

If the player says **Yes**:

1. reset the temporary ledger
2. clear the completed Turn events and Current In-Turn State, reset `Pending Shop Transactions` to `None yet.` while preserving its template, clear pending transfers, final review, save verification, and prior reset approval
3. prepare the next Campaign Turn number
4. set `Status` to `ready`
5. set `Current Step` to `0`
6. set `Current Scene` to `None yet.`
7. set `Base save revision` to the newly completed `save_revision`

The reset is a cleanup/checkpoint operation. It does **not** increment `save_revision` because the permanent Campaign Turn save already completed.

### Campaign Turn recovery by status

Before beginning or continuing gameplay, read `turn_save.md` and use its status to determine recovery:

- `ready` — no unfinished Campaign Turn exists; the next Campaign Turn may begin.
- `in_progress` — resume the active Campaign Turn from the last completed permanent state plus the temporary overlay. `Current Step` and `Current Scene` in `turn_save.md` are the live gameplay position. Never start another Campaign Turn first.
- `ending_review` — the full Campaign Turn end was interpreted and the ledger is frozen. No permanent Campaign Turn write is authorized until the player confirms the final review.
- `reconciling` — the player approved the final state and the permanent save may be partially or fully written. Check `active_game.json`, the affected permanent files, and the approved Final Turn State before taking any action. Never replay the Campaign Turn automatically.
- `saved_awaiting_reset` — the permanent Campaign Turn save is complete and verified. Do not replay or resave it. Only the player's reset confirmation remains.

Also compare `Base save revision` with `active_game.json.save_revision` in context with the status:

- `in_progress` normally overlays the same base revision currently recorded in `active_game.json`.
- `reconciling` may temporarily coexist with a newer `active_game.json.save_revision` if the permanent save has already landed and is awaiting verification.
- `saved_awaiting_reset` intentionally references the older base revision while `active_game.json` already contains the newly completed revision.
- a base revision greater than the completed `active_game.json.save_revision` is inconsistent and must be reconciled before play continues.

Never silently discard an unfinished, frozen, reconciling, or saved-awaiting-reset Campaign Turn ledger.

## Character creation and Campaign Turns

Character creation occurs before Campaign Turn 1. It uses **character-creation checkpoint saves**, not the Campaign Turn ledger. `turn_save.md` remains prepared for Campaign Turn 1 and is not opened, reconciled, or reset merely because character-creation choices are saved.

A character-creation checkpoint is a logical group of finalized choices that the player is ready to make permanent. Discussion, previews, rejected options, and unfinished choices do not create a checkpoint or increment `save_revision`.

Before writing a character-creation checkpoint:

1. determine the exact finalized choices and every permanent file that must change
2. calculate any derived values that depend on those choices and verify them against the established rules
3. prepare the proposed `session_log.md` checkpoint entry and the new `active_game.json.save_revision`
4. keep `campaign_turn_number` at `0` because no gameplay Campaign Turn has completed
5. keep `turn_save.md` unchanged and `ready`
6. show the player the finalized checkpoint and exact planned permanent changes
7. ask: `Confirm character-creation checkpoint save? Yes / No / Corrections`

If the player says **No**, write nothing and do not increment `save_revision`.

If the player gives **Corrections**, revise the proposed character-creation state and planned permanent changes, show the corrected checkpoint again, and ask for confirmation again.

If the player says **Yes**:

1. write only the confirmed permanent character-creation changes to their proper owners
2. synchronize duplicated required representations, including the Level/XP mirrors in `character_sheet.md` and authoritative PC advancement state in `active_game.json` when advancement is affected
3. append one chronological character-creation checkpoint to `session_log.md` identifying the completed save revision and summarizing only what that checkpoint finalized
4. update `active_game.json` last as the completed-save marker with the new authoritative state, a `save_revision` increment of exactly `1`, and a compact `last_sync_note`
5. do not change `campaign_turn_number` from `0` and do not create a Campaign Turn Step

Whenever tooling permits an atomic multi-file commit, the affected permanent files, `session_log.md`, and `active_game.json` must be committed together as the character-creation checkpoint save. There is no second reset gate because character creation has no temporary source ledger to erase.

If permanent files must be written sequentially, update the supporting permanent files and `session_log.md` first and `active_game.json` last. Do not report the checkpoint as complete until all required files have been reread and verified. If an interruption or partial write occurs, treat the checkpoint as incomplete; inspect the affected files, `session_log.md`, and `active_game.json.save_revision`, reconcile them to one confirmed state, and only then continue character creation.

After every character-creation checkpoint, verify at minimum:

- every confirmed choice landed in the correct permanent owner
- no undecided field or rejected option was invented or made canonical
- derived character values are internally consistent
- when Level/XP is involved, `character_sheet.md` mirrors exactly match `active_game.json.character_advancement`
- starting equipment and `inventory.md` agree when inventory was part of the checkpoint
- `session_log.md` contains exactly one corresponding character-creation checkpoint for the completed `save_revision`
- `campaign_turn_number` remains `0`
- `turn_save.md` remains `ready` for Campaign Turn 1 and was not used as a character-creation ledger
- `save_revision` advanced exactly once
- `last_sync_note` accurately describes the completed checkpoint
- no unrelated campaign state changed

The final character-creation checkpoint must additionally verify that every required character-creation field listed in the repository-wide `Character creation` rules is established for every required player character in that campaign. Only that confirmed and verified final checkpoint sets `active_game.json.character_created` to `true`. Until then it remains `false`. Before Campaign Turn 1 begins, `active_game.json.current_scene_name` may continue to identify the current pre-game character-creation context; no live Campaign Turn Step exists outside `turn_save.md`.

## Equipment ownership and special-effect continuity

Do not forget an item's established special effect simply because several scenes pass. Check `inventory.md`, `character_sheet.md`, `NPC-state.md`, and `world_state.md` as relevant before resolving an item-dependent effect.

For persistent NPCs, `NPC-state.md` owns the master list of what the NPC owns. `inventory.md` expands mechanically relevant possessions only while that NPC is currently traveling with the party. Shop stock belongs in the shop NPC's `NPC-state.md` record as business inventory until a party member actually acquires an item.

Standard official items that are still vendor stock use the compact linked storefront architecture below rather than duplicating full official mechanics into the shop record.

## Official shop items and vendor pricing

### Standard official item sourcing

Normal standard vendor stock uses official D&D items whose usable mechanics are freely viewable.

For a candidate standard official item:

1. choose it from the relevant official item/equipment catalog or category
2. open the item's direct official page before using it as normal stock
3. verify that enough actual mechanics are freely viewable to use the item without requiring a purchase
4. reject a candidate whose page is only a teaser, marketplace redirect, ownership prompt, or otherwise hides the usable mechanics, and choose another suitable official item instead
5. place the verified direct official URL on the **item name itself** in the vendor stock row

The campaign does not maintain a duplicate local official-item catalog or a second detailed inspection layer for normal standard vendor items. D&D Beyond or another approved official source is a mechanics/reference authority for the standard item while it remains shop stock, but it is **not** the campaign's vendor-price authority.

External URLs and access rules can change. A stored reference may be rechecked when an item is newly stocked or when the existing reference no longer works. If a reference fails at acquisition time, resolve that case individually before finalizing the owned-item mechanics snapshot.

Official shop references must eventually align with that campaign's chosen D&D rules/version baseline. This vendor architecture does not itself choose that broader baseline.

Homebrew, custom, unique, campaign-created, and mechanically modified items are outside this standard official vendor-item schema. Their mechanics and persistence must be handled by whatever separate campaign architecture governs those items rather than forcing them into the normal official-stock flow.

### Storefront presentation

`NPC-state.md` owns the persistent business-level vendor state and `Current Shop Stock` table.

For normal standard official stock, the row contains:

- linked Item name
- Base Price
- Qty
- Category
- Key Mechanics
- Short Description

`Category` and `Key Mechanics` are compact storefront fields derived from the current linked official reference. `Short Description` is compact generated storefront text. These are presentation fields, not independent permanent mechanical authorities.

Do not add a separate official-reference column, a duplicate local official-item catalog, a locally maintained detailed copy of standard official mechanics, or an extra generated inspection block that repeats the stock row.

### Base Price and Final Price

`Base Price` is the campaign starting price before the applicable vendor or transaction modifiers.

`routine_item_prices.md` is authoritative for which items are classified as routine/basic repeat goods for recurring-price purposes and for each such item's current recurring Base Price. A routine/basic item must use that established Base Price whenever stocked. Every vendor stock row for that routine item mirrors the value from `routine_item_prices.md` and must not independently redefine it.

This recurring-price rule applies only to items explicitly classified in `routine_item_prices.md`; it does not require every item appearing at multiple merchants to share one Base Price. If an item has no entry there, do not claim it already has an established routine recurring Base Price. Establish the entry through the appropriate completed-save workflow before relying on routine-price authority.

For other official items, the GM may establish a reasonable Base Price when the item appears in stock. The price should be sensible rather than arbitrary noise. Relevant considerations can include rarity, mechanical power, usefulness, duration or number of uses, whether the item is consumed, replaceability, local scarcity, item category, and comparable established campaign prices. These non-routine items do not require a permanent global Base Price registry.

After Base Price is established:

`final price = base price +/- applicable merchant or unused contextual modifiers`

Merchant markup/discount is business or relationship pricing, such as ordinary shop policy, relationship treatment, reputation, faction standing, or negotiation.

Contextual market factors include scarcity, shortages, unusual demand, temporary events, and similar established market circumstances. A contextual factor is not automatically a merchant markup/discount.

A pricing factor must not be counted more than once in the same stock listing or transaction. If scarcity, rarity, local conditions, or another factor already affected that listing's Base Price, the same factor must not be applied again to Final Price. A distinct merchant markup or discount may still apply afterward because it is a different pricing factor.

A change to an established Base Price in `routine_item_prices.md` is campaign-wide, not a single-vendor adjustment. When that recurring Base Price changes, every currently stocked vendor row for that item must be reconciled to the new mirrored Base Price in the same completed save whenever such rows exist. Vendor-specific price differences continue to use Final Price modifiers instead.

The exact stacking, ordering, and rounding rules for multiple distinct modifiers remain intentionally undecided until the active campaign establishes them.

### Shop purchase flow

During an active Campaign Turn, a purchase is staged in `turn_save.md` under `Pending Shop Transactions`; do not immediately rewrite permanent vendor or inventory files.

A completed purchase has connected state on both sides:

- vendor quantity decreases by the purchased quantity
- buyer currency decreases by the approved Final Transaction Price
- the buyer gains the purchased item in the appropriate inventory record
- the acquired standard official item's mechanically relevant facts are preserved in the acquisition snapshot governed by `inventory.md`
- compatible or separate stack handling follows `inventory.md`
- if the buyer is a current-party persistent NPC, that NPC's master ownership list in `NPC-state.md` is reconciled too

After Confirmation Gate 1, reconcile all connected sides together. Never permanently apply only the vendor side, only the currency side, or only the inventory side of the transaction.

Once an official item has been acquired and its relevant mechanics are established in campaign inventory, later changes to the external official page do not silently rewrite the already-owned campaign item. `inventory.md` owns the acquired-item snapshot and stack-compatibility rules.

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
- Long-term party NPCs should advance often enough to remain mechanically relevant, but they do **not** automatically use the PCs' XP system unless that has been explicitly established for the NPC.
- NPC advancement may be level-based, ability-based, feature-based, or another established form appropriate to that NPC.
- Existing NPCs do **not** automatically scale merely because the PCs became stronger. A previously established weaker NPC may remain weaker, while new or changed threats can become harder naturally through the world and story.
- Any NPC advancement caused during an active Campaign Turn is staged in `turn_save.md` and transferred to `NPC-state.md` only through the normal confirmed Campaign Turn save process.

### Relationship and attraction state

Relationship information is made of separate facts and must not be collapsed into one label.

When relevant, track:

- **relationship status** such as single, dating, married, widowed, complicated, or another established state
- **current partner(s)**
- **romantic interest(s)**
- **sexual interest(s)** for explicitly adult NPCs only
- target-specific attraction toward relevant PCs or NPCs
- **jealousy / rivalry**
- **established boundaries**
- **consent / availability notes**
- target-specific disposition, trust, respect/fear, attraction/tension, relationship role, debts/favors, promises/obligations, and important history

`Single` does **not** imply romantic or sexual interest. `Married` does **not** automatically imply lack of attraction to everyone else. Friendship, gratitude, debt, party membership, attraction, partnership status, boundaries, and consent are separate state facts. Do not infer one from another.

For NPCs below 18, omit sexual-interest fields entirely. Any recorded crush or romantic information must remain age-appropriate and nonsexual under the repository-wide Adult-content rules.

Numbers may be used internally when helpful, but narration should remain natural rather than exposing every relationship as a meter.

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

### NPCs in world state and quests

`world_state.md` may reference NPCs when they matter to locations, factions, quests, clues, discoveries, or consequences, but each persistent NPC reference must use the stable NPC ID and may include the current NPC name for readability. Do not rely on a name-derived Markdown heading or anchor as the identity key, and do not duplicate the full persistent NPC record.

`world_state.md` owns overall quest/mission state. `NPC-state.md` owns the NPC's personal involvement, motives, promises, information, rewards offered, conditions, and related continuity.

A shop's existence and location may be referenced in `world_state.md`, while the shop owner/operator's `NPC-state.md` record owns persistent business state, current shop stock, vendor pricing state, storefront presentation fields, and services. `routine_item_prices.md` separately owns the recurring Base Price authority for items explicitly classified there as routine/basic repeat goods.

## Image and reference-art persistence

Each campaign's `art/art_log.md` is that campaign's canonical visual index.

Generated image binaries remain player-managed under the repository-wide image rules. File existence does not itself make an image canonical.

When newly established continuity-critical visual information occurs during an active Campaign Turn, stage it in `turn_save.md` and include `art/art_log.md` in the Exact Planned Permanent Transfers. Add it to `art/art_log.md` only during approved Campaign Turn reconciliation. Outside an active Campaign Turn, persist it through the normal completed-save workflow.

When the player supplies reference art or manually adds images to the repository:

- record the repository path only after it actually exists
- record which features are canonical and which are inspiration only
- prefer written canonical traits over accidental differences in generated images
- never assume an unverified image path exists

If reference art is supplied or adopted during an active Campaign Turn, the image file may exist immediately, but canonical path/trait metadata remains staged in `turn_save.md` until approved Campaign Turn reconciliation. File existence does not bypass Confirmation Gate 1.

## Campaign save routing and file ownership

`active_campaign.json` in this `campaigns/` directory is a **campaign selector only**. It identifies the active numbered campaign and points to that campaign's `active_game.json`.

It is not the authoritative place for session, Campaign Turn, character level, XP, location, or other changing gameplay state. Do not rewrite `active_campaign.json` after ordinary Campaign Turns unless the active campaign selection, campaign path, or pointer-level phase actually changes.

Campaign saves are isolated:

- Campaign 1 saves only to `campaign-1/`.
- Campaign 2 saves only to `campaign-2/`.
- Campaign 3 saves only to `campaign-3/`.
- Continue the same rule for later campaigns.
- Never write one campaign's state into another campaign folder unless the player explicitly requests a crossover or import.

Within each numbered campaign, file ownership is:

- `active_game.json` — authoritative **last completed live save**: session, completed `campaign_turn_number`, completed/pre-game `current_scene_name`, location, character-creation state, authoritative completed PC advancement through `xp_mode` and `character_advancement`, save revision, and latest synchronization note. It does not store the live Campaign Turn Step.
- `turn_save.md` — temporary authoritative ledger for the current Campaign Turn: current/next Campaign Turn number, `Current Step`, `Current Scene`, numbered events, compact effective in-turn state, `Pending Shop Transactions`, pending transfers, final review, permanent-save verification, and reset approval.
- `character_sheet.md` — player-character statistics, abilities, appearance, personal state, established relationship continuity, and synchronized human-readable Level/XP mirrors of `active_game.json`.
- `NPC-state.md` — persistent NPC stable IDs, identity, appearance, statistics, abilities, condition, personality, relationships/attractions, knowledge/secrets, party membership, off-party location, master personal possessions, NPC-specific quest involvement, shops/services, shop stock, and NPC-specific continuity. It owns the stable cross-file identity key for each persistent NPC.
- `routine_item_prices.md` — authoritative campaign-local classification and recurring Base Price reference for routine/basic repeat goods. Vendor rows mirror these Base Prices; this file does not own item mechanics, vendor quantities, merchant modifiers, Final Price, or inventory.
- `inventory.md` — detailed active mechanical bookkeeping for player characters and possessions carried by current party NPCs. For NPCs, `NPC-state.md` remains the master ownership list.
- `world_state.md` — locations, factions, overall quests/missions, clues, discoveries, player-known world secrets, world consequences, and lightweight world-context references to persistent NPCs by stable NPC ID and current name.
- `session_log.md` — chronological completed character-creation checkpoint saves and completed Campaign Turn history.
- `art/art_log.md` — visual continuity and verified reference-art information.
- `README.md` — static campaign documentation; do not use it as a duplicate live save.
- a local `GAME_MASTER_RULES.md`, when present — only campaign-specific canon, exceptions, or overrides that are not already owned by the shared repository or campaign rulebooks.

## Persistence

The detailed Campaign Turn workflow is defined above. The persistence rules below govern how that workflow writes permanent state.

### Permanent transfer destinations

At approved Campaign Turn reconciliation, transfer only persistent, continuity-relevant, or historically important results to their correct owners.

Typical destinations include:

- `character_sheet.md` — PC HP, conditions, abilities, character resources, synchronized human-readable Level/XP mirrors, and lasting personal state
- `NPC-state.md` — NPC HP, conditions, abilities, relationships, party status, master personal-possession ownership/quantities, shop stock/services changes, and other persistent NPC state
- `routine_item_prices.md` — explicit routine/basic classification changes and recurring Base Price additions or revisions, together with any required vendor Base Price mirror updates
- `inventory.md` — detailed active item quantities, charges, currency, ammunition, consumables, equipment changes, evidence, and other possessions for PCs and current party NPCs
- `world_state.md` — persistent locations, quests, factions, discoveries, clues, and world consequences
- `session_log.md` — chronological character-creation checkpoint or completed Campaign Turn summary and continuity-critical events
- `art/art_log.md` — newly established visual continuity when relevant
- `active_game.json` — completed session/Campaign Turn/`current_scene_name`/location, authoritative `xp_mode` and `character_advancement`, save revision, and latest sync state

For a **current party NPC**, an ownership-changing item event may require both `NPC-state.md` and `inventory.md` to be updated in the same completed save:

- update `NPC-state.md` so the NPC's master ownership list remains correct
- update `inventory.md` so the NPC's expanded active mechanical bookkeeping remains correct

Examples include consuming or gaining an item, spending or receiving currency, losing ammunition, transferring equipment, changing quantities, or permanently changing charges/uses.

For a **shop purchase**, reconcile the connected transaction rather than updating isolated pieces: update the shop NPC's business stock in `NPC-state.md`, decrease the buyer's currency by the approved Final Transaction Price, add the acquired item and acquisition snapshot to the appropriate `inventory.md` record, apply the compatible/separate stack result, and update the buyer's `NPC-state.md` master ownership too when the buyer is a current-party persistent NPC. For a routine/basic repeat good, verify that the shop row's Base Price matches `routine_item_prices.md`. Shop stock must not be treated as the shopkeeper's personal carried possessions.

Do not leave a master record stale merely because the same possession also has a more detailed active representation in `inventory.md`.

### Save revision rule

`active_game.json` contains `save_revision`.

For a completed Campaign Turn or other completed persistent save revision:

1. determine all permanent campaign files that need real changes
2. prepare the canonical state/history updates
3. prepare `active_game.json` with the new completed authoritative state
4. increment `save_revision` by exactly 1 only for the completed permanent save
5. set `last_sync_note` to a compact description of what that completed revision represents
6. if a required permanent-state update fails or remains unresolved, do not pretend the save completed and do not finalize the revision until the permanent state is reconciled

Individual Campaign Turn Steps, status checkpoints, final-review checkpoints, `saved_awaiting_reset` checkpoints, and the later temporary-ledger reset do **not** increment `save_revision`.

Whenever atomic Git tooling is available, one completed persistent save revision should correspond to one permanent-state Git commit containing the synchronized supporting permanent files, `session_log.md` when applicable, and `active_game.json`. The temporary ledger is deliberately **not reset** in that commit.

If the environment cannot make one atomic multi-file permanent save and must write files sequentially, update supporting permanent files first and `active_game.json` last. Then verify the completed state before moving the temporary ledger to `saved_awaiting_reset`.

The later player-approved reset of `turn_save.md` is a separate cleanup/checkpoint operation and does not create another campaign save revision.

A file does not need fictional changes just to prove it was checked. If nothing substantive changed, preserve it.

The revision marks a completed campaign save checkpoint. It does not permit old campaign history to become canon.

Do **not** remove or delete anything from a file unless it is necessary. Do **not** reorganize a file unless chronological order or clear ownership requires it.

Examples of reasons to remove, delete, or correct existing material include, but are **not limited to**:

- items were sold, lost, used, consumed, destroyed, traded, transferred, or otherwise legitimately removed from a character's possession
- an established fact is explicitly corrected or superseded by the player
- duplicate or accidental erroneous information must be removed
- a mechanical state would otherwise remain incorrect
- information conflicts and the current canonical source cannot be resolved from existing records; ask which conflicting fact to keep
- chronological order

### Session log behavior

`session_log.md` is chronological. Each completed character-creation checkpoint save and each completed Campaign Turn should be appended as a new checkpoint rather than replacing older checkpoints. Every checkpoint should identify its completed `save_revision`, and Campaign Turn checkpoints should also identify their completed Campaign Turn number.

For character creation, record only the choices and derived state actually finalized by that confirmed checkpoint; do not log every option discussed or rejected. For gameplay, record important rolls, choices, consequences, XP awards, scene transitions, discoveries, relationship changes, combat outcomes, and other continuity-critical events. The session log summarizes completed Campaign Turns and does not need every granular Step already preserved during the temporary Turn ledger.
