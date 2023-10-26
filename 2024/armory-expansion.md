# 2024 Armory Expansion

We're adding **twelve** new unlockable weapons, and also a new way to unlock weapons. The max commander level of 34 will not change in this update, and these new weapons will not need to be re-obtained when a commander promotes. They will have requirements to equip that are separate from their requirements to obtain, however. For example, armory access restrictions can re-lock the weapon after a promotion (it will not need to be re-obtained, however).

Eight new Primary/Secondary weapons:

- [TC19 DRG Cryo Cannon](#new-weapon-tc19-drg-cryo-cannon)
- [G521 Plasma Thrower](#new-weapon-g521-plasma-thrower)
- [X-117 Flechette Launcher](#new-weapon-flechette-launcher)
- [v60 Ricochet Rifle](#new-weapon-ricochet-rifle)
- [HC42 Automated Hacking Tool](#new-weapon-hc42-automated-hacking-tool)
- [IAF Railgun Sentry](#new-weapon-iaf-railgun-sentry)
- [TC79 Energy Field Generator](#new-weapon-tc79-energy-field-generator)
- [TC1121 Reanimator](#new-weapon-tc1121-reanimator)

Four new Extra/Equipment weapons:

- [EC-02 Stun Grenades](#new-equipment-ec-02-stun-grenades)
- [NA-23 Incendiary Grenades](#new-equipment-na-23-incendiary-grenades)
- [EX981 Speed Burst Module](#new-equipment-ex981-speed-burst-module)
- [MA9128 Force Dome Generator](#new-equipment-ma9128-force-dome-generator)

## New Weapon: TC19 DRG Cryo Cannon

- Class Restriction: Special Weapons
- Activation Type: Gun (projectile, spin-up, ammo)
- Secondary Fire: Hold (spin-up)
- Manufacturer: Telic Corporation
- Inspirations: Deep Rock Galactic "Cryo Cannon"

**Attributes:** Flash-Freezes, Extinguishes Fires, Slow Movement

- Basically a fire extinguisher minigun that does damage.
- Deals additional damage when extinguishing a fire on something.
- Damage slightly increases against fully frozen targets.

**Alt Fire Description:** Barrel Spin-up

**Lore:** This Telic Corporation prototype was originally meant to be a tool to quickly freeze specimens for safe transport. The Directed Refrigeration Gun had two main problems: first, it was so large and heavy that it required an exosuit to operate. Second, the process of quickly freezing a specimen severely damaged it - or just made it angry. The freezing didn't last very long, and it usually ended with one of the participants shattered or torn to shreds.

- [x] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [x] Lore text
- [ ] Balance

## New Weapon: G521 Plasma Thrower

- Class Restriction: Special Weapons
- Activation Type: Gun (projectile, ammo)
- Secondary Fire: Gun (air blast, uses primary ammo)
- Manufacturer: Telic Corporation
- Inspirations: Team Fortress 2 "Phlogistinator", Half-Life "Gluon Gun"

**Attributes:** Extreme Damage, Loses Accuracy

- Fires a beam with the cool helix thing that becomes increasingly wobbly and unpredictable the more the gun is fired in a time window.
- Vaporizes biomass similar to the mining laser.
- Airblast extinguishes fires and pushes; takes more than 1 ammo per airblast.
- Big damage.
- Reloadable, same ammo as flamer?

**Alt Fire Description:** Pressurized Air Blast

**Lore:** TODO. <!-- TODO: Quark-Gluon Plasma? would be a nice callback to the HL1 Gluon gun -->

- [x] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Weapon: X-117 Flechette Launcher

- Class Restriction: *unrestricted*
- Activation Type: Gun (projectile, ammo)
- Secondary Fire: None
- Manufacturer: Vapor Systems
- Inspirations: Half-Life 2 "Hunter"

**Attributes:** Delayed Detonation

- Fires Half-Life 2: Episode Two Combine Hunter flechettes.
- Aims at the crosshair rather than trying to aim flat, so that missed shots hit the floor.

**Lore:** TODO.

<!--
Vapor Systems a reference to Valve Software / Valve Corporation

- founded by Gabe Newman (the not-Gabe-Newell character from "Half-Life: Alyx but the gnome is too aware" https://www.twitch.tv/wayneradiotv/clip/FrigidFilthyKiwiBleedPurple-jzQm3_tkY9fx7cB2)
- started out as a shipping company called VaporTrans, later rebranded to Vapor Systems when they started manufacturing their own products and doing their own research (the reverse of Valve, who started out making Steam to just distribute their own stuff and later became the biggest PC game distributor)
- guns are references to Half-Life 2: Episode Two (the flechettes are Combine Hunter flechettes) and Ricochet (literally a "ricochet" rifle)
- in actuality, these two guns are remakes of leftover prototypes from the Valve version of Alien Swarm, released in 2010
-->

- [x] Model
- [ ] Sounds
- [x] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Weapon: v60 Ricochet Rifle

- Class Restriction: *unrestricted*
- Activation Type: Gun (hitscan, ammo)
- Secondary Fire: Hold (changes primary fire to burst/shotgun mode)
- Manufacturer: Vapor Systems
- Inspirations: Warframe "Drakgoon"

**Attributes:** Bounce Shots

- Bullets bounce up to 3 / 1 times
- Pellets per shot: 1 / 7
- Spread: 3 / 20 degrees
- Damage per pellet: 100% / 30% of rifle bullet damage
- Laser sight shows bounce preview.

**Alt Fire Description:** Burst Fire Mode

**Lore:** TODO.

- [x] Model
- [ ] Sounds
- [x] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Weapon: HC42 Automated Hacking Tool

- Class Restriction: *unrestricted*
- Activation Type: None
- Secondary Fire: None
- Manufacturer: SynTek Megacorporation
- Inspiration: AS2K4 "Hack Tool"

**Attributes:** Allows Any Marine To Hack

- If a marine has this weapon equipped or holstered, they count as a tech for the purposes of tech marine requirements.
- If this weapon is in the mission, the tech marine failure state takes longer to count down to give marines time to retrieve it.
- Allows non-tech marines to access the hacking minigames.
- Does not boost download speed or provide any Engineering bonus.
- Techs with this item equipped have part of the hacking minigame covered by TV static. This area counts as completed for the purpose of determining if a hack is finished.
- Visible in the marine's left hand if doing a hack with this item holstered.

**Lore:** An advanced IAF tech-issue 'circuit breaker' hacking device, developed in the high security IAF labs.  Offering a variety of intelligent circuit analyzers and bypassing logic gate systems, this tool can be used by any marine to bypass security systems.  Tech marines can use this tool to hack at twice the speed.

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Weapon: IAF Railgun Sentry

- Class Restriction: *unrestricted*
- Activation Type: Deployable (sentry)
- Secondary Fire: None
- Manufacturer: SynTek Megacorporation
- Inspiration: Helldivers "A/RX-34 Railcannon Turret"

**Attributes:** TODO

- Faster rotation speed than other sentries.
- Deals a huge amount of damage per shot.
- Does not aim at targets obscured by marines, but can deal friendly fire damage (if it hits a marine through a target).
- Does not aim at shieldbugs unless it can get a clean shot.
- 125 ammo?
- Pierces, but no AOE.

**Lore:** TODO.

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Weapon: TC79 Energy Field Generator

- Class Restriction: Tech
- Activation Type: Attached Deployable (ammo)
- Secondary Fire: None
- Manufacturer: Telic Corporation
- Inspiration: Team Fortress 2 "Projectile Shield"

**Attributes:** TODO

- While firing, creates a large yellow version of the TF2 medic's energy shield from Mann vs Machine.
- Destroys projectiles and blocks hitscan bullets from non-allies. Ally projectiles and bullets unaffected.
- Shield is non-solid to characters. Deals DMG_DISSOLVE to anyone touching it, including allies.
- Large ammo pool, but not refillable and does not reload.

**Lore:** TODO. <!-- Telic Corporation -->

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Weapon: TC1121 Reanimator

- Class Restriction: Medic
- Activation Type: None (key)
- Secondary Fire: None
- Manufacturer: Telic Corporation
- Inspiration: Team Fortress 2 "Reanimator"

**Attributes:** TODO

- When the item is in a map, marines who die spawn "gravestones" which look like the trap thing from ghost busters.
- The gravestones have visible holograms representing the marine who died for the medic with this weapon holstered, to every marine when this weapon is equipped, or to marines who are within a very small distance (100 unit USE radius?) of the gravestone.
- Gravestones periodically check to make sure at least one medic owning the weapon is able to path to them. If not, they teleport to a nearby accessible location (note: will have to check if this feels good or like cheating)
- The weapon is completely passive and acts as a key. The medic can expend the weapon by interacting with a gravestone to respawn the marine it represents at full health with the weapons they had when they died (unless someone else is currently holding those weapons - that is, the weapons teleport to the revived marine if they are on the ground).
- If no copies of the weapon exist in a mission, any remaining gravestones self-destruct.

**Lore:** TODO. <!-- Telic Corporation -->

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Equipment: EC-02 Stun Grenades

- Class Restriction: *unrestricted*
- Activation Type: Thrown (ammo)
- Manufacturer: SynTek Megacorporation
- Inspiration: 22A7-Z Prototype Assault Rifle alternate fire

**Attributes:** TODO

- Similar to CR-18 Freeze Grenades, but causes a shock at the targeted area rather than a freeze.

**Lore:** TODO. <!-- Electric Charge -->

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Equipment: NA-23 Incendiary Grenades

- Class Restriction: Officer
- Activation Type: Thrown (ammo)
- Manufacturer: SynTek Megacorporation
- Inspiration: M42 Vindicator alternate fire

**Attributes:** TODO

- Simply a box of vindicator grenades that can be thrown in an arc. Direct hit causes an immediate detonation as usual.

**Lore:** TODO. <!-- Napalm -->

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Equipment: EX981 Speed Burst Module

- Class Restriction: *unrestricted*
- Activation Type: Instant (battery)
- Manufacturer: Telic Corporation
- Inspiration: Team Fortress 2 "Chargin' Targe", Dota 2 "Force Staff"

**Attributes:** TODO

- When used, makes the marine move forward very quickly but also greatly reduces their turning speed.
- Can be used again while active to quickly stop the effects.
- Recharges over time.
- Deals physics damage to non-marines hit by the charge; stumbles marines who are hit.

**Lore:** TODO. <!-- EXosuit EXtension -->

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance

## New Equipment: MA9128 Force Dome Generator

- Class Restriction: Special Weapons
- Activation Type: Thrown (ammo)
- Manufacturer: Telic Corporation
- Inspiration: Guild Wars 2 "Sanctuary", Dota 2 "Magnetic Field", EVOLVE "Mobile Arena"

**Attributes:** TODO

- When it lands after being thrown, creates a sphere (usually the bottom half will be underground) that pushes non-allies of the deployer.
- Push force is initially very strong, then becomes weaker once the dome is fully deployed.
- Push force remains strong against projectiles (boomer blobs, mortar shells, ranger spit, etc).
- When the duration expires, the force dome simply vanishes and everything it was pushing can move normally.

**Lore:** TODO. <!-- Mass Accelerator / Mobile Arena / ? -->

- [ ] Model
- [ ] Sounds
- [ ] Implementation
- [ ] Swarmopedia
- [ ] Lore text
- [ ] Balance
