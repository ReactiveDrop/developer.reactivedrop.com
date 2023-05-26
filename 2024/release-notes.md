# Alien Swarm: Reactive Drop Update - April 20 2024 (7th Anniversary!) (Draft)

TODO

## New Type of Campaign

TODO

## Fresh Coat of Paint

TODO

## Weapons

- **v45 Electric Charged Armor:** Fixed the deployment count being listed as a duplicate "Damage Blocked" stat. Added a note to the Swarmopedia entry clarifying that this armor blocks 75% of melee damage while active.
- **IAF Medical Amplifier Gun:** Fixed this weapon not having enough secondary ammo capacity for Bastille's default ammo count, causing the gun to become reloadable, which would cause primary ammo to be discarded.
- **IAF Medical SMG:** Fixed this weapon highlighting potential heal targets based on whether it had primary ammo.

## Mapping

- rd_weapon_generic_object can now be assigned an icon (see [Haikü's tutorial for how to make weapon icons](https://steamcommunity.com/sharedfiles/filedetails/?id=914386392)).
- rd_weapon_generic_object now has ForcePickUp and ForceDrop inputs as well as OnPrimaryAttack, OnSecondaryAttack, OnReload, OnPickedUp, and OnDropped outputs in Hammer.
