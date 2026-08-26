# Campaign Setup, Activation, and Navigation

## Continuing an existing campaign

Before continuing play:

1. read the applicable reusable rules under `Rule/`
2. read `campaigns/active_campaign.json`
3. follow its pointer to the active numbered campaign
4. read that campaign's `Rules/Campaign-N_Rules.md` so any persistent campaign-specific overrides are applied
5. read that campaign's `active_game.json` and `turn_save.md`
6. use the `turn_save.md` status to recover, resume, review, verify, reset, or begin the next Campaign Turn correctly
7. read the other canonical state files needed for the current scene

Do not rely on chat memory when the current repository state can answer the question.

## Numbered campaign structure

Each numbered campaign is a sibling folder such as `campaign-1/`, `campaign-2/`, `campaign-3/`, and so on.

A normal numbered campaign contains:

```text
active_game.json
turn_save.md
character_sheet.md
NPC-state.md
routine_item_prices.md
inventory.md
world_state.md
session_log.md
Rules/
  Campaign-N_Rules.md
art/
  art_log.md
```

The numbered campaign folder owns live campaign state and its own narrowly scoped persistent campaign-specific rules. Reusable repository-wide rules belong in `Rule/`, and reusable blank sheet structure belongs in `New-Sheets/`.

## Template instantiation contract

`New-Sheets/` files are **blueprints**, not byte-for-byte live campaign files.

When creating a numbered campaign from `New-Sheets/`, instantiate only the structure and initial state that the live campaign file needs. Reusable instructions, rule-authority prose, examples, placeholder records, sample rows, explanatory schema text, and template-only labels remain in `New-Sheets/` and must not be copied into live campaign state merely because they appear in a template.

### What becomes live state

Copy or create only:

- state-owning headings and field names
- required table headers when the live file needs an empty table
- blank fields that represent not-yet-established campaign facts
- explicit empty-state markers such as `None established.` or `None yet.` when useful
- required initialization values defined by the rules
- campaign-specific titles or identifiers
- actual campaign facts that have already been explicitly established for the new campaign

### What stays template-only

Do **not** copy into a live campaign file merely because it appears in `New-Sheets/`:

- rule-authority paragraphs or cross-reference explanations
- instructional prose explaining how a sheet works
- example formats or example code blocks
- headings explicitly labeled as templates
- placeholder records such as `NPC-####`, `NPC Name`, `Item Name`, `Service Name`, or similar examples
- blank sample vendor rows or sample repeated records whose only purpose is to demonstrate schema
- lists explaining which optional fields may be tracked
- duplicate operating rules already owned by `Rule/`

A repeated-record template is instantiated only when the corresponding real entity or event exists. For example, do not copy a full blank NPC record into `NPC-state.md` until a persistent NPC is actually established, and do not copy the shop-transaction template into `turn_save.md` until an actual staged shop transaction needs a concrete record.

### File-by-file initial live form

When no additional campaign facts have yet been established, instantiate the templates as follows:

- **`active_game.json`** — copy the full JSON schema from `New-Sheets/active_game.json`; set the campaign identifier and initialization values required below; keep temporary role-key placeholders only until the corresponding PC names are established.
- **`character_sheet.md`** — create the campaign title, character-creation status, `Shared Relationship Canon`, and the two core-PC sections with their state-owning fields and subheadings. Leave undecided character facts blank. Level/XP mirrors must match initialized `active_game.json`. Omit template guidance paragraphs and rule explanations. Role-based core-PC headings may remain until names are established, then rename the headings to the actual PC names while preserving their control-role labels where useful.
- **`NPC-state.md`** — create the campaign title, `Current Party NPCs`, and `Important NPC Index`, each initialized with no established NPCs. Do not copy the full `NPC Record Template`, relationship-field explanation, shop/service template, or other schema examples. Add a concrete persistent NPC record only when that NPC actually becomes persistent.
- **`inventory.md`** — create the campaign title, one section for each required core PC with the live inventory subheadings, and `Current Party NPC Inventories` initialized with none established. Do not copy the sample current-party NPC inventory record, item examples, or instructional rule sections. Rename role-based core-PC headings when actual names are established.
- **`routine_item_prices.md`** — create the campaign title, `Current Routine Item Base Prices`, the empty `Item | Base Price | Notes` table, and `Base Price Change History` initialized with no history. Do not copy pricing instructions or suggested example-history syntax.
- **`world_state.md`** — create the campaign title and the state-owning sections for Important NPCs, Relationships, Locations, Factions / Organizations, Active Quests / Goals, Clues / Discoveries, Known Secrets, World Changes / Consequences, and Unresolved Threads. Initialize each section as empty or not established. Do not copy reference examples or quest-schema guidance into the live file.
- **`session_log.md`** — create the campaign title and `Checkpoints`, initialized with `None yet.`. Do not copy rule-authority or logging-instruction prose. Add entries only for completed saves governed by the session-log rules.
- **`turn_save.md`** — create the campaign title and all live ledger sections: Active Campaign Turn, Turn Events, Current In-Turn State, Pending Shop Transactions, Pending Permanent Transfers, Final Turn Review, Permanent Save Verification, and Reset Approval. Initialize them using the new-campaign values below. Do not copy the Shop Transaction Template or instructional prose into the live ledger. When a shop transaction actually occurs, instantiate one concrete transaction record using the template as the schema.
- **`art/art_log.md`** — instantiate from `New-Sheets/art_log.md` at the live path `art/art_log.md`. Create the campaign title and the reference sections for both core PCs, NPCs, locations, and equipment / important objects, initialized with no references established. Omit rule-authority prose, reference instructions, and other template guidance. Rename role-based core-PC reference headings when actual names are established.

