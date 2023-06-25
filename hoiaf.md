# Heroes of the Interstellar Armed Forces Scoring Changelog

## April 20, 2022 (Season 1)

- Seasons last 3 months (March-April-May, June-July-August, September-October-November, December-January-February).
- First season begins April 20, 2022.
- Initial scoring algorithm is as follows:
   1. `sv_cheats` disallowed as is standard.
   1. Failing a mission records stats but does not update score.
   1. Remaining steps in algorithm do not run for failed mission attempts.
   1. Look up current challenge multiplier and ruleset. (Unrated challenges have a multiplier of 0.)
   1. Set score to base score for ruleset and difficulty setting.
   1. If the difficulty is at least Hard, at least 2 marines survived, and hardcore friendly fire is enabled, add Alive Bonus points for each surviving marine in the squad.
   1. If Onslaught is disabled, subtract 2 points.
   1. If the current score is at least 2, multiply by the mission multiplier. (Unrated missions have a multiplier of 0.01.)
   1. Multiply by the challenge multiplier.
   1. If the previous mission completion was during the current season and within the past 7200 seconds (two hours):
      1. Search circular buffer of past 6 completed missions for current mission.
      1. If the current mission appears, multiply score by 0.25.
   1. If the circular buffer was not checked in the previous step, clear the circular buffer.
   1. Add the current mission to the circular buffer.
   1. If the current score is less than 1, the current score is set to 1.
   1. Add the current score to the player's total for this season.
- Initial difficulty config defined:
   | Ruleset | Easy | Normal | Hard | Insane | Brutal | Alive Bonus |
   | - | - | - | - | - | - | - |
   | Standard | 1 | 1 | 5 | 10 | 15 | 1 |
   | ASBI | 1 | 1 | 20 | 50 | 80 | 4 |
