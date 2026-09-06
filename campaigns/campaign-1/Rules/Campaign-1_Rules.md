# Campaign 1 Rules

This file is the canonical persistent rule layer for rules, overrides, exceptional premises, and operating instructions that apply specifically to this numbered campaign.

This campaign inherits the reusable rules under `../../../Rule/`. This file contains only the **campaign-specific delta** from those reusable rules.

Do not duplicate unchanged repository-wide rules here merely for convenience.

Do not store ordinary character, NPC, relationship, inventory, world, quest, shop, session, advancement, art, or other state facts here. Those facts remain in their assigned campaign state files.

When the player explicitly establishes, changes, or rescinds a persistent campaign-specific rule, update this file so future sessions can recover that rule from the repository rather than chat memory.

Rule priority and scope are defined in `../../../Rule/RULE_AUTHORITY_AND_HIERARCHY.md`. Campaign isolation is defined in `../../../Rule/CANON_HISTORY_AND_CAMPAIGN_ISOLATION.md`.

## Initialization guidance

When this skeleton is copied into `campaigns/campaign-1/Rules/`, rename the file to match the actual numbered campaign, for example `Campaign-1_Rules.md`, and replace `Campaign N` in the heading with the actual campaign number.

This guidance is template documentation, not campaign canon.

## Active Campaign-Specific Rules

### Ironknuckle Gauntlets: approved G2 equipment option

Scope: Campaign 1 only. The player approved this homebrew weapon option by selecting loadout B, Foxguard. This does not approve the alternative Clawguard Wraps or Ridgeback Gauntlets, or change the global equipment catalog.

- **Category:** Nonmagical Simple Melee weapon, worn as an open-finger pair. Gauntlet strikes are weapon attacks, not Unarmed Strikes.
- **Construction:** Fingerless leather with steel knuckle bars and short wrist plates; fingers and natural claws remain accessible.
- **Listed starting price / weight:** 15 GP per pair; 2 lb. per pair. Actual ownership and acquisition payments belong in `../inventory.md`; this is not a recurring routine-price entry.
- **Attack ability / proficiency:** Strength for attack and damage rolls. Simple-weapon proficiency applies normally.
- **Reach / damage:** 5 feet; 1d6 Bludgeoning plus Strength modifier on a normal hit. Applicable Strength-based Rage damage may be added normally. No automatic scaling, special critical rule, attack bonus, or additional damage die.
- **Weapon properties:** None. In particular, not Light, Finesse, Thrown, Reach, or Two-Handed.
- **Mastery property:** Sap. A character must select Ironknuckle Gauntlets through a feature that grants the applicable Weapon Mastery before using Sap. When enabled, hitting a creature with a gauntlet gives it Disadvantage on its next attack roll before the start of the wielder's next turn. No additional action, charge, or saving throw; ordinary Advantage/Disadvantage rules apply.
- **Hands:** Strike with a gauntleted hand that is not holding another weapon, shield, object, or a grapple. A shield occupies its hand; the other hand may strike. Wearing the gauntlets does not otherwise prevent grasping, manipulating objects, or using the exposed natural claws.
- **Claw interaction:** Choose either the natural claw attack or the gauntlet attack for each attack. Do not combine their damage dice or types. Sap from this weapon does not apply to claw attacks.
- **Action economy:** Use a normal available weapon attack. The pair grants no additional attack, Bonus Action attack, Reaction, or two-weapon/Light-property benefit.
- **Armor interaction:** These weapons are neither armor nor shields and grant no AC, damage resistance, or protection bonus. They do not disable Unarmored Defense or count as Medium/Heavy armor for Dragonkin flight restrictions.
- **Donning / doffing:** 1 minute to put on or remove the pair. This is equipment handling time, not elapsed setup time.
- **Resources:** No charges, recharge, attunement, magical effect, hidden property, or automatic condition immunity.

Selecting or acquiring this weapon does not also select its mastery. Record character-specific mastery choices in `../character_sheet.md`.

Official Sap reference: `https://www.dndbeyond.com/sources/dnd/br-2024/equipment#Sap`. All other ordinary weapon rules continue to use the repository baseline.
