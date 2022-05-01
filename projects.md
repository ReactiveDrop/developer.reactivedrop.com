# Projects

## Documentation

- [ ] Create level design style guide
- [ ] Document all lore (and origins of lore)
- [ ] Create campaign creation guide
- [ ] Create challenge creation guide
- [ ] Look into translating documentation

## Translation

- [x] Load reactivedrop_foo.txt from all addons (similar to particle_manifest.txt)
- [x] Load closecaption_foo.txt from all addons
- [ ] Load closecaption_foo.dat from all addons (need to determine if this is possible with compiled captions)
- [x] Rewrite translation sync tool to format better, avoid duplication
- [ ] Create "fail to load translations on purpose" cvar for testing
- [x] All official campaigns: make campaign, overview strings available for translation
- [ ] All official campaigns: make objective strings available for translation
- [ ] All official campaigns: make misc (game_text, env_instructor_hint, etc.) strings available for translation
- [ ] Look into translating other parts of Steam Community
- [ ] Sweep UI for untranslatable strings
- [X] Make stats website translatable
- [ ] Translation progress dashboard

## Official Campaigns

- [ ] Make Bonus Missions and Deathmatch campaigns dynamically created at runtime
- [ ] Bonus Missions: move away from numbered missions, use names instead
- [ ] Operation Cleansweep: U.S.C. Medusa: elevator to bridge has inconsistent door behavior, causing marines to fall out or not be able to get in
- [ ] Research 7: Illyn Forest: drone can get stuck in generator attack animation, causing guaranteed failure
- [ ] Lana's Escape: Lana's Bridge: escape trigger does not respond to marine death properly
- [ ] Lana's Escape: Lana's Sewer: escape trigger does not respond to marine death properly
- [ ] Lana's Escape: Lana's Maintenance: wrong number of random hacks can spawn
- [ ] Lana's Escape: Lana's Bridge: research possibility of letting marines build the sentry after the bridge in place with fixed leg positions
- [ ] Lana's Escape: Lana's Maintenance: research possibility of letting marines build sentry into south-east drone hole in generator objective room
- [ ] Tutorial: new mission
- [ ] BioGen Corporation: BioGen Labs: remaster
- [ ] Sweep official maps for inconsistent behavior

## Scripting / Challenges

- [ ] Research possibility of giving challenges access to UI for voting/menus
- [ ] fog\_volume equivalent for specific marines

## Menus / Controller

- [ ] Remake lobby browser a la Deep Rock Galactic lobby browser
- [ ] Remake mission selection a la Warframe inventory screen
- [ ] Make d-pad use radial menus to access swap marine, offhand, offhand 2, emote
- [ ] Research viability of using ISteamInput API without engine updates
- [x] Create advanced game settings menu
- [ ] Main menu commander profile
- [ ] Categorized achievements list
- [ ] Have received feedback that "select character" button in briefing is not as obviously interactable as it could be

## Team

- [ ] Badges on stats website for contributors with what their contribution was
- [ ] Donation links on stats website for contributors?
- [ ] Full list of contributors by role on stats website

## TileGen

- [ ] Method of compiling tileset to bsp file
- [ ] Entity that moves tiles around to create playable space at runtime
- [ ] MissionChooser support for generating and distributing a layout