If a template changes later, do not rewrite an existing live campaign file merely to make it resemble the newer template. Apply structural changes to an existing campaign only when the player explicitly requests the migration or when a required rule change makes the migration necessary, and preserve all established campaign state during that migration.

## Revision-0 bootstrap canon

`active_game.json.save_revision: 0` is the campaign's **initialization baseline**. It is not a completed character-creation checkpoint or completed Campaign Turn save.

Revision 0 may nevertheless contain canonical facts that the player explicitly established as part of creating or initializing that campaign before the first formal checkpoint. These are **bootstrap canon**.

Bootstrap canon may include, when explicitly established at initialization:

- the numbered campaign identifier and initial pre-game scene
- the selected advancement mode and required starting advancement defaults
- core-PC names, ages, pronouns, or other identity facts already supplied by the player
- explicitly supplied starting relationship, family, history, or campaign-premise facts
- other campaign facts the player directly establishes as part of the initial campaign premise before checkpointed character creation begins

Bootstrap canon does **not** authorize ChatGPT to invent filler, resolve undecided fields, import another campaign's state, recover facts from chat memory, or treat guesses as canon.

Facts legitimately present in revision 0 are canonical even though no completed save revision exists yet and no `session_log.md` checkpoint is required for them. `session_log.md` may record that the campaign was initialized, but it must not fabricate a revision-1 checkpoint for bootstrap facts.

Revision 0 ends as a special initialization state once the first confirmed persistent character-creation checkpoint completes. After initialization, newly finalized character-creation choices use the checkpoint workflow in `CHARACTER_CREATION.md` and increment `save_revision` normally.

A later player correction to a bootstrap fact is not a reason to rewrite history silently. During ongoing character creation, persist the corrected canonical state through the next appropriate confirmed checkpoint unless the change is merely correcting an initialization transcription error.

## New campaign setup

When creating a new numbered campaign:

1. create a new sibling folder under `campaigns/`
2. instantiate fresh **state-only** campaign files from `New-Sheets/` under the Template instantiation contract above; do not copy another campaign's populated state and do not byte-copy Markdown template guidance into live state
3. create `Rules/Campaign-N_Rules.md` for that numbered campaign; begin with no campaign-specific rules unless the player explicitly establishes some
4. copy `New-Sheets/active_game.json` into the new campaign as `active_game.json` and initialize every field for that campaign:
   - set `campaign` to the numbered campaign folder name
   - keep `campaign_turn_number` at `0`
   - use `Character creation` as `current_scene_name` unless another explicit pre-game scene label has already been established
   - leave `current_location` blank until a location is established
   - keep `character_created` as `false`
   - use the chosen `xp_mode`; use `cumulative` by default unless the player chooses another mode
   - keep both core-PC advancement records at Level 1, 0 XP, and the applicable next-level threshold unless an explicit campaign-specific rule establishes different starting advancement
   - `PLAYER_CONTROLLED_PC_NAME` and `CHATGPT_CONTROLLED_PC_NAME` are template-only key placeholders; replace each with that core PC's actual established name as soon as the name is finalized
   - keep `save_revision` at `0`
   - use a compact initialization `last_sync_note` describing the current pre-game state
5. write any player-established bootstrap canon supplied as part of campaign initialization to its proper state owner while keeping `save_revision` at `0`; leave everything else undecided rather than inventing it
6. initialize the live `turn_save.md` for Campaign Turn 1 with:
   - `Campaign Turn: 1`
   - `Status: ready`
   - `Current Step: 0`
   - `Current Scene: None yet.`
   - `Base save revision: 0`
   - `Turn Events: None yet.`
   - `Current In-Turn State: None yet.`
   - `Pending Shop Transactions: None yet.`
   - `Pending Permanent Transfers: None yet.`
   - Final Turn Review `Status: not_started`, no Final Turn State or planned transfers, and `Player save confirmation: not_requested`
   - Permanent Save Verification `Status: not_started`, no completed save revision, and no verification notes
   - Reset Approval `Status: not_requested` and `Player reset confirmation: not_requested`
7. create both required core PCs under `CORE_PARTY_AND_CHARACTER_AGENCY.md` and `CHARACTER_CREATION.md`
8. keep the new campaign's canon and campaign-specific rules isolated from every existing campaign under `CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`
9. change `campaigns/active_campaign.json` only when the new campaign should become the active campaign

The new campaign begins fresh. Existing characters, NPCs, relationships, items, locations, quests, secrets, story events, campaign-specific rules, and other state are not imported unless the player explicitly requests a permitted import.

## Activating another campaign

Changing the active campaign changes only the selector in `campaigns/active_campaign.json` and its pointer to that campaign's `active_game.json`.

After activation, use the newly active campaign's own `Rules/Campaign-N_Rules.md` and state files. Do not continue applying a prior campaign's local rules merely because they were active in the previous conversation.

Do not move, merge, rewrite, or copy campaign state or campaign-specific rules merely because a different campaign becomes active.
