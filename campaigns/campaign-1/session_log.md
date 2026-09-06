# Session Log

## Rule Authority

Chronological logging is governed by `../../Rule/SESSION_LOG_AND_HISTORY.md`. Campaign time is governed by `../../Rule/CORE_GAME_MECHANICS.md`. Append-first preservation and corrections are governed by `../../Rule/STATE_OWNERSHIP_AND_PERSISTENCE.md`.

This file stores completed chronological history. The labeled templates below are guidance, not completed checkpoints.

## Checkpoints

Do not add intermediate character-creation checkpoints during `save_revision: 0`.

### Character Creation Completion Entry Template

- **Type:** Character creation complete / Campaign Turn 1 starting baseline
- **Save revision:** 1
- **Campaign Turn:** Not started; `campaign_turn_number` remains 0
- **Opening clock:**
- **Opening scene / location:**
- **Core PCs:**
- **Starting relationship / family continuity:**
- **Starting equipment / resources:**
- **Starting world facts:**
- **Summary / notes:**

Record only finalized facts needed to understand the baseline.

### Completed Campaign Turn Entry Template

- **Type:** Completed Campaign Turn

- **Save revision:**
- **Campaign Turn:**
- **Start clock:**
- **End clock:**
- **Elapsed time:**
- **Ending scene / location:**
- **Continuity-critical events:**
- **Important rolls / outcomes:**
- **Character / relationship / reproductive changes:**
- **NPC / party / family changes:**
- **Inventory / resource / transaction changes:**
- **Quest / clue / world changes:**
- **Scheduled events or deadlines reached:**
- **XP / advancement changes:**
- **Other lasting consequences:**

Use only fields that matter. Preserve enough chronology to explain later state without copying the entire Turn ledger.

Do not delete these labeled templates merely because real entries are added unless the player explicitly requests that the campaign copy be simplified.

### Revision 1: Character Creation Complete; Play Not Started

- **Type:** Character creation complete / Campaign Turn 1 starting baseline
- **Save revision:** 1
- **Player approval:** "yes but not starting yet" in response to the final two-character creation review and baseline confirmation
- **Campaign Turn:** Not started; `active_game.json.campaign_turn_number` remains 0. `turn_save.md` is ready for Campaign Turn 1, Step 0, base save revision 1.
- **Opening clock:** Campaign Day 1, 08:00:00; unchanged from initialization, with 0 elapsed gameplay seconds
- **Opening scene / location:** Morning at Briarbridge / Briarbridge, east market square. Static GM frame is saved in `world_state.md`; opening narration is withheld until the player starts play.
- **Core PCs:** Cutlor Ashvale, 18-year-old male Dragonkin Barbarian 1 / Soldier, Neutral Good; Seren Ashvale, 18-year-old female Kitsune Bard 1 / Wayfarer, Chaotic Good. Both speak Common, Draconic, and Elvish; both have 0 cumulative XP and next level at 300 XP.
- **Starting relationship / family continuity:** Married core protagonists, friends since age 3, with the established linked backgrounds and present adult relationship unchanged. No children or new family event established. Optional unestablished personal details remain undecided.
- **Cutlor baseline:** Scores 18/16/18/11/15/12; HP 16/16, Temporary HP 0, AC 19 with shield, initiative +3, passive Perception 14. Rage 2/2 and Draconic Awakening 1/1, both inactive. Horns, wings, and tail withdrawn. Ironknuckle Gauntlets / Sap and Javelins / Slow remain selected. Personal manifestation, Draconic Guard, and Awakening use the existing Campaign-1 rules without activation or change.
- **Seren baseline:** Scores 12/17/16/13/14/20; HP 11/11, Temporary HP 0, leather AC 14, initiative +3, passive Perception 14, spell save DC 15, spell attack +7. Bardic Inspiration 5/5 d6, first-level spell slots 2/2, Luck Points 2/2, Fox Step 2/2; all unspent. Spells, appearance, and other established features unchanged.
- **Starting equipment / resources:** Existing `inventory.md` is preserved without another acquisition or deduction. Cutlor has the Foxguard loadout plus fitted Leather Armor, 20 GP 4 SP, one unused Potion of Healing, a full 10-use Healer's Kit, four Javelins, and unspent travel supplies. Seren keeps her established Bard/Wayfarer equipment and 35 GP. No currency or possession transfer occurs.
- **Starting world facts:** Riverside market-square opening, immediate public noticeboard hook, unnamed adult background vendors and porter, and a cart with a damaged wheel as visible scene setup. No quest accepted, persistent NPC introduced, deadline scheduled, check rolled, or encounter resolved. No hidden solution is recorded.
- **Summary / notes:** This is the sole completed character-creation checkpoint, not a completed Campaign Turn. Character creation is approved and `character_created` is true. The player's hold is explicit: do not narrate the opening, set the Turn in progress, create Step 1, roll, or advance time until the player asks to begin play.