- Initial mission ratings defined:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | Jacob's Rest | Landing Bay | 1.4 | New |
   | Jacob's Rest | Cargo Elevator | 1.5 | New |
   | Jacob's Rest | Deima Surface Bridge | 1.1 | New |
   | Jacob's Rest | Rydberg Reactor | 1.5 | New |
   | Jacob's Rest | SynTek Residential | 2.0 | New |
   | Jacob's Rest | Sewer Junction B5 | 1.25 | New |
   | Jacob's Rest | Timor Station | 2.0 | New |
   | Area 9800 | Landing Zone | 2.0 | New |
   | Area 9800 | Power Plant's Cooling Pump | 2.25 | New |
   | Area 9800 | Power Plant's Generator | 2.0 | New |
   | Area 9800 | Wastelands | 2.0 | New |
   | Lana's Escape | Lana's Bridge | 2.5 | New |
   | Lana's Escape | Lana's Sewer | 2.5 | New |
   | Lana's Escape | Lana's Maintenance | 2.0 | New |
   | Lana's Escape | Lana's Vents | 2.0 | New |
   | Lana's Escape | Lana's Complex | 1.8 | New |
   | Operation Cleansweep | Storage Facility | 0.9 | New |
   | Operation Cleansweep | Landing Bay 7 | 1.5 | New |
   | Operation Cleansweep | U.S.C. Medusa | 1.4 | New |
   | Paranoia | Unexpected Encounter | 1.4 | New |
   | Paranoia | Hostile Places | 1.4 | New |
   | Paranoia | Close Contact | 2.1 | New |
   | Paranoia | High Tension | 3.0 | New |
   | Paranoia | Crucial Point | 1.75 | New |
   | Research 7 | Transport Facility | 1.5 | New |
   | Research 7 | Research 7 | 1.5 | New |
   | Research 7 | Illyn Forest | 2.0 | New |
   | Research 7 | Jericho Mines | 2.0 | New |
   | Tears for Tarnor | Insertion Point | 3.0 | New |
   | Tears for Tarnor | Abandoned Maintenance Tunnels | 1.75 | New |
   | Tears for Tarnor | Oasis Colony Spaceport | 2.75 | New |
   | Tilarus-5 | Midnight Port | 2.25 | New |
   | Tilarus-5 | Road to Dawn | 2.5 | New |
   | Tilarus-5 | Arctic Infiltration | 2.25 | New |
   | Tilarus-5 | Area 9800 | 2.5 | New |
   | Tilarus-5 | Cold Catwalks | 2.25 | New |
   | Tilarus-5 | Yanaurus Mine | 2.5 | New |
   | Tilarus-5 | Forgotten Factory | 2.75 | New |
   | Tilarus-5 | Communication Center | 2.75 | New |
   | Tilarus-5 | SynTek Hospital | 2.75 | New |
   | BioGen Corporation | Operation X5 | 2.0 | New |
   | BioGen Corporation | Invisible Threat | 1.75 | New |
   | BioGen Corporation | BioGen Labs | 2.75 | New |
   | Nam Humanum | Logistics Area | 1.4 | New |
   | Nam Humanum | Platform XVII | 1.75 | New |
   | Nam Humanum | Groundwork Labs | 2.5 | New |
   | *Bonus Mission* | Space Port Catastrophe | 1.75 | New |
   | *Bonus Mission* | Rapture | 1.75 | New |
   | *Bonus Mission* | Bunker | 2.5 | New |
   | *Bonus Mission* | Landing Bay + Cargo Elevator | 3.0 | New |
   | *Bonus Mission* | Hostile Places + Close Contact | 3.25 | New |
   | *Bonus Mission* | High Tension + Crucial Point | 3.75 | New |
   | *Bonus Mission* | Power Plant | 3.75 | New |
   | [Adanaxis](https://steamcommunity.com/sharedfiles/filedetails/?id=1093180806) | New Beginning | 2.5 | New |
   | Adanaxis | Anomaly | 2.25 | New |
   | Adanaxis | Nexus SubNode | 2.25 | New |
   | Adanaxis | Dark Path | 2.25 | New |
   | Adanaxis | Fuel Junction | 2.25 | New |
   | Adanaxis | Neon Carnage | 2.25 | New |
   | Adanaxis | Forbidden Outpost | 2.25 | New |
   | [AMBER Project](https://steamcommunity.com/sharedfiles/filedetails/?id=2091618233) | Information Department | 2.0 | New |
   | AMBER Project | Powerhood | 2.25 | New |
   | AMBER Project | Research Center | 1.75 | New |
   | AMBER Project | AMBER Complex | 3.75 | New |
   | [Call to Cathalu](https://steamcommunity.com/sharedfiles/filedetails/?id=921199337) | Cathalu Laboratories | 2.25 | New |
   | [Cataclysm](https://steamcommunity.com/sharedfiles/filedetails/?id=1551965583) | Space Port Catastrophe | 1.75 | New |
   | Cataclysm | Train Station Investigation | 2.0 | New |
   | [City 17](https://steamcommunity.com/sharedfiles/filedetails/?id=861497042) | Trainstation | 2.25 | New |
   | City 17 | City center | 2.1 | New |
   | City 17 | Tunnel | 2.0 | New |
   | City 17 | Fountain | 2.0 | New |
   | City 17 | Citadel | 3.25 | New |
   | [Dead City](https://steamcommunity.com/sharedfiles/filedetails/?id=909702841) | Omega City | 2.5 | New |
   | Dead City | Breaking An Entry | 2.25 | New |
   | Dead City | Search And Rescue | 3.0 | New |
   | Dead City | Fight and Flight | 2.25 | New |
   | [Jacobs 7 in 2](https://steamcommunity.com/sharedfiles/filedetails/?id=2289630826) | Jacobs 1 to 4 | 4.5 | New |
   | Jacobs 7 in 2 | Jacobs 5 to 7 | 4.5 | New |
   | *Bonus Mission* | [Mission Queen](https://steamcommunity.com/sharedfiles/filedetails/?id=936092737) | 1.75 | New |
   | [NAAM](https://steamcommunity.com/sharedfiles/filedetails/?id=1118193931) | NAAM 0 | 2.75 | New |
   | NAAM | NAAM | 1.75 | New |
   | [Operation: Chaos Theory](https://steamcommunity.com/sharedfiles/filedetails/?id=936101427) | Research Station Delta | 2.5 | New |
   | [Outpost 5](https://steamcommunity.com/sharedfiles/filedetails/?id=912391147) | Outpost 5 | 2.5 | New |
   | [Outpost 7 WIP](https://steamcommunity.com/sharedfiles/filedetails/?id=2225112897) | Boarding | 1.75 | New |
   | [Silent Corridors](https://steamcommunity.com/sharedfiles/filedetails/?id=848260335) | Laboratory | 2.5 | New |
   | Silent Corridors | Research Complex | 2.75 | New |
   | Silent Corridors | Corridor | 2.25 | New |
   | [Operation Cleansweep 3 in 1](https://steamcommunity.com/sharedfiles/filedetails/?id=2584775431) | Operation Cleansweep 3 in 1 | 2.75 | New |
- Initial challenge ratings defined:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | *No Challenge* | Standard | 1.0 | New |
   | ASBI | ASBI | 1.0 | New |
   | Difficulty Tier 1 | Standard | 3.5 | New |
   | Difficulty Tier 2 | Standard | 6.0 | New |
   | Level One | Standard | 3.5 | New |
   | One Hit | Standard | 3.5 | New |
   | Energy Weapons | Standard | 1.0 | New |
   | [Hellion Puzzle](https://steamcommunity.com/sharedfiles/filedetails/?id=1768656061) | Standard | 1.3 | New |
   | [Weapons Balancing VanASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | Standard | 1.3 | New |
   | [RNG](https://steamcommunity.com/sharedfiles/filedetails/?id=1448547351) | Standard | 1.8 | New |
   | [RNG PRO](https://steamcommunity.com/sharedfiles/filedetails/?id=1517302956) | Standard | 2.0 | New |
   | [RNG Standard](https://steamcommunity.com/sharedfiles/filedetails/?id=1448556629) | Standard | 1.5 | New |
   | [Turbo](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | Standard | 1.6 | New |
   | [Alien Swarm Mutated](https://steamcommunity.com/sharedfiles/filedetails/?id=2070196148) | Standard | 1.1 | New |
   | [VanASBI Blox](https://steamcommunity.com/sharedfiles/filedetails/?id=2326134727) | Standard | 1.4 | New |
   | [VanASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=1098363725) | Standard | 1.3 | New |
   | [Good Weapons](https://steamcommunity.com/sharedfiles/filedetails/?id=1333152091) | Standard | 1.0 | New |
   | [Good Weapons Carnage x2](https://steamcommunity.com/sharedfiles/filedetails/?id=1333152091) | Standard | 1.2 | New |
   | [Elite](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | Standard | 1.6 | New |
   | [Elite Carnage 2](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | Standard | 2.5 | New |
   | [Weapons Balancing](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | Standard | 1.0 | New |
   | [ASBI Classic](https://steamcommunity.com/sharedfiles/filedetails/?id=1358596669) | ASBI | 1.0 | New |
   | [ASBI Weapon Balancing + RNG](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 1.5 | New |
   | [ASBI Weapon Balancing + RNG2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 1.5 | New |
   | [ASBI Elite](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | ASBI | 1.5 | New |
   | [ASB2 - Carnage Edition](https://steamcommunity.com/sharedfiles/filedetails/?id=1374886583) | ASBI | 1.5 | New |
   | [ASBI Carnage x2](https://steamcommunity.com/sharedfiles/filedetails/?id=935767408) | ASBI | 1.5 | New |
   | [ASBI WB RNG3](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 1.8 | New |
   | [ASBI Weapon Balancing + RNG C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 1.8 | New |
   | [Turbo ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 1.8 | New |
   | [ASBI Elite Carnage 2](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | ASBI | 1.8 | New |
   | [ASBI Weapon Balancing + RNG2 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 2.3 | New |
   | [ASBI WB RNG3 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 2.3 | New |
   | [Turbo ASBI WB RNG2](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 2.3 | New |
   | [ASBI 2077](https://steamcommunity.com/sharedfiles/filedetails/?id=2381921032) | ASBI | 2.3 | New |
   | [ASBI Hordes](https://steamcommunity.com/sharedfiles/filedetails/?id=1664826545) | ASBI | 2.0 | New |
   | [Turbo ASBI WB RNG2 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 2.6 | New |
   | [ASBI PRO](https://steamcommunity.com/sharedfiles/filedetails/?id=1366599495) | ASBI | 1.2 | New |
   | [ASB2](https://steamcommunity.com/sharedfiles/filedetails/?id=1374886583) | ASBI | 1.2 | New |
   | [One Hit ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=1447743649) | ASBI | 1.7 | New |
   | [ASBI Tier 1](https://steamcommunity.com/sharedfiles/filedetails/?id=1167497265) | ASBI | 1.7 | New |
   | [ASBI Tier 1 Carnage x2](https://steamcommunity.com/sharedfiles/filedetails/?id=1167497265) | ASBI | 2.0 | New |
   | [Alien Swarm Mutated ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2070196148) | ASBI | 1.1 | New |
   | [ASBI Blox](https://steamcommunity.com/sharedfiles/filedetails/?id=2326134727) | ASBI | 1.1 | New |
   | [Good Weapons ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=1333152091) | ASBI | 1.0 | New |
   | [Good Weapons ASBI Carnage x2](https://steamcommunity.com/sharedfiles/filedetails/?id=1333152091) | ASBI | 1.4 | New |

## June 1, 2022 (Season 2)

- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | [Adanaxis](https://steamcommunity.com/sharedfiles/filedetails/?id=1093180806) | Dark Path | 1.1 | Decreased multiplier from 2.25 |
   | Adanaxis | Fuel Junction | 1.1 | Decreased multiplier from 2.25 |
   | Adanaxis | Forbidden Outpost | 1.1 | Decreased multiplier from 2.25 |
   | [Accident 32](https://steamcommunity.com/workshop/filedetails/?id=2814753147) | Confined Facility | 1.75 | New |
   | Accident 32 | J5 Connector | 2.25 | New |
   | Accident 32 | Lab Ruins | 2.25 | New |
- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | [ASBI WB RNG4](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 2.3 | New |
   | [Turbo ASBI WB RNG2 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 2.9 | Increased multiplier from 2.6 |
   | [ASBI WB RNG4 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 2.9 | New |

## July 8, 2022 (Season 2)

- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | Accident 32 | Information Department | 2.0 | New (official, beta branch only) |
   | Accident 32 | Powerhood | 2.25 | New (official, beta branch only) |
   | Accident 32 | Research Center | 1.75 | New (official, beta branch only) |
   | Accident 32 | Confined Facility | 2.0 | New (official, beta branch only) |
   | Accident 32 | J5 Connector | 2.5 | New (official, beta branch only) |
   | Accident 32 | Lab Ruins | 3.0 | New (official, beta branch only) |
   | *Bonus Mission* | AMBER Complex | 4.5 | New (official, beta branch only) |
   | [AMBER Project](https://steamcommunity.com/sharedfiles/filedetails/?id=2091618233) | AMBER Complex | 4.5 | Increased multiplier from 3.75 |
   | [Accident 32](https://steamcommunity.com/workshop/filedetails/?id=2814753147) | Confined Facility | 2.0 | Increased multiplier from 1.75 |
   | Accident 32 | J5 Connector | 2.5 | Increased multiplier from 2.25 |
   | Accident 32 | Lab Ruins | 3.0 | Increased multiplier from 2.25 |

## July 25, 2022 (Season 2)

- Added medals (awarded retroactively) for:
   - [Participating in a season of Heroes of the Interstellar Armed Forces.](https://stats.reactivedrop.com/static/medals/hoiaf_participant_new.png)
   - [Placing in the top 100 for a March-April-May season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_green.png)
   - [Placing in the top 100 for a June-July-August season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_red.png)
   - [Placing in the top 100 for a September-October-November season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_yellow.png)
   - [Placing in the top 100 for a December-January-February season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_blue.png)
   - [Placing in the top 20 for a season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_top20.png)

## September 3, 2022 (Season 3)

- Seasons are now monthly, rather than every 3 months.
- Scoring algorithm changes:
   - The Alive Bonus for the Standard Ruleset has been changed from 1 to 3.
   - Having onslaught disabled now sets the score to `score / 2 + 1` instead of subtracting 2 points.
- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | Operation Cleansweep | Landing Bay 7 | 1.2 | Decreased multiplier from 1.7 |
- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | [VanASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=1098363725) | Standard | 1.3 (1.0) | Now has a multiplier of 1.0 if onslaught is disabled |
   | [ASBI Weapon Balancing + RNG2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 2.3 | Increased multiplier from 1.5 |
   | [ASBI Elite](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | ASBI | 2.3 | Increased multiplier from 1.5 |
   | [ASBI WB RNG3](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 3.0 | Increased multiplier from 1.8 |
   | [ASBI Weapon Balancing + RNG C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 2.3 | Increased multiplier from 1.8 |
   | [Turbo ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 2.3 | Increased multiplier from 1.8 |
   | [ASBI Elite Carnage 2](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | ASBI | 3.0 | Increased multiplier from 1.8 |
   | [ASBI Weapon Balancing + RNG2 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 3.0 | Increased multiplier from 2.3 |
   | [ASBI WB RNG3 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 4.0 | Increased multiplier from 2.3 |
   | [ASBI WB RNG4](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 4.0 | Increased multiplier from 2.3 |
   | [Turbo ASBI WB RNG2](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 3.0 | Increased multiplier from 2.3 |
   | [ASBI 2077](https://steamcommunity.com/sharedfiles/filedetails/?id=2381921032) | ASBI | 3.0 | Increased multiplier from 2.3 |
   | [ASBI Hordes](https://steamcommunity.com/sharedfiles/filedetails/?id=1664826545) | ASBI | 2.5 | Increased multiplier from 2.0 |
   | [Turbo ASBI WB RNG2 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 6.0 | Increased multiplier from 2.6 |
   | [ASBI WB RNG4 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 6.0 | Increased multiplier from 2.9 |
   | [One Hit ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=1447743649) | ASBI | 2.5 | Increased multiplier from 1.7 |
   | [ASBI Tier 1](https://steamcommunity.com/sharedfiles/filedetails/?id=1167497265) | ASBI | 2.5 | Increased multiplier from 1.7 |
   | [ASBI Tier 1 Carnage x2](https://steamcommunity.com/sharedfiles/filedetails/?id=1167497265) | ASBI | 3.5 | Increased multiplier from 2.0 |

## October 20, 2022 (Season 4)

- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | Accident 32 | Confined Facility | 2.5 | Increased multiplier from 2.0 (official, beta branch only) |
   | Accident 32 | J5 Connector | 3.0 | Increased multiplier from 2.5 (official, beta branch only) |
   | Accident 32 | Lab Ruins | 3.5 | Increased multiplier from 3.0 (official, beta branch only) |
- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | [Turbo ASBI WB RNG2 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 3.0 | Decreased multiplier from 6.0 while we investigate problems with dedicated servers receiving updates for this addon. |

## November 1, 2022 (Season 5)

- Scoring algorithm changes:
   - The Alive Bonus for the Standard Ruleset has been changed from 3 to 1. (Reverted previous change.)
   - Computer-controlled marines no longer count as alive for the purpose of scoring.
- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | Operation Cleansweep | Landing Bay 7 | 1.5 | Increased multiplier from 1.2 |
   | BioGen Corporation | Operation X5 | 2.5 | Increased multiplier from 2.0 |

## February 1, 2023 (Season 8)

- Scoring algorithm changes:
   - Completing the same mission multiple times within the past 6 missions now applies the penalty multiple times.
   - Repeated mission penalty changed from 75% to 50%. (Both changes together change the multipliers from 1/0.25/0.25/0.25/0.25/0.25/0.25 to 1/0.5/0.25/0.125/0.0625/0.03125/0.015625.)
- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | [Blitz Campaign](https://steamcommunity.com/sharedfiles/filedetails/?id=2821100493) | Lightmare | 1.2 | New |
   | Blitz Campaign | Syntek 2 | 2.0 | New |
   | Blitz Campaign | Nightmare | 1.3 | New |
   | Blitz Campaign | Lazer Range | 1.2 | New |
   | Blitz Campaign | Jevent 2 | 3.0 | New |
   | Blitz Campaign | Asteroid Quarry | 1.75 | New |
   | [Reduction](https://steamcommunity.com/sharedfiles/filedetails/?id=914071790) | Reduction - Mission 1 | 2.25 | New |
   | Reduction | Reduction - Mission 2 | 1.5 | New |
   | Reduction | Reduction - Mission 3 | 1.75 | New |
   | Reduction | Reduction - Mission 4 | 1.75 | New |
   | Reduction | Reduction - Mission 5 | *not rated* | *There is no combat in this mission.* |
   | Reduction | Reduction - Mission 6 | 3.0 | New |
   | *Bonus Mission* | [Crude Infestation](https://steamcommunity.com/sharedfiles/filedetails/?id=1519884777) | 2.5 | New |
   | [Nitro Canister MR](https://steamcommunity.com/sharedfiles/filedetails/?id=1313628775) | Breach | 2.25 | New |
   | *Bonus Mission* | [Warehouse](https://steamcommunity.com/sharedfiles/filedetails/?id=1312255876) | 1.75 | New |
   | *Bonus Mission* | [Chemical Facility](https://steamcommunity.com/sharedfiles/filedetails/?id=1109961848) | 3.0 | New |
   | *Bonus Mission* | [Delusion](https://steamcommunity.com/sharedfiles/filedetails/?id=935549703) | 2.0 | New |
   | [Ground Zero](https://steamcommunity.com/sharedfiles/filedetails/?id=930171604) | Crash Landed | 2.25 | New |
   | Ground Zero | Ground Zero | 2.5 | New |
   | [The Beginning](https://steamcommunity.com/sharedfiles/filedetails/?id=880002363) | Keep it up! | 1.75 | New |
   | The Beginning | Underground! | 2.25 | New |
   | The Beginning | Upperground | 2.75 | New |
   | The Beginning | A beautiful night. | 1.5 | New |
   | *Bonus Mission* | [Nest](https://steamcommunity.com/sharedfiles/filedetails/?id=848331447) | 1.5 | New |
   | [Absolute madness](https://steamcommunity.com/sharedfiles/filedetails/?id=2120875626) | Madness begins | 3.0 | New |
   | [Ancient Ruins](https://steamcommunity.com/sharedfiles/filedetails/?id=915370759) | Sacred Bridge | 1.75 | New |
   | Ancient Ruins | Renovated Station | 2.0 | New |
   | [edge](https://steamcommunity.com/sharedfiles/filedetails/?id=914421802) | colony | 2.25 | New |
   | edge | crash | 2.0 | New |
   | edge | truckin | 1.25 | New |
   | edge | relay | 2.25 | New |
   | edge | theship | 2.25 | New |
- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | [Bounds](https://steamcommunity.com/sharedfiles/filedetails/?id=1584605820) | Standard | 1.3 | New |
   | [Darkness](https://steamcommunity.com/sharedfiles/filedetails/?id=1757080639) | Standard | 1.6 | New |
   | [Kill Or Die](https://steamcommunity.com/sharedfiles/filedetails/?id=937399666) | Standard | 1.6 | New |
   | [Elite](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | Standard | 2.5 | Increased multiplier from 1.6 |
   | [Elite Carnage 2](https://steamcommunity.com/sharedfiles/filedetails/?id=2461568606) | Standard | 3.5 | Increased multiplier from 2.5 |
   | [Kamikaze Drones](https://steamcommunity.com/sharedfiles/filedetails/?id=2885875069) | Standard | 3.5 | New |
   | [Invisible Aliens](https://steamcommunity.com/sharedfiles/filedetails/?id=2592381597) | Standard | 3.5 | New |
   | [Darkness ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=1757080639) | ASBI | 1.5 | New |
   | [ASBI KillOrDie](https://steamcommunity.com/sharedfiles/filedetails/?id=937405470) | ASBI | 1.5 | New |
   | [ASBI 3.0](https://steamcommunity.com/sharedfiles/filedetails/?id=1297056081) | ASBI | 2.3 | New |
   | [Kamikaze Drones ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2885875069) | ASBI | 3.0 | New |
   | [ASBI Invisible Aliens](https://steamcommunity.com/sharedfiles/filedetails/?id=2592381597) | ASBI | 3.0 | New |
   | [Turbo ASBI WB RNG2 C2](https://steamcommunity.com/sharedfiles/filedetails/?id=2178770089) | ASBI | 6.0 | Increased multiplier from 3.0 |
   | [ASBI Bounds](https://steamcommunity.com/sharedfiles/filedetails/?id=2921394571) | ASBI | 1.2 | New |

## April 20, 2023 (Season 10)

- Fixed a bug where points could carry over between seasons if the first mission completed was unrated.
- Medals awarded in seasons 1-10 will no longer be awarded in season 11 and later.
- After this season, players can no longer receive multiple medals per season; instead, only the most prestigious medal a player qualifies for per season will be awarded.
- Added new medals starting in season 11:
   - [Participating in a season of Heroes of the Interstellar Armed Forces.](https://stats.reactivedrop.com/static/medals/hoiaf_participant_11plus.png)
   - [Placing in the top 100 for a March, April, or May season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_green_11plus.png)
   - [Placing in the top 100 for a June, July, or August season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_red_11plus.png)
   - [Placing in the top 100 for a September, October, or November season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_yellow_11plus.png)
   - [Placing in the top 100 for a December, January, or February season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_blue_11plus.png)
   - [Placing in the top 20 for a March, April, or May season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_top20_green_11plus.png)
   - [Placing in the top 20 for a June, July, or August season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_top20_red_11plus.png)
   - [Placing in the top 20 for a September, October, or November season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_top20_yellow_11plus.png)
   - [Placing in the top 20 for a December, January, or February season.](https://stats.reactivedrop.com/static/medals/hoiaf_elite_top20_blue_11plus.png)
- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | Accident 32 | Information Department | 2.0 | This mission has been officially released |
   | Accident 32 | Powerhood | 2.25 | This mission has been officially released |
   | Accident 32 | Research Center | 1.75 | This mission has been officially released |
   | Accident 32 | Confined Facility | 2.5 | This mission has been officially released |
   | Accident 32 | J5 Connector | 3.0 | This mission has been officially released |
   | Accident 32 | Lab Ruins | 3.5 | This mission has been officially released |
   | *Bonus Mission* | AMBER Complex | 4.5 | This mission has been officially released |
   | *Bonus Mission* | Reversed Sewer Junction B5 | 1.25 | New |
   | *Bonus Mission* | Reversed Rydberg Reactor | 1.5 | New |
   | *Bonus Mission* | Reversed Cargo Elevator | 1.5 | New |
   | *Bonus Mission* | Reversed Landing Bay | 1.4 | New |
- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | [ASBI WB RNG4](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | ASBI | 3.0 | Decreased multiplier from 4.0 |

## May 12, 2023 (Season 11)

- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | First Person | Standard | 1.0 | New |
   | Third Person | Standard | 1.0 | New |
   | [Weapons Balancing VanASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2082369328) | Standard | 1.3 (1.0) | Now has a multiplier of 1.0 if onslaught is disabled |
   | [VanASBI Blox](https://steamcommunity.com/sharedfiles/filedetails/?id=2326134727) | Standard | 1.3 (1.0) | Decreased multiplier from 1.4<br>Now has a multiplier of 1.0 if onslaught is disabled |
   | [Resident Evil](https://steamcommunity.com/sharedfiles/filedetails/?id=2953250066) | Standard | 3.5 | New |
   | [Carnage x5](https://steamcommunity.com/sharedfiles/filedetails/?id=918455573) | Standard | 3.5 | New |
   | [Shared Damage](https://steamcommunity.com/sharedfiles/filedetails/?id=2966183425) | Standard | 1.6 | New |
   | [Shared Damage ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2966183425) | ASBI | 1.5 | New |
   | [Gnome](https://steamcommunity.com/sharedfiles/filedetails/?id=2916269416) | Standard | 2.5 | New |
   | [Tower Defense](https://steamcommunity.com/sharedfiles/filedetails/?id=2922947680) | Standard | 3.5 | New |
   | [Tower Defense VanASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2922947680) | Standard | 4.5 (3.5) | New |
   | [Tower Defense ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2922947680) | ASBI | 3.0 | New |
   | [Football Special](https://steamcommunity.com/sharedfiles/filedetails/?id=1690620315) | Standard | 1.0 | New |
   | [ASBI Football](https://steamcommunity.com/sharedfiles/filedetails/?id=1690620315) | ASBI | 1.0 | New |
   | [Super Shotgun](https://steamcommunity.com/sharedfiles/filedetails/?id=2946879059) | Standard | 2.0 | New |
   | [Super Shotgun VanASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2946879059) | Standard | 2.6 (2.0) | New |
   | [Super Shotgun ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2946879059) | ASBI | 1.5 | New |

## May 15, 2023 (Season 11)

- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | [Tower Defense ASBI](https://steamcommunity.com/sharedfiles/filedetails/?id=2922947680) | ASBI | 1.5 | Decreased multiplier from 3.0 |

## June 1, 2023 (Season 12)

- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | *Bonus Mission* | [Gluon Cave](https://steamcommunity.com/sharedfiles/filedetails/?id=2979008182) | 3.5 | New |
   | *Bonus Mission* | [Gluon Cave (No Boss Version)](https://steamcommunity.com/sharedfiles/filedetails/?id=2979008182) | 1.75 | New |
   | *Bonus Mission* | [Gluon Cave (Short Version)](https://steamcommunity.com/sharedfiles/filedetails/?id=2979008182) | 1.25 | New |

## July 1, 2023 (Season 13)

- Servers now check for updates to the addon list and scoring parameters on every level load. A server.dll update is no longer required to change the HoIAF mission or challenge lists.
- Created an [official workshop collection](https://steamcommunity.com/sharedfiles/filedetails/?id=2994125702) replacing the previous collection used for marking addons for download on dedicated servers (2816464806).
- The scoring algorithm has been updated to account for endless missions.
   1. If the mission score is less than Min Score, the mission is considered to have been failed.
   1. If the mission score is at least Min Score and the mission allows leaderboard scores to be uploaded for failures, the mission is considered to have succeeded.
   1. The existing score calculation logic is run with the Base Multiplier defined for the mission.
   1. Before diminishing returns for repeating the same mission is checked:
   1. If the mission score is higher than Max Score, it is reduced to Max Score.
   1. The mission score is multiplied by Score Multiplier.
   1. The mission score is raised to the Exponent'th power.
   1. The mission score is multiplied by the difficulty base score for the current ruleset raised to the Difficulty Contribution'th power.
   1. The mission score is multiplied by the challenge multiplier raised to the Challenge Contribution'th power.
   1. If the mission has a multiplier for the ruleset, the mission score is multiplied by that value.
   1. The mission score is added to the points earned for the mission before diminishing returns for repeating a mission are calculated.
- Added a new system where dynamic multipliers can be assigned to challenges that change their difficulty based on factors other than mission settings.
- Initial endless mission ratings defined:
   | Mission | Base Multiplier | Score Multiplier | Min Score | Max Score | Exponent | Difficulty Contribution | Challenge Contribution | ASBI Multiplier | Changes |
   | ------- | --------------- | ---------------- | --------- | --------- | -------- | ----------------------- | ---------------------- | --------------- | ------- |
   | [Infinite Landing Bay](https://steamcommunity.com/sharedfiles/filedetails/?id=2809765323) | 0.001 | 1.4 | 1 | 25 | 1.35 | 1.0 | 1.0 | 1.0 | New |
   | IAF Marine Academy | 0.001 | 0.075 | 1 | 1000 | 1.5 | 0.0 | 1.0 | 5.0 | New |
   | [The Gauntlet: Arctic](https://steamcommunity.com/sharedfiles/filedetails/?id=2990264624) | 0.001 | 0.0002 | 500 | 200000 | 1.05 | 1.0 | 1.0 | 1.0 | New |
- Updated mission ratings:
   | Campaign | Mission | Multiplier | Changes |
   | -------- | ------- | ---------- | ------- |
   | [AMBER Project](https://steamcommunity.com/sharedfiles/filedetails/?id=2091618233) | Information Department | *not rated* | Removed Workshop version of official campaign to save space |
   | AMBER Project | Powerhood | *not rated* | Removed Workshop version of official campaign to save space |
   | AMBER Project | Research Center | *not rated* | Removed Workshop version of official campaign to save space |
   | AMBER Project | AMBER Complex | *not rated* | Removed Workshop version of official campaign to save space |
   | [Accident 32](https://steamcommunity.com/workshop/filedetails/?id=2814753147) | Confined Facility | *not rated* | Removed Workshop version of official campaign to save space |
   | Accident 32 | J5 Connector | *not rated* | Removed Workshop version of official campaign to save space |
   | Accident 32 | Lab Ruins | *not rated* | Removed Workshop version of official campaign to save space |
- Updated challenge ratings:
   | Challenge | Ruleset | Multiplier | Changes |
   | --------- | ------- | ---------- | ------- |
   | [ASBI 2077](https://steamcommunity.com/sharedfiles/filedetails/?id=2381921032) | ASBI | *not rated* | Removed from HoIAF as it is no longer accessible on the Steam Workshop |
   | [Resident Evil First Person](https://steamcommunity.com/sharedfiles/filedetails/?id=2953250066) | Standard | 3.5 | New |
   | [Resident Evil Third Person](https://steamcommunity.com/sharedfiles/filedetails/?id=2953250066) | Standard | 3.5 | New |
   | [Risk of Rain](https://steamcommunity.com/sharedfiles/filedetails/?id=2985633068) | Standard | *TBD* | New |
   | [Campaign Execution](https://steamcommunity.com/sharedfiles/filedetails/?id=2811007850) | Standard | 1.0 plus 0.25 for each completed mission in the campaign | New |
   | [ASBI Campaign Execution](https://steamcommunity.com/sharedfiles/filedetails/?id=2811007850) | ASBI | 1.0 plus 0.35 for each completed mission in the campaign | New |
