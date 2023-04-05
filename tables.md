# Data Tables

## Alien Health

First, compute the mission difficulty:

| Skill Level     | Easy | Normal | Hard | Insane | Brutal |
| --------------- | ---- | ------ | ---- | ------ | ------ |
| Base Difficulty | 3    | 5      | 7    | 10     | 13     |

If `rd_difficulty_tier` is active, add 12 times its value to the mission difficulty.

If the campaign has a `DifficultyModifier` entry for this mission, add its value to the mission difficulty.

Next, add a modifier based on the number of marines present in the mission. If `asw_adjust_difficulty_by_number_of_marines` is set, the modifiers for marine counts below 4 are applied. If `rd_increase_difficulty_by_number_of_marines` is set, the modifiers for marine counts above 4 are applied. Most ASBI-based modes have the latter set, and most other modes have the former set.

| Marine Count | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |
| ------------ | --- | --- | --- | --- | --- | --- | --- | --- |
| Modifier     | \-2 | \-2 | \-1 | \+0 | \+1 | \+2 | \+3 | \+4 |

The mission difficulty has a minimum value of 2. If it would be below 2, it is increased to 2.

Alien health is increased or decreased by 20% for each point of mission difficulty above or below 5 (normal).

| <abbr title="Mission Difficulty">MD</abbr> | <abbr title="Easy">3</abbr> | <abbr title="Normal">5</abbr> | <abbr title="Hard">7</abbr> | <abbr title="Insane">10</abbr> | <abbr title="Brutal">13</abbr> |
| ------------- | ----- | ----- | ----- | ----- | ----- |
| **Allies**    |       |       |       |       |       |
| Marine\*      | 80†   | 80†   | 80†   | 80†   | 80†   |
| Colonist\*    | 40    | 40    | 40    | 40    | 40    |
| **The Swarm** |       |       |       |       |       |
| Drone         | 25    | 40    | 56    | 80    | 104   |
| (Uber)        | 300   | 500   | 700   | 1000  | 1300  |
| Ranger        | 60    | 101   | 141   | 202   | 262   |
| Shieldbug     | 600   | 500   | 1400  | 2000  | 2600  |
| Buzzer        | 18    | 30    | 42    | 60    | 78    |
| Boomer        | 480   | 800   | 1120  | 1600  | 2080  |
| Parasite      | 15    | 25    | 35    | 50    | 65    |
| Harvester     | 120   | 200   | 280   | 400   | 520   |
| Xenomite      | 6     | 10    | 14    | 20    | 26    |
| Mortarbug     | 210   | 350   | 490   | 700   | 910   |
| Mender        | 35    | 59    | 82    | 118   | 153   |
| Grub\*        | 1     | 1     | 1     | 1     | 1     |
| Queen         | 2100  | 3500  | 4900  | 7000  | 9100  |
| **Zombies**   |       |       |       |       |       |
| Classic       | 30    | 50    | 70    | 100   | 130   |
| Fast          | 30    | 50    | 70    | 100   | 130   |
| Poison        | 105   | 175   | 245   | 350   | 455   |
| Zombine       | 60    | 100   | 140   | 200   | 260   |
| **Headcrabs** |       |       |       |       |       |
| Classic       | 6     | 10    | 14    | 20    | 26    |
| Fast          | 6     | 10    | 14    | 20    | 26    |
| Poison        | 21    | 35    | 49    | 70    | 91    |
| **Antlions**  |       |       |       |       |       |
| Classic       | 14    | 24    | 33    | 48    | 62    |
| Worker        | 14    | 24    | 33    | 48    | 62    |
| Guard         | 300   | 500   | 700   | 1000  | 1300  |
| Guardian      | 300   | 500   | 700   | 1000  | 1300  |
| **Combine**   |       |       |       |       |       |
| SMG           | 30    | 50    | 70    | 100   | 130   |
| Shotgun       | 30    | 50    | 70    | 100   | 130   |
| Elite (AR2)   | 42    | 70    | 98    | 140   | 182   |
| Hunter        | 126   | 210   | 294   | 420   | 546   |
| Strider       | 210   | 350   | 490   | 700   | 910   |

\*Some creature types do not have health scaling and use the same max HP regardless of difficulty.  
†Marines gain max HP for each point in the Health skill.  

## Enemy Damage

Similarly to health, alien damage increases or decreases by 20% for each mission difficulty above or below Normal. In Source Engine, fractional damage carries over and there is no rounding. All attacks deal a minimum of 1 damage before calculating any resistance for the victim. 

