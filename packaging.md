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

Missions require an overview file, which is a VDF file located in `resource/overviews` with the same name as the BSP file and a `.txt` extension.

Mission overviews have two main parts: the minimap and the mission details.

```vdf
"GAME"
{
	// These values come from cl_leveloverview when on a 1024x768 resolution.
	"pos_x" "12345"
	"pos_y" "6789"
	"scale" "10.0"

	// This texture should contain a stylized view of your map. it is used on the minimap.
	"material" "vgui/swarm/overviews/cookie9_cool_mission"
	// This texture is a fancier version of your minimap image, used in briefing.
	"briefingmaterial" "vgui/swarm/overviews/cookie9_cool_mission_briefing"

	// This section is optional and only needed if you are using minimap layering.
	// The briefing material will not be replaced by these, only the minimap.
	"vertical_sections"
	{
		"vgui/swarm/overviews/cookie9_cool_mission_underground"
		{
			// Z coordinate of the marines' feet.
			"AltitudeMin" "-300"
			"AltitudeMax" "-100"
		}
	}

	// This determines how your mission looks in the mission chooser and during briefing.
	"missiontitle" "Cool Mission"
	"description" "Shoot guns at bugs in this cool mission!"

	// These three fields are optional but recommended.
	"author" "Cookie9"
	"website" "https://example.com/cookie9/cool-mission"
	"version" "1.0"

	// This should be a 4:3 aspect ratio image representing your mission for the mission chooser.
	"image" "swarm/missionpics/cookie9_cool_mission"

	// If your mission is not part of a campaign, this is how you add credits at the end.
	// A .txt extension is automatically added. Ignored if the mission is part of a campaign.
	"CustomCreditsFile" "script/cookie9_cool_mission_credits"

	// Tags affect how the game treats your mission.
	// These are different than the searchable Workshop tags,
	// although some tags affect the Workshop uploader.
	//
	// This example includes all tags the game currently understands,
	// but you should only include the ones that make sense for your mission.
	//
	// Don't include tags that the game doesn't understand,
	// as they might mean something unexpected in the future.

	// Adds your mission to the Bonus Missions tab in the mission chooser.
	// Recommended for standard missions that are not part of a campaign.
	"tag" "bonus"

	// For missions that don't have a pre-set ending point, usually used with the "points" tag.
	// Adds your mission to the Endless tab in the mission chooser.
	// Should not be used on the same mission as "bonus" or for missions in a campaign.
	//
	// It is recommended that you tag survival missions with a pre-defined number of waves as "bonus"
	// and then add the "Survival" tag when uploading to the Workshop instead of using this tag.
	"tag" "endless"

	// This tag will make your mission's leaderboard show points in descending order instead of time in ascending order.
	// Use the AddPoints input on asw_gamerules to award points to the squad.
	"tag" "points"

	// Allows your mission to upload leaderboard scores even when the mission fails. Sometimes useful with "endless".
	"tag" "upload_on_failure"

	// For Deathmatch maps. Adds your mission to the Deathmatch tab in the mission chooser.
	// Should not be part of a campaign. The map must contain an asw_deathmatch_mode entity.
	"tag" "deathmatch"
}
```

## Campaigns

Campaigns are collections of missions that are not otherwise visible in the mission chooser with a VDF file located in `resource/campaigns`.

The file should have a `.txt` extension and have a unique name, but the name doesn't need to match anything else in your addon.

```vdf
"GAME"
{
	"CampaignName" "Cookie9's Cool Campaign"
	"CampaignDescription" "Shoot many guns at many bugs in this cool campaign!"
	"CustomCreditsFile" "script/cookie9_cool_campaign_credits"

	// The icon that will appear in the mission chooser.
	"ChooseCampaignTexture" "swarm/campaigns/cookie9_cool_campaign"

	// These should be between 0 and 1023, but are not currently used in the game.
	// If they were, they would determine the location of the campaign on a galactic map.
	"GalaxyX" "123"
	"GalaxyY" "456"

	// These next fields determine how the campaign map looks.
	// These are safe defaults, but it is highly recommended that you make something unique for your campaign.
	"CampaignTextureName" "swarm/campaign/jacob_galacticmap"
	"CampaignTextureLayer1" "swarm/Campaign/CampaignMap_EmptyLayer"
	"CampaignTextureLayer2" "swarm/Campaign/CampaignMap_EmptyLayer"
	"CampaignTextureLayer3" "swarm/Campaign/CampaignMap_EmptyLayer"

	// Search lights appear on the campaign map. Set Searchlight\*X to 0 to hide the search light.
	// Coordinates are from 0 to 1023; angles are in degrees counterclockwise from the right.
	"Searchlight1X" "217"
	"Searchlight1Y" "860"
	"Searchlight1Angle" "80"
	"Searchlight2X" "263"
	"Searchlight2Y" "751"
	"Searchlight2Angle" "100"
	"Searchlight3X" "92"
	"Searchlight3Y" "446"
	"Searchlight3Angle" "90"
	"Searchlight4X" "580"
	"Searchlight4Y" "266"
	"Searchlight4Angle" "90"

	// The first mission in a campaign file is the "starting point", only shown on the map.
	"MISSION"
	{
		"MapName" "start_area"

		// Location coordinates are from 0 to 1023. Description is shown on the campaign map.
		"LocationX" "330"
		"LocationY" "780"
		"LocationDescription" "Atmospheric Entry"

		// The starting point should be linked to the first mission in your campaign.
		"Links" "cookie9_coolcampaign_01"
	}

	"MISSION"
	{
		"MissionName" "Ice Cold"

		// MapName should match the name of your bsp file.
		"MapName" "cookie9_coolcampaign_01"

		"LocationX" "525"
		"LocationY" "700"
		"LocationDescription" "Ice Cream Factory"
		"ShortBriefing" "Go to the ice cream factory."

		// DifficultyModifier changes the mission difficulty.
		// 3 is about equivalent to increasing the skill level by one tier, eg. from normal to hard.
		"DifficultyModifier" "0"

		// ThreatString is not currently used, but can be any text.
		"ThreatString" "Low"

		"AlwaysVisible" "1"
		"NeedsMoreThanOneMarine" "0"

		// Link your first mission to the starting point and to the second mission.
		"Links" "start_area cookie9_coolcampaign_02"
	}

	"MISSION"
	{
		"MissionName" "Unfrozen Warehouse"
		"MapName" "cookie9_coolcampaign_02"
		"LocationX" "360"
		"LocationY" "506"
		"LocationDescription" "Road Salt Storage"
		"DifficultyModifier" "0"
		"ThreatString" "Medium"
		"AlwaysVisible" "1"
		"NeedsMoreThanOneMarine" "0"

		// The short briefing is shown on the campaign transition screen.
		"ShortBriefing" "Find the salt at the salt store."

		// Missions in the middle of your campaign should link to the mission immediately before and after them.
		"Links" "cookie9_coolcampaign_01 cookie9_coolcampaign_03"
	}

	"MISSION"
	{
		"MissionName" "Cold Fusion"
		"MapName" "cookie9_coolcampaign_03"
		"LocationX" "820"
		"LocationY" "200"
		"LocationDescription" "Ice Cream Reactor"
		"DifficultyModifier" "0"
		"ThreatString" "High"
		"AlwaysVisible" "1"
		"NeedsMoreThanOneMarine" "0"
		"ShortBriefing" "Turn off the reactor."

		// The last mission in your campaign only has one link.
		"Links" "cookie9_coolcampaign_02"
	}

	// The game doesn't currently understand any tags for campaigns.
}
```
