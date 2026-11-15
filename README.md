# Pure Summoner Trainer

This Legion script trains Magery, Evaluating Intelligence, Mysticism, and Spellweaving toward your selected goal: **Grandmaster (100)** or **Legendary (120)**.

The script uses a 0.5-second check interval and a 2.5-second target timeout. It does not train Focus or Meditation; the Legendary notice reminds you to obtain 120 Power Scrolls for those skills as well.

## Startup

### Safety notice

The first popup says:

> Make sure you are in a safe spot like your house or a non-guard-zone area  
> so area-of-effect damage does not flag you with guards.  
> Reminder: You must have ZERO Necromancy and ZERO Spirit Speak,  
> including skill bonuses from armor or weapons.

This is a reminder. The milestone popups later check Necromancy and Spirit Speak.

### Choose your path

The next popup displays **CHOOSE YOUR PATH** and offers:

- **GrandMaster Pure Summoner (Skill cap 100)**
- **Legendary Pure Summoner (skill cap 120)**

Choose **100** or **120** in the dropdown.

If you choose 120, a notice says:

> In order to get to 120 in all 6 skills, you will need to consume  
> PowerScrolls(120) for Evaluating Intelligence, Focus, Magery, Meditation,  
> Mysticism and Spellweaving.

Click **Continue** to proceed.

## Magery

At **40.0 or below**, the script advises you to train with an NPC in New Haven or another city, then stops the Magery phase. Above 40, it chooses a spell based on your skill:

- Above 40 through 45: **Wall of Stone** — 9 mana
- Above 45 through 55: **Fire Field** — 11 mana
- Above 55 through 65: **Poison Field** — 14 mana
- Above 65 through 75: **Paralyze Field** — 20 mana
- Above 75 through 90: **Energy Field** — 40 mana
- Above 90 through your goal: **Earthquake** — 50 mana

The script preselects you as the target. At **105 Magery**, it displays a one-time popup recommending a mage weapon with **-25 Magery**. Choose **Stop Script** or **Continue**. This threshold applies to the 120 path; the 100 path ends Magery first.

## Evaluating Intelligence

After Magery reaches your goal, if Evaluating Intelligence is below that goal, a popup says:

> Congratulations! You have achieved your Magery goal.  
> Now we need to raise your Evaluating Intelligence.  
> Reactive Armor will be cast repeatedly until the goal is reached.

Click **Begin Reactive Armor** to start.

The script repeatedly casts Reactive Armor. At **4 mana or less**, it displays **“Regenerating mana...”** and waits until mana is full. When the skill reaches the goal, a congratulations popup names you **GrandMaster Mage** or **Legendary Mage**, then says:

> Okay, now let's move on to Mysticism.

## Mysticism

If Mysticism is below **40**, the script advises you to train with a Mystic vendor in Ter Mur, such as the Royal City. Otherwise, it chooses a spell based on your skill:

- 40 through below 63: **Stone Form** — 11 mana
- 63 through below 80: **Cleansing Winds** — 20 mana
- 80 through below 95: **Hail Storm** — 40 mana
- 95 through your goal: **Rising Colossus** — 50 mana

If your health falls below **75%**, the script casts Greater Heal, which requires 11 mana. Rising Colossus targets the tile in front of you, then the script finds and releases the newly summoned Colossus.

When Mysticism reaches your goal, a congratulations popup names you **GrandMaster Mystic** or **Legendary Mystic**.

## Spellweaving Quest

Before Spellweaving training, the script asks whether you completed the quest that unlocks Spellweaving. It describes the five-quest chain and the two paths: **Patience in Heartwood** or **Discipline in Sanctuary**.

- Choose **NO** to see “Please come back when this task is completed.” Click **Close**; the script ends.
- Choose **YES** to continue.

The dropdown defaults to **NO**.

## Spellweaving

Spellweaving training begins at your current skill. The script casts:

- Below 20: **Arcane Circle** — 24 mana
- 20 through below 33: **Immolating Weapon** — 32 mana
- 33 through below 44: **Reaper Form** — 34 mana
- 44 through below 60: **Summon Fey** — 10 mana
- 60 through below 74: **Essence of Wind** — 40 mana
- 74 through below 90: **Wildfire** — 50 mana; targets yourself
- 90 through your goal: **Word of Death** — 50 mana; targets yourself

Before Arcane Circle training, a popup asks you to stand on an **Arcane Circle, Pentagram, or Abattoir**. It is placed above center; click **Continue** when ready.

Before Immolating Weapon training, a popup says:

> Equip any melee weapon before training Immolating Weapon.

Click **Continue** when ready.

During Summon Fey training, the script records nearby mobiles, casts Summon Fey, and looks for newly appeared living mobiles within one tile. It issues **Release** without relying on the Fey’s randomly generated name. If the Release command fails, it retries once and reports a system message if it still cannot find the option.

During casting phases, if your health is below **75%**, the script casts Greater Heal. If mana is below the current spell’s requirement, it displays **“Regenerating mana...”** and waits until mana is full.

Training ends at your selected goal: **100** or **120**.

## Spellweaving Milestones

Each milestone popup appears once when Spellweaving reaches its threshold. If your skill is already above a threshold when Spellweaving training begins, that popup appears then.

The popups display current values for Magery, Evaluating Intelligence, Mysticism, Spellweaving, Meditation, Focus, Necromancy, and Spirit Speak. They mark milestone benefits unavailable when the required thresholds are not met or when Necromancy or Spirit Speak is not exactly zero. These checks inform you; they do not stop the training loop.

### Developing Summoner — Spellweaving 50

The popup lists:

- Rising Colossus drops from 5 follower slots to 3.
- Magery Elementals and Daemon drop from 4 slots to 2.
- Animated Weapon uses Mysticism instead of Tactics and Anatomy for scaling, and uses 4 follower slots.
- Mysticism should already be at your selected goal.

It checks that Mysticism and Spellweaving are at least **50**, and that Necromancy and Spirit Speak are both **0**.

### Grandmaster Summoner — Spellweaving 100

The popup lists:

- Summon Creature drops from 5 slots to 2 at 100+ Mysticism and Spellweaving.
- Animated Weapon drops from 4 slots to 2 and gains Armor Pierce at 100+ Magery, Mysticism, and Spellweaving.
- Flexible 5-slot army combinations, such as a 3-slot Colossus with a 2-slot Summon Creature, Elemental, or Animated Weapon.

It checks that all six base skills are at least **100**, and that Necromancy and Spirit Speak are both **0**.

### Legendary Summoner — Spellweaving 120

The popup lists:

- Greater Elementals and Greater Daemon unlock with upgraded stats and special attacks.
- Elemental Colossus mutations include Physical, Magma, Energy, Frozen, and Poisonous; duration is about 3 minutes.
- Arcane Fey/Fiend groups can summon up to 5 allies per cast, depending on Arcane Focus.
- Ethereal Form grants 8% Hit Mana Drain; Ethereal Burst has a 5-minute cooldown.
- Pocket Colossus stores a spell trigger; Summon Creature lasts about 5 minutes.

It checks that all six base skills are at least **120**, and that Necromancy and Spirit Speak are both **0**.
