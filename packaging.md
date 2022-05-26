# Alien Swarm: Reactive Drop Addon Packaging Guide

## VPK Files

Addons are distributed in [VPK (Valve PacK) files](https://developer.valvesoftware.com/wiki/VPK). The simplest way to make one is to drag a folder onto `vpk.exe`, which comes with Alien Swarm: Reactive Drop in the `bin` folder (the same folder that includes Hammer and HLMV, not the folder that includes `client.dll`).

VPK files, including the more complicated `pak01_dir.vpk` that stores most of the game's files, can be viewed and extracted with [GCFScape](https://developer.valvesoftware.com/wiki/GCFScape).

If your addon is not in a VPK (for example, during development) you may wish to add `-override_vpk` to your command line arguments, which will cause loose files to be used instead of files inside packages, instead of the default behavior of preferring VPKs.

All files stored in a VPK are lowercase, and there is only one dot in each file's name. This means that `CoolSword.dx90.vtx` will be named `coolsword.vtx` inside the VPK.

## Addon File Structure

There are two files specific to addons: `addoninfo.txt` and `addonimage.jpg`.

All other files in an addon replace (or in some cases described later in this document, augment) files in the `reactivedrop` folder. If your addon contains a file named `materials/example.vmt` (for an unpacked addon, this could be at `reactivedrop/addons/MyAddon/materials/example.vmt`), the game acts as if that file were located at `reactivedrop/materials/example.vmt`.

`addoninfo.txt` is a [VDF](https://developer.valvesoftware.com/wiki/KeyValues) file that describes your addon.

A basic `addoninfo.txt` file looks like this:

```vdf
"AddonInfo"
{
	"addontitle" "Cool Mission"
	"addonauthor" "Cookie9"
	"addondescription" "Shoot guns at bugs in this cool mission!"
}
```

There are other fields in `addoninfo.txt`, but they are optional or not read by the game.

`addonimage.jpg` is a small (256x256 pixels or smaller - it will be in memory at all times when the addon is installed) preview image for the addon. The preview image is optional, and the Steam Workshop preview image will be used by the game instead if your addon is on the workshop. AddonInfo is required for the game to load your addon.

**Keep in mind that unless otherwise stated, the game will only load a file with a given name from the last installed addon that provides it.** Make sure your filenames are unique - for example, include your name or your addon's name in the filename.

## Augmented Files

In a few rare cases, the game loads a file from *all* addons that provide it and merges them.

These files are:

- `resource/reactivedrop_*.txt` - Translation files (any language). English is always loaded as a fallback for translations that are missing from the player's selected language.
- `resource/closecaption_*.txt` - Dialogue translations (any language). Again, English is loaded as a fallback.
- `particles/particles_manifest.txt` - List of particle effect files.
- `resource/swarmopedia.txt` - Swarmopedia entries.

Augmented files in your addon should only contain content you added or changed. Do not include the entire contents of the file from the game, as that will cause higher memory usage and cause you to unintentionally revert changes from other addons.

**Any filename not listed here other than `addoninfo.txt` and `addonimage.jpg` will only be loaded from one addon.** Again, make sure your filenames are unique.

## Packaging an "Other" Addon

"Other" addons are addons that do not include any missions, campaigns, or challenges. They can be model, sound, or texture replacements, unofficial translations, configuration files, asset libraries, loading screens, and so on.

Packaging an "Other" addon is simple - you just need `addoninfo.txt`, the files you want to add or replace, and optionally `addonimage.jpg`. Put them into a folder and drag the folder onto `vpk.exe`, then upload your addon from the Workshop management screen in the game.

As with anything on the Steam Community, [you need to have legal permission to share the files you're uploading](https://steamcommunity.com/workshop/workshoplegalagreement/). Valve has [given permission](https://partner.steamgames.com/doc/sdk/uploading/distributing_source_engine) to use assets from Valve games in content you share on Steam, so long as it is not misrepresented as being endorsed by Valve.

It is recommended that you rename any file you copied over from another Valve IP if you modify it, as another addon may include an unmodified version of the same file and cause conflicts.

## Challenges

Challenges are VDF files located in `resource/challenges`.

Simple challenges change console variables (convars) when they are activated, and more complex challenges include scripts or spawn definitions as well.

For example, an addon might include a file named `resource/challenges/cookie9_slippery.txt` with these contents:

```vdf
"CHALLENGE" {
	"name" "Cookie9's Slippery Floor Challenge"
	"description" "Oh no! The space janitor just washed the floors! They're all slippery!"
	"author" "Cookie9"
	"icon" "swarm/challenges/cookie9_slippery"

	"convars" {
		"asw_marine_friction" "0.2"
	}
}
```

This addon would also include `materials/vgui/swarm/challenges/cookie9_slippery.vmt` and the texture for that material.

A more complicated version of the challenge might include files named `scripts/vscript/challenge_cookie9_slippery.nut` or `resource/alien_selection_cookie9_slippery.txt`.

## Missions

*This section coming soon.*

## Campaigns

*This section coming soon.*
