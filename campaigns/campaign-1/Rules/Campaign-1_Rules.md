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

### Cutlor's Veiled Dragonkin and Draconic Awakening

**Scope and authorization:** Campaign 1, Cutlor Ashvale only. The player requested horns, wings, and tail that appear only by choice, a battle transformation with healing, increased damage, HP protection and defense, and delegated the remaining design and a Light/Medium armor selection. The following bounded implementation is GM-designed under that delegation; its exact numerical limits were not separately specified by the player. This is additional campaign homebrew, not an official Barbarian feature, a global species rewrite, a new subclass, or an automatically inherited lineage. It intentionally makes Cutlor stronger than the standard Level-1 package; balance has not been playtested. Future changes require an explicit campaign update.

#### Voluntary manifestation

- Cutlor retains the Dragonkin package except that his horns, wings, and tail can be physically manifested or withdrawn instead of remaining permanently exposed. He does not become another species, gain a monster stat block, or change his Size.
- As a Bonus Action while able to act, he may manifest or withdraw any combination of those features. There is no daily limit or maximum duration for appearance alone. The player decides; damage, anger, flirting, or another character's commands never automatically force a change.
- He may manifest features as part of the same Bonus Action used to enter Rage, without spending another Bonus Action. He may also manifest his wings as part of the Reaction used for Wing-Assisted Descent, provided he is conscious and his wings have space to move. Neither permission gives an extra action or Reaction.
- The last chosen appearance persists until changed by the player; ending Rage or becoming unconscious does not itself force a cosmetic change. Draconic Awakening's benefits have separate ending conditions below.
- Withdrawn features are absent, not merely invisible. Other physical traits, including fine scales and the existing claws, remain. Manifestation does not alter identity, facial features, age, ability scores, current or maximum HP, equipment ownership, conditions, or resource totals.
- Clothing and armor fitted to this anatomy accommodate the manifestation without a damage or repair tax. Equipment stays external and functional; it does not merge, duplicate, disappear, or become extra-dimensional storage. The transformation does not automatically end a grapple or restraint.
- The tail is not an extra hand; horns, wings, and tail grant no independent attacks, reach increase, automatic shield, cover bonus, or movement benefit beyond explicitly recorded traits. Wings may remain folded in confined spaces.
- Wing-Assisted Descent requires manifested, movable wings, using its original falling trigger, Reaction, damage reduction, and horizontal movement. No Fly Speed is granted at Level 1. Mature Flight still first becomes available at character level 5, still costs its own Bonus Action and Long Rest use, and still cannot be used in Medium or Heavy armor. Withdrawing the wings ends that flight; use ordinary falling rules when applicable.

#### Draconic Guard: Light armor compatibility

- While Cutlor wears no armor or wears Light armor, he may use base AC `10 + Dexterity modifier + Constitution modifier` instead of the armor's base-AC calculation. A wielded Shield adds its normal +2 once.
- This explicitly extends his unarmored-style calculation to Light armor in this campaign only. Ordinary Barbarian Unarmored Defense does not normally work while wearing armor.
- Choose a single base-AC formula. Do not add Leather's 11, another armor formula, or the Constitution modifier again on top of this calculation. Ironknuckle Gauntlets still give no AC bonus. Other independently applicable bonuses follow their own rules.
- Draconic Guard works in either visible form and does not require Rage or consume a use. It grants no additional damage resistance. In Medium or Heavy armor, use the normally applicable armor calculation instead; this exception does not apply.
- This is Cutlor's personal trait, not an enchantment on the Leather Armor and not an upgrade transferred to another wearer.

#### Draconic Awakening: empowered battle state

- **Requirement:** Cutlor must be able to act, have at least 1 HP, not be wearing Heavy armor, and be entering or already maintaining his Barbarian Rage. He chooses this state; it never takes control away from the player.
- **Activation:** Spend one Awakening use as part of the Bonus Action used to enter Rage, or use a Bonus Action to awaken during an already active Rage. Manifest horns, wings, and tail as part of that activation. Starting a new Rage still spends its normal Rage use; Awakening does not grant a free Rage or an extra Bonus Action.
- **Uses / recovery:** One use, regained after a Long Rest. A Short Rest may recover Rage under its ordinary rule but does not recover Awakening. Declining to awaken on a Rage preserves the Awakening use.
- **Duration:** Up to 1 minute. Ends earlier if Rage ends, Cutlor becomes Incapacitated or dies, he withdraws any of the three manifested features, or he ends Awakening voluntarily on his turn (no action). Merely folding physical wings does not count as withdrawing them. Normal Rage extension requirements remain in effect; Awakening does not automatically sustain Rage.
- **Restorative surge:** On activation only, regain HP equal to the Constitution modifier (minimum 1), never above the current HP maximum. This heals Cutlor only. At full HP the healing is unused, not stored. It is not recurring regeneration, condition removal, death prevention, or revival from 0 HP.
- **Draconic vigor:** On activation only, gain Temporary HP equal to Proficiency Bonus + Constitution modifier (minimum 1). Normal non-stacking Temporary HP rules apply: choose the existing amount or this new amount. These Temporary HP absorb incoming damage normally and are not healed or refreshed. Any remaining Temporary HP from this Awakening expire when Awakening ends; unrelated replacement Temporary HP do not expire because of this rule. Maximum HP never increases.
- **Empowered strike:** Once on each of Cutlor's own turns, when he hits and deals damage with a Strength-based weapon attack or Unarmed Strike, he may add damage equal to Proficiency Bonus, of the attack's existing damage type. Natural claw, Ironknuckle, and Strength-based Javelin attacks qualify, including thrown Javelins. This bonus is in addition to applicable Rage damage, applies to only one hit on that turn, gives no extra attack, and does not apply on other creatures' turns. It is a flat bonus, so critical hits do not double it.
- **Hardened guard:** +1 AC while Awakening is active. This adds to the single valid base-AC calculation and any valid Shield bonus, not to multiple armor formulas. It supplies no saving throw bonus or general damage reduction.
- **Existing Rage:** Rage's usual damage bonus, Bludgeoning/Piercing/Slashing Resistance, and Strength Advantage continue normally. They are not granted twice. No elemental Resistance, spellcasting, Concentration exemption, extra action, ability-score increase, or automatic attack success is added.
- **Nature and dice:** An innate supernatural feature, not a spell; no Concentration, spell slot, material component, roll, or attunement is required to activate it. All later attack and damage rolls remain player-rolled. No dice result is chosen to award the fixed healing, vigor, or damage bonus.
- **No reset loop:** Withdrawing and remanifesting anatomy never restores HP, Temporary HP, Rage, or Awakening uses. An ended Awakening cannot be resumed without another available use.
- **Progression:** The formulas use current Proficiency Bonus and Constitution modifier. The +1 AC, one-use limit, and one-minute duration do not automatically increase. No additional later-level power is implied.

Current use counters, selected appearance, current HP/Temporary HP, Rage state, and any active start/end clock belong in `../character_sheet.md` or the unfinished-Turn ledger, not in this rule file.

Official baseline references, checked for this implementation: `https://www.dndbeyond.com/sources/dnd/br-2024/character-classes#Barbarian`; `https://www.dndbeyond.com/sources/dnd/br-2024/equipment`; `https://www.dndbeyond.com/sources/dnd/br-2024/rules-glossary#TemporaryHitPoints`. The manifestation, Light-armor compatibility, and Awakening bonuses above are campaign-created exceptions, not claims about those official sources.
