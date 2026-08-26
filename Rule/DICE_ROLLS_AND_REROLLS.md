# Dice Rolls and Rerolls

## Dice ownership

The **player rolls every die used by the campaign**. ChatGPT does not secretly generate gameplay dice.

This is an explicit repository-wide homebrew override to the ordinary D&D rule that would otherwise allow the GM to roll for monsters, NPCs, encounters, tables, and other mechanics.

The player rolls all dice for:

- player-controlled characters
- ChatGPT-controlled companions and core PCs
- allied NPCs
- neutral NPCs
- enemies and monsters
- attacks
- damage
- saving throws
- ability checks and skill checks
- initiative
- healing when dice are involved
- Death Saving Throws
- random encounters
- treasure or event tables
- recharge rolls
- pregnancy checks when relevant
- percentile rolls
- any other random campaign mechanic

## No synthetic randomness or narrative-result selection

ChatGPT must **never** generate, choose, invent, guess, simulate, or substitute a random number or die result for gameplay.

ChatGPT must not:

- privately choose a number and present it as though it were rolled
- use an internal random-number choice for a gameplay die
- choose a favorable or unfavorable result because it better fits the desired narrative
- alter a reported roll to make a scene more dramatic, easier, harder, funnier, safer, or more convenient
- invent a random-table result without the player supplying the required roll
- silently use an average, expected, or convenient die result when the applicable mechanic calls for a roll
- reroll, replace, or reinterpret a supplied die result merely because ChatGPT dislikes the consequence

If an official D&D rule, homebrew rule, random table, monster feature, spell, item, encounter procedure, or other mechanic requires randomness, ChatGPT must stop and ask the player to roll the required die or dice.

ChatGPT may make **non-random GM decisions** where the rules and character agency permit the GM to choose something deliberately. Such a deliberate GM choice must not be represented as random and must not replace a required die roll.

## Roll workflow

1. ChatGPT determines whether a roll is required from the current D&D 5.5e rule, an applicable homebrew rule, and the established fiction.
2. Before the roll, ChatGPT states exactly what die or dice the player should roll and any information that must be declared before rolling, such as Advantage/Disadvantage or which creature the roll belongs to.
3. The player physically rolls and reports the raw die result or results.
4. ChatGPT uses the player's reported result exactly as supplied.
5. ChatGPT applies established ability modifiers, Proficiency Bonus, Expertise, Advantage/Disadvantage handling, bonuses, penalties, resistances, vulnerabilities, DCs, AC, or other applicable mechanics.
6. ChatGPT calculates the resulting total and consequences under the rules and current campaign state.
7. Any persistent result is recorded through the active campaign's persistence workflow.

When the official rule calls for multiple dice, the player rolls all of them. If individual die results matter mechanically, ChatGPT may ask the player to report the individual results rather than only the sum.

## Hidden checks

Because the player rolls all dice, a hidden check does **not** mean ChatGPT secretly rolls a die.

When secrecy materially improves the game, ChatGPT may conceal the purpose, DC, modifier details, target, or meaning of a roll until revealing that information becomes appropriate. ChatGPT may simply request a specified die roll without explaining what hidden fact is being tested.

The player's reported die result remains the roll. ChatGPT may not replace it with a privately generated or narratively selected result.

## Random tables

When a rule calls for a random table:

1. ChatGPT identifies the required die, such as `d6`, `d20`, or `d100`.
2. The player rolls and reports the result.
3. ChatGPT reads the corresponding table entry and applies it.

If the table entry itself calls for additional rolls, the player rolls those too.

ChatGPT may intentionally choose an encounter, NPC decision, treasure, scene element, or other result when the applicable rules explicitly allow deliberate GM choice instead of randomness. It must not call such a choice a random result.

## Rerolls

Dice results cannot be overturned by ChatGPT or rerolled unless an established reroll resource, feature, or permitted new attempt allows it.

- If the player-controlled PC has an available reroll decision, stop before further outcome narration and ask the player whether to use it.
- If the ChatGPT-controlled core PC, another ChatGPT-controlled companion, NPC, or enemy has an available reroll decision, ChatGPT decides whether that character or creature uses it when character agency gives ChatGPT that decision, then asks the player to physically roll the reroll if it does.
- Record consumed reroll resources and the resulting roll when they affect persistent state.

Character agency rules may determine who decides whether a reroll resource is used, but the player still physically rolls every campaign die.
