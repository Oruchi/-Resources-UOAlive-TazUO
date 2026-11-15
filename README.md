Pure Summoner Trainer — Script Overview
The script trains Magery, Evaluating Intelligence, Mysticism, and Spellweaving toward the goal you select: 100 (Grandmaster) or 120 (Legendary). It does not train Focus or Meditation; the Legendary startup popup reminds you that you need 120 Power Scrolls for those skills as well as the four trained by the script.

The script uses a 0.5-second check interval and a 2.5-second target timeout.
Startup and Path Selection
Safety popup
When the script starts, it displays this reminder:
Make sure you are in a safe spot like your house or a non-guard-zone area
so area-of-effect damage does not flag you with guards.
Reminder: You must have ZERO Necromancy and ZERO Spirit Speak,
including skill bonuses from armor or weapons.

This popup is a reminder. The script checks Necromancy and Spirit Speak later in the milestone popups.
Choose your path
The next popup displays CHOOSE YOUR PATH, with:
- GrandMaster Pure Summoner (Skill cap 100)
- Legendary Pure Summoner (skill cap 120)
The dropdown offers 100 and 120.
Power Scroll popup
If you choose 120, a popup says:
In order to get to 120 in all 6 skills, you will need to consume
PowerScrolls(120) for Evaluating Intelligence, Focus, Magery, Meditation,
Mysticism and Spellweaving.

Click Continue to proceed.
Magery
The script checks Magery first. At 40.0 or below, it displays a system message advising you to train with an NPC in New Haven or another city, then stops the Magery phase. Above 40, it chooses a spell based on your current skill:
Magery skill	Spell
Above 40 through 45	Wall of Stone
Above 45 through 55	Fire Field
Above 55 through 65	Poison Field
Above 65 through 75	Paralyze Field
Above 75 through 90	Energy Field
Above 90 through your selected goal	Earthquake


It preselects you as the target for the Magery spell. If a spell needs a target cursor, it waits up to 2.5 seconds and targets you.

At 105 Magery, the script displays a one-time popup:
You have reached a threshold where skill gain has slowed down.
We recommend equipping a mage weapon with a -25 to Magery.
Do you wish to stop the script or continue as it is?

Choose Stop Script to end the Magery phase, or Continue to keep training. This threshold is relevant to the 120 path; the 100 path ends Magery before 105.
Evaluating Intelligence
After Magery reaches the selected goal, the script checks Evaluating Intelligence. If it is below the goal, it displays:
Congratulations! You have achieved your Magery goal.
Now we need to raise your Evaluating Intelligence.
Reactive Armor will be cast repeatedly until the goal is reached.

Click Begin Reactive Armor to start.

Reactive Armor is cast until Evaluating Intelligence reaches the goal. At 4 mana or less, the script displays “Regenerating mana...” and waits until mana is full. When Evaluating Intelligence reaches the goal, the script displays a congratulations popup naming you GrandMaster Mage or Legendary Mage, followed by “Okay, now let’s move on to Mysticism.”
Mysticism
If Mysticism is below 40, the script sends a system message advising you to train with a Mystic vendor in Ter Mur, such as the Royal City. Otherwise, it chooses a spell based on current Mysticism:
Mysticism skill	Spell
40 through below 63	Stone Form
63 through below 80	Cleansing Winds
80 through below 95	Hail Storm
95 through your selected goal	Rising Colossus


If your health is below 75%, the script casts Greater Heal before continuing. If mana is below the current spell’s requirement, it displays “Regenerating mana...” and waits until mana is full.

For Rising Colossus, the script targets the tile in front of you, waits briefly, finds the newly appearing Rising Colossus, and sends it the Release context-menu command.

At the selected Mysticism goal, the script displays a congratulations popup naming you GrandMaster Mystic or Legendary Mystic.
Spellweaving Quest Check
Before Spellweaving training, the script asks whether you completed the quest that unlocks Spellweaving. The popup describes the five-quest chain and the two paths: Patience in Heartwood or Discipline in Sanctuary. The dropdown defaults to NO.
- If you choose NO, the script displays “Please come back when this task is completed.” Click Close; the script ends.
- If you choose YES, the script continues to Spellweaving.
Spellweaving
Spellweaving training begins at your current skill. The script uses these skill bands:
Spellweaving skill	Spell
Below 20	Arcane Circle
20 through below 33	Immolating Weapon
33 through below 44	Reaper Form
44 through below 60	Summon Fey
60 through below 74	Essence of Wind
74 through below 90	Wildfire
90 through your selected goal	Word of Death


Before Arcane Circle training, a popup asks you to stand on an Arcane Circle, Pentagram, or Abattoir. It is positioned above center so it is less likely to block your view. Click Continue when ready.

Before Immolating Weapon training, a popup says:
Equip any melee weapon before training Immolating Weapon.

Click Continue when ready.

For Summon Fey, the script records the nearby mobiles, casts the spell, then looks for newly appeared living mobiles within one tile. It sends each a Release command without relying on the creature’s randomly generated name. If the command does not succeed, it retries once and sends a system message if it still cannot find the Release option.

Wildfire and Word of Death are targeted on yourself. The script casts Greater Heal whenever health falls below 75%, including during Spellweaving training. Each spell phase checks its own mana requirement; when mana is too low, the script displays “Regenerating mana...” until mana is full.

Training ends at the selected goal: 100 or 120.
Spellweaving Milestone Popups
Each milestone popup appears once when Spellweaving reaches its threshold. If your skill is already above a threshold when Spellweaving begins, the corresponding popup appears then.

The popups show the current values for the six base skills—Magery, Evaluating Intelligence, Mysticism, Spellweaving, Meditation, and Focus—and the current Necromancy and Spirit Speak values. They mark the listed benefits unavailable if the required skills do not meet the threshold or if either Necromancy or Spirit Speak is not exactly zero. This status is informational; it does not stop the training loop.
Developing Summoner — Spellweaving 50
The popup lists:
- Rising Colossus drops from 5 follower slots to 3.
- Magery Elementals and Daemon drop from 4 slots to 2.
- Animated Weapon uses Mysticism instead of Tactics and Anatomy for scaling, and uses 4 follower slots.
- Mysticism should already be at your selected goal.
It checks that Mysticism and Spellweaving are at least 50, and that Necromancy and Spirit Speak are both 0.
Grandmaster Summoner — Spellweaving 100
The popup lists:
- Summon Creature drops from 5 slots to 2 at 100+ Mysticism and Spellweaving.
- Animated Weapon drops from 4 slots to 2 and gains Armor Pierce at 100+ Magery, Mysticism, and Spellweaving.
- Flexible 5-slot army combinations, such as a 3-slot Colossus with a 2-slot Summon Creature, Elemental, or Animated Weapon.
It checks that all six base skills are at least 100, and that Necromancy and Spirit Speak are both 0.
Legendary Summoner — Spellweaving 120
The popup lists:
- Greater Elementals and Greater Daemon unlock with upgraded stats and special attacks.
- Elemental Colossus mutations include Physical, Magma, Energy, Frozen, and Poisonous; duration is about 3 minutes.
- Arcane Fey/Fiend groups can summon up to 5 allies per cast, depending on Arcane Focus.
- Ethereal Form grants 8% Hit Mana Drain; Ethereal Burst has a 5-minute cooldown.
- Pocket Colossus stores a spell trigger; Summon Creature lasts about 5 minutes.
It checks that all six base skills are at least 120, and that Necromancy and Spirit Speak are both 0.