| Attack        | Damage (Normal) |
| ------------- | ----- |
| **The Swarm** |       |
| Drone (slash) | 15    |
| Drone (blocked while climbing) | 20    |
| Ranger (spit) | 6     |
| Shieldbug (stomp) | 25    |
| Buzzer (sting) | 15 (max 30) |
| Boomer (kick) | 4-6   |
| Boomer (explosion) | 55 (does not scale) |
| Parasite | (infest damage is special) |
| Harvester (skin) | 5 (does not scale) |
| Xenomite (burst) | 15    |
| Mortarbug (skin) | 5 (does not scale) |
| Mortarbug (explosion) | 50 (does not scale) |
| Mender | (does not attack; healing does 4% of max per second) |
| Queen (tentacles) | 1     |
| Queen (slash) | 5     |
| Queen (spit) | 10    |
| **Zombies**   |       |
| All (swipe) | 10    |
| Poison (swipe) | 20    |
| Zombine (grenade) | 200   |
| **Headcrabs** |       |
| All (leap) | 5     |
| Poison (poison) | takes marines down to 1 HP; 20 to other targets |
| **Antlions**  |       |
| Classic (kick) | 10    |
| Classic (leap) | 10    |
| Worker (kick) | 10    |
| Worker (leap) | 10    |
| Guard/Guardian (shove) | 10    |
| Guard/Guardian (charge) | 20    |
| Guardian (poison) | takes marines down to 12 HP; disabled by default |
| **Combine**   |       |
| Soldier (SMG) | 3 (per bullet) |
| Soldier (Shotgun) | 3 (per pellet) |
| Soldier (shove) | 10    |
| Elite (AR2)   | 5 (per pulse) |
| Elite (shove) | 15    |
| Hunter (kick) | 20    |
| Hunter (charge, if marine) | 20    |
| Hunter (charge, unless marine) | 250   |

## Commander Experience Points

| Level | Experience from Previous | Total Experience | Unlocked Weapons                |
|-------|--------------------------|------------------|---------------------------------|
| 1     | *N/A*                    | 0                | Starting Weapons\*              |
| 2     | 1000                     | 1000             | L3A Tactical Heavy Armor        |
| 3     | 1050                     | 2050             | Model 35 Pump-action Shotgun    |
| 4     | 1100                     | 3150             | X-33 Damage Amplifier            |
| 5     | 1150                     | 4300             | IAF Tesla Cannon                |
| 6     | 1200                     | 5500             | Hornet Barrage                  |
| 7     | 1250                     | 6750             | Precision Rail Rifle            |
| 8     | 1300                     | 8050             | CR-18 Freeze Grenades                 |
| 9     | 1350                     | 9400             | IAF Medical Gun                 |
| 10    | 1400                     | 10800            | Adrenaline                      |
| 11    | 1450                     | 12250            | K80 Personal Defense Weapon     |
| 12    | 1500                     | 13750            | IAF Tesla Sentry Coil           |
| 13    | 1550                     | 15300            | M868 Flamer Unit                |
| 14    | 1600                     | 16900            | v45 Electric Charged Armor      |
| 15    | 1650                     | 18550            | IAF Freeze Sentry Gun           |
| 16    | 1700                     | 20250            | M478 Proximity Incendiary Mines |
| 17    | 1750                     | 22000            | IAF Minigun                     |
| 18    | 1800                     | 23800            | Flashlight Attachment           |
| 19    | 1850                     | 25650            | AVK-36 Marksman Rifle           |
| 20    | 1900                     | 27550            | IAF Power Fist Attachment       |
| 21    | 1950                     | 29500            | IAF Incendiary Sentry Gun       |
| 22    | 2000                     | 31500            | FG-01 Hand Grenades                   |
| 23    | 2050                     | 33550            | Chainsaw                        |
| 24    | 2100                     | 35650            | MNV34 Nightvision Goggles       |
| 25    | 2150                     | 37800            | IAF High Velocity Sentry Cannon |
| 26    | 2200                     | 40000            | MTD6 Smart Bomb                 |
| 27    | 2250                     | 42250            | Grenade Launcher                |
| 28    | 2300                     | 44550            | PS50 Bulldog                    |
| 29    | 2350                     | 46900            | IAF HAS42 Devastator            |
| 30    | 2400                     | 49300            | 22A4-2 Combat Rifle             |
| 31    | 2450                     | 51750            | IAF Medical Amplifier Gun       |
| 32    | 2500                     | 54250            | TG-05 Gas Grenades              |
| 33    | 2550                     | 56800            | 22A5 Heavy Assault Rifle        |
| 34    | 2600                     | 59400            | IAF Medical SMG                 |

\* Starting Weapons are:

- 22A3-1 Assault Rifle
- 22A7-Z Prototype Assault Rifle
- S23A SynTek Autogun
- M42 Vindicator
- M73 Twin Pistols
- IAF Advanced Sentry Gun
- IAF Heal Beacon
- IAF Ammo Satchel
- IAF Personal Healing Kit
- Hand Welder
- SM75 Combat Flares
- ML30 Laser Trip Mine

| Promotion | Name              | Experience Requirement Multiplier | Total Experience to Max |
|-----------|-------------------|-----------------------------------|-------------------------|
| 0         | *N/A*             | 1x                                | 59400                   |
| 1         | Titanium Star     | 1x                                | 118800                  |
| 2         | Carbide Star      | 1x                                | 178200                  |
| 3         | Gallium Cross     | 1x                                | 237600                  |
| 4         | Platinum Star     | 2x                                | 356400                  |
| 5         | Osmium Star       | 4x                                | 594000                  |
| 6         | Iridium Medallion | 6x                                | 950400                  |
| 7         | Golden Medallion  | 8x                                | 1425600                 |
