# Pure Summoner Trainer

This script trains the six skills in the Pure Summoner template. It uses two timing constants throughout:

- `CHECK_INTERVAL` controls how often the script checks conditions.
- `TARGET_TIMEOUT` controls how long it waits for a target cursor.

The training goal is selected when the script starts: **Grandmaster (100)** or **Legendary (120)**.

## Mana and Healing

Each training spell has its own minimum mana requirement. If mana is below the current spell’s requirement, the script waits until mana is full before continuing.

The script casts Greater Heal when health falls below 75% during the Mysticism phase and during the Summon Fey and Word of Death Spellweaving phases. Healing is not checked during every phase.

## Startup

When the script starts, it displays a safety notice:

> Make sure you are in a safe spot like your house or a non-guard-zone area so area-of-effect damage does not flag you with guards.
>
> You must have ZERO Necromancy and ZERO Spirit Speak, including skill bonuses from armor or weapons.

Then choose a path:

- **Grandmaster:** train to 100
- **Legendary:** train to 120

Choosing Legendary displays a Power Scroll notice. You will need 120 Power Scrolls for Evaluating Intelligence, Focus, Magery, Meditation, Mysticism, and Spellweaving.

## Magery

If Magery is **40.0 or lower**, the script tells you to train with an NPC. At skill above 40, it selects a spell based on your current skill:

| Magery skill | Spell |
|---|---|
| Above 40 through 45 | Wall of Stone |
| Above 45 through 55 | Fire Field |
| Above 55 through 65 | Poison Field |
| Above 65 through 75 | Paralyze Field |
| Above 75 through 90 | Energy Field |
| Above 90 through your selected goal | Earthquake |

At the selected goal, the script moves on to Evaluating Intelligence.

## Evaluating Intelligence

If Evaluating Intelligence is below your selected goal, the script repeatedly casts Reactive Armor until it reaches the goal. When mana drops below 4, the script waits for mana to refill.

After the goal is reached, a congratulations popup appears and the script moves on to Mysticism.

## Mysticism

If Mysticism is below 40, the script advises you to train with a Mystic vendor in Ter Mur, such as the Royal City. Otherwise, it selects a spell based on your current skill:

| Mysticism skill | Spell |
|---|---|
| 40 through below 63 | Stone Form |
| 63 through below 80 | Cleansing Winds |
| 80 through below 95 | Hail Storm |
| 95 through your selected goal | Rising Colossus |

The script checks your health during this phase and casts Greater Heal below 75%. Rising Colossus is targeted at the tile in front of you, then released.

At the selected goal, a congratulations popup appears.

## Spellweaving Quest

Before Spellweaving training, the script asks whether you completed the quest that unlocks Spellweaving.

- Choosing **No** displays a reminder to complete the quest, then ends the script.
- Choosing **Yes** continues to Spellweaving training.

Spellweaving has no NPC trainer, so scripted training begins at 0.

## Spellweaving

The script trains with these spells:

| Spellweaving skill | Spell |
|---|---|
| 0 through below 20 | Arcane Circle |
| 20 through below 33 | Immolating Weapon |
| 33 through below 44 | Reaper Form |
| 44 through below 60 | Summon Fey |
| 60 through below 74 | Essence of Wind |
| 74 through below 90 | Wildfire |
| 90 through your selected goal | Word of Death |

Before Arcane Circle training, a popup reminds you to stand on an Arcane Circle, Pentagram, or Abattoir. Before Immolating Weapon training, a popup reminds you to equip a melee weapon.

During Summon Fey training, the script casts the spell, attempts to release the summoned Fey, and casts Greater Heal if your health is below 75%. During Word of Death training, it casts Greater Heal below 75% as needed.

Training ends at your selected goal: 100 for Grandmaster or 120 for Legendary.

## Spellweaving Milestones

The script displays each milestone popup once when your Spellweaving skill reaches its threshold.

### Developing Summoner — Spellweaving 50

- Rising Colossus drops from 5 follower slots to 3.
- Magery Elementals and Daemon drop from 4 slots to 2.
- Animated Weapon uses Mysticism instead of Tactics and Anatomy for scaling, and uses 4 follower slots.
- Mysticism should already be at your selected goal.

### Grandmaster Summoner — Spellweaving 100

- Summon Creature drops from 5 slots to 2 at 100+ Mysticism and Spellweaving.
- Animated Weapon drops from 4 slots to 2 and gains Armor Pierce at 100+ Magery, Mysticism, and Spellweaving.
- Unlocks flexible 5-slot army combinations, such as a 3-slot Colossus and a 2-slot Summon Creature, Elemental, or Animated Weapon.

### Legendary Summoner — Spellweaving 120

- Greater Elementals and Greater Daemon unlock with upgraded stats and special attacks.
- Elemental Colossus mutations include Physical, Magma, Energy, Frozen, and Poisonous; duration is about 3 minutes.
- Arcane Fey/Fiend groups can summon up to 5 allies per cast, depending on Arcane Focus.
- Ethereal Form grants 8% Hit Mana Drain; Ethereal Burst has a 5-minute cooldown.
- Pocket Colossus stores a spell trigger; Summon Creature lasts about 5 minutes.

All three milestone popups check Necromancy and Spirit Speak. Both skills must be **exactly 0** to benefit from the milestone unlocks. If either skill is above 0, the popup warns that you cannot benefit until both are zero.
