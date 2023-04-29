# 2024 OCM Contracts

Based on several "battle pass" or "choose your own adventure" or just plain "achievement" systems in various games, we're adding a new objective system that is per-player and persists between missions.

Major inspirations include:

- Deep Rock Galactic: "Performance Pass"
- Team Fortress 2: "ConTracker"
- Dota Underlords: "City Crawl"
- CS:GO: "Operations"
- Dota 2: "Hero Challenges"
- Warframe: "Star Chart"
- Helldivers: "Planet"

## Basic Overview

- 9 out-of-game "campaigns", consisting of a short introductory campaign, one for each marine class, "weapons", "locations", "aliens", and "special requests".
- Each campaign consists of a never-before-seen Telic Corporation facility (with one notable exception) with automated defenses that will be infiltrated by an Office of Consensus Maintenance operative. The only gameplay here is completing objectives to advance the plot. The defenses are purely story.
- Players will make progress through a graph of areas on a 2D map. Areas have prerequisites, and areas with multiple prerequisite areas can be AND or OR.
- Each area contains a certain number of objectives, and a certain number of them need to be completed to complete the area.
- Completing objectives adds visual details to the area to represent progress.
- Objectives reward an amount of OCM gift shop currency - either rare, which can be used to buy the 5 new weapons that are in the shop, or common, which can be used to buy materials and possibly cosmetics like medals
- Areas reward a specific item, with the first and last areas of each campaign granting the most appealing items.
- Each campaign has a fairly substantial reward early in the campaign and a fairly substantial reward at the end.

Things to consider:

- Need to make sure this doesn't murder people who have OCD. Everything should be hideable or at least tied to a specific spot that isn't used for anything else. Currency numbers should end up nice and rounded.
- The current design is completely non-moddable. Can we make this moddable without primarily encouraging players to cheat? What can we give as rewards for modded campaigns?

## Rewards

First Area:

- **Intro:** "OCM Contractor ID" (medal that tracks contract campaign stats)
- **Officer:** NA-23 Incendiary Grenades
- **Special Weapons:** MA9128 Force Dome Generator
- **Medic:** EX981 Speed Burst Module
- **Tech:** EC-02 Stun Grenades
- **Weapons:** IAF Railgun Sentry
- **Locations:** "Connoisseur" (medal that tracks "successful workshop missions")
- **Aliens:** TODONAME Ricochet Rifle
- **Special Requests:** TODONAME Flechette Launcher

Final Area:

- **Intro:** remaining eight campaigns unlocked
- **Officer:** customized suits (strange: Missions, Successful Missions, ?) for both officers
- **Special Weapons:** customized suits (strange: Missions, Successful Missions, Alien Kill Streak) for both special weapons
- **Medic:** customized suits (strange: Missions, Successful Missions, Infestations Cured) for both medics
- **Tech:** customized suits (strange: Missions, Successful Missions, Fast Hacks) for both techs
- **Weapons:** choice of strange weapon + choice of strange device
- **Locations:** strange device: "Missions" + strange device: "Successful Missions"
- **Aliens:** strange device: "Aliens Killed" + strange device: "Alien Kill Streak"
- **Special Requests:** "Helvetica's Gratitude" (medal that tracks "successful missions with friends" and "successful missions with strangers") + OCM Gift Shop will now buy excess crafting materials

Other area completions give rare currency; all objective completions give common currency.

OCM Gift Shop:

- Five weapons that have the rare currency shared between them. Each can be unlocked once.
	- DRG19 Cryo Cannon (cost 4 intel)
	- G521 Plasma Thrower (cost 4 intel)
	- HC42 Automated Hacking Tool (cost 5 intel)
	- TC79 Energy Field Generator (cost 4 intel)
	- TC1121 Reanimator (cost 6 intel)
	- Total cost is 23 out of 30 intel from area completions.
	- sell intel -> 1000 credits (cost 1 intel, only available after all 5 weapons have been purchased)
- Crafting materials (credits):
	- Can buy from the start; can only sell after completing Special Requests campaign final area.
	- XXXX Carbon (buy YYYY credits / sell ZZZZ credits)
	- XXXX Loose Wires (buy YYYY credits / sell ZZZZ credits)
	- XXXX Common Crafting Material (buy YYYY credits / sell ZZZZ credits)
	- XXXX Uncommon Crafting Material (buy YYYY credits / sell ZZZZ credits)
	- XXXX Rare Crafting Material (buy YYYY credits / sell ZZZZ credits)
	- XXXX Regional Crafting Material (buy YYYY credits / sell ZZZZ credits)
	- Without selling crafting materials or intel, the amount of common credits available is XXXX.

## Campaigns

- [#rd_contract_campaign_in](contract-campaign-intro.html) (2 areas)
- [#rd_contract_campaign_of](contract-campaign-officer.html) (5 areas)
- [#rd_contract_campaign_sp](contract-campaign-special-weapons.html) (5 areas)
- [#rd_contract_campaign_me](contract-campaign-medic.html) (5 areas)
- [#rd_contract_campaign_te](contract-campaign-tech.html) (5 areas)
- [#rd_contract_campaign_we](contract-campaign-weapons.html) (4 areas)
- [#rd_contract_campaign_lo](contract-campaign-locations.html) (9 areas)
- [#rd_contract_campaign_al](contract-campaign-aliens.html) (7 areas)
- [Special Requests](contract-campaign-special-requests.html) (6 areas)
