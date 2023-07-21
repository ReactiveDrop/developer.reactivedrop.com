# Alien Swarm: Reactive Drop Developer FAQ

## Face Poser, HLMV, or Hammer crash at startup!

This engine bug has a simple workaround. In Steam, go to Manage -> Browse Local Files, then open `reactivedrop/cfg/video.txt`. Make sure `setting.defaultresheight` is set to the correct value. An engine bug puts the screen width there on the first game startup, which causes SDK tools to crash.

## I want to help make Alien Swarm: Reactive Drop!

First, that's fantastic! The more people helping, the more improvements we can make to the game.

Where you should go next is based on what kind of help you want to offer:

| Help with... | By going to... |
| ------------ | -------------- |
| Translating the game into your language | <https://github.com/ReactiveDrop/reactivedrop_translations#readme> |
| Ideas | <https://steamcommunity.com/workshop/discussions/?appid=563560> |
| Reporting bugs | <https://github.com/ReactiveDrop/reactivedrop_public_src/issues> or <https://feedback.reactivedrop.com/> |
| Programming | <https://github.com/ReactiveDrop/reactivedrop_public_src#readme> |
| Developer documentation | <https://github.com/ReactiveDrop/developer.reactivedrop.com> |
| Player documentation | <https://github.com/ReactiveDrop/wiki.reactivedrop.com> or <https://steamcommunity.com/app/563560/guides/> |
| Monetary donations | <https://store.steampowered.com/itemstore/563560/> or check developers' Steam profiles |
| Fan art or renders | <https://steamcommunity.com/app/563560/images/> |
| New missions, challenges, cosmetic mods, etc. | <https://steamcommunity.com/app/563560/workshop/> |

Something missing from this list? [Let us know.](https://feedback.reactivedrop.com/)

## What parts of Alien Swarm: Reactive Drop aren't open source?

While the majority of Alien Swarm: Reactive Drop's code is [open source](https://github.com/ReactiveDrop), some of the code related to the game is not publicly available for various reasons.

| Closed Source Component | Reason |
| ----------------------- | ------ |
| Anti-cheat              | We don't want to make it easier for cheat authors to work around our anti-cheat functionality. Rest assured, the anti-cheat does not record any personal information and does not run when you're not playing the game. |
| Engine                  | Valve has not made the source code of the 2010 Source Engine branch available. |
| Website                 | The reactivedrop.com website's source code is not available. |
| Ranked servers          | The code that handles ranked servers is not part of the open source code because we do not want custom clients or servers running it. This gives us assurance that any custom server running the ranked server code is malicious and not merely an accident. |

## Can I make external content such as streams, videos, blog posts, etc. using content from Alien Swarm: Reactive Drop?

**Yes.** There are no restrictions on showing Alien Swarm: Reactive Drop in-game content, including pre-release content, to others. We ask that you try to be clear about where the content came from (eg. "you can find this workshop addon here") but this is not an enforced rule.

## I'm running a cyber cafe or streaming game service. Am I allowed to provide users access to Alien Swarm: Reactive Drop?

**Yes.** If your service can run Steam games, you have Reactive Drop Team's permission to run Alien Swarm: Reactive Drop on your service and optionally indicate that you do so. For cyber cafes participating in the [Steam PC Café](https://partner.steamgames.com/pccafe) program, you don't need to do anything - players who have added AS:RD to their Steam accounts can already play it on your machines.

We have also given a few streaming game platforms such as Boosteroid and NVIDIA GeForce Now explicit permission to host AS:RD. This does not differ from the permission given in the previous paragraph. If you need explicit written permission that matches the above, feel free to [submit a ticket](https://feedback.reactivedrop.com).

## I'm running a game publishing or distribution service. Can Alien Swarm: Reactive Drop join my service?

Likely no.

## What agreement do you have with Valve?

Alien Swarm: Reactive Drop is a [non-commercial Source Engine mod](https://partner.steamgames.com/doc/sdk/uploading/distributing_source_engine). To summarize, we are allowed to use released assets from any first party Valve game and release the game on Steam. We are not allowed to charge money for the game or use leaked material.

We have requested and received special permission to use the Steam microtransaction service for donations on the condition that the items we make available through that service are informational and not desirable.

## I found a security problem!

If the problem is in Steam or Source Engine, you can submit a report on [Valve's HackerOne page](https://hackerone.com/valve). If the problem is specific to Alien Swarm: Reactive Drop's websites or game code, [submit a ticket](https://feedback.reactivedrop.com). You can also submit a ticket if you have a cheating program sample to send to the developers for analysis.

## I was banned!

If you were kicked via a vote, the ban lasts 5 minutes and only affects the server or lobby host you were kicked from.

If you have been banned from a dedicated server, contact the server's administrators. Reactive Drop Team cannot modify server-specific bans.

If you have received a [game ban](https://help.steampowered.com/en/faqs/view/46DB-4CEC-F7E9-49E5) for cheating or other abuse or [a ban from the community hub](https://help.steampowered.com/en/faqs/view/271D-4C46-2915-B315) and you feel it was issued incorrectly, feel free to [submit a ticket](https://feedback.reactivedrop.com).

## I'm missing an item!

Many of Alien Swarm: Reactive Drop's Steam Inventory items are manually granted. In some cases, we make a mistake or miss something that deserves a medal. The best way to get this fixed is to [submit a ticket](https://feedback.reactivedrop.com). Note that the majority of in-game weapons are unlocked via leveling up, which is not part of the Steam Inventory Service.

## I'm missing an achievement!

If you're missing an achievement due to a bug, [check the feedback forum](https://steamcommunity.com/app/563560/discussions/2/) for a recent thread about the achievement, and if none exists, please create one.

## I found a bug!

First: try shooting it with your gun. Most of the bugs die if they are shot with bullets.

If it's not that kind of bug, please [create an issue report](https://github.com/ReactiveDrop/reactivedrop_public_src/issues), [post on the feedback forum](https://steamcommunity.com/app/563560/discussions/2/), or tell a developer about it in the official Steam or Discord chats. If it's a bug with a Workshop addon, tell the author of that addon.

# Partnerships

## I'm running a "cloud gaming" service where users can pay a subscription fee for access to a machine where they can play a game over remote desktop.

Great! As long as your platform downloads the game's content from Steam and players log in using their Steam accounts, you don't need any special permission to allow your users to run Alien Swarm: Reactive Drop on your computers.

## I would like to run a dedicated server for Alien Swarm: Reactive Drop and don't know where to start.

You'll need to use [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) to download the server files, and after that you can run them like you would run any other EXE. The two apps you need to install are 563560 and 1007 (in the same folder). The dedicated server app is 582400, but there are currently issues with getting it to download a specific branch, and the files you'd get by installing 1007 and 563560 are exactly the same files you would get by installing 582400 if everything worked correctly.

You can run the server just by double-clicking srcds.exe, but most server hosts will want to set up a script to start the server in a loop, with a call to SteamCMD before each run to do a light-weight check for updates.

On Linux hosts, you will need to set a variable in SteamCMD to allow downloading the Windows version of the game, which you can run through Wine, Proton, or something similar: `@sSteamCmdForcePlatformType windows`

An example of a script to run the server repeatedly on Linux is:

```
#!/bin/bash

cleanup() {
	wineserver -k
}

trap cleanup EXIT

while true; do

steamcmd +force_install_dir ~/reactivedrop_server \
	+login anonymous \
	+@sSteamCmdForcePlatformType windows \
	+app_update 1007 \
	+app_update 563560 -beta beta \
	+quit

(cd reactivedrop_server &&
./srcds_console.exe -console -condebug \
	-game reactivedrop \
	+exec server \
	+map lobby)

done
```

In `(server root directory)/reactivedrop/cfg/server.cfg`, you'll want something like:

```
// hostname determines how your server shows up in the server browser.
hostname "My Cool Server"

// you'll want your rcon password to be impossible to guess.
// rcon gives full administrative access to the server console.
// don't use this one, obviously.
rcon_password iEmXNGpU5cMcnoDAj53JXGNGQ9jtyazkHwcauN4jNvI8rHyPOxCCXEtGZjnQ0qr

// you can decide the maximum number of players for your server.
// any players not controlling a marine will be spectators.
maxplayers 12

// make the server process exit when the last player leaves
// (this makes it very easy to keep the server up-to-date as a
// player failing to join your server while it is empty due to
// a version mismatch will cause it to update with a script
// like what is shown above)
rd_server_shutdown_when_empty 1
```

You can make a file named `(server root directory)/reactivedrop/cfg/workshop.cfg` to subscribe your server to various Steam Workshop addons. Each command in this script should be `rd_enable_workshop_item` followed by the shared file ID of the workshop addon or collection you want your server to subscribe to.

## I want my dedicated server to participate in Heroes of the Interstellar Armed Forces!

Servers participating in Heroes of the Interstellar Armed Forces have additional requirements:

- The server must be running at the default tick rate.
- The server must have a static IP address and port.
- The server must have a stable internet connection.
- The server must not be modded (non-gameplay-affecting SourceMod plugins may be allowed on a case-by-case basis).
- Workshop addons should be kept to the list installed automatically on ranked servers to avoid confusing players with mission choices that will earn them no points. (Some participating server hosts choose to run a separate unranked server with a wider variety of addons installed.)
- The server and its administrator(s) should be well-known and trusted in the community.

See [the Contributing to AS:RD thread](https://steamcommunity.com/app/563560/discussions/0/3361397532258443696/) for more information, including how to apply.

## Someone stole my content and uploaded it to the Steam Workshop as their own.

File a [DMCA takedown request](https://steamcommunity.com/dmca/create/) with information about what was plagiarized. Uploading content to the Steam Community requires signing a legal document stating the uploader must have legal ownership of the content being uploaded, and we take breaches of this requirement very seriously.

## I would like to propose a business partnership with the Reactive Drop Team.

First, Alien Swarm: Reactive Drop is classified as a [non-commercial Source Engine mod](https://partner.steamgames.com/doc/sdk/uploading/distributing_source_engine) on Steam. This means:

- We cannot include advertising in our game or on its Steam Store or Community pages.
- We cannot sell access to content.
- We *can* accept donations in exchange for non-gameplay-affecting cosmetic items.
- We cannot add Steam Trading Cards, badges, emoticons, or profile backgrounds to our game.
- We *can* add stickers, animated avatars, avatar frames, animated profile backgrounds, and mini-profile backgrounds to the Steam points shop, but are unlikely to do so as part of a business partnership.
- We are unlikely to be able to distribute the game outside of Steam. (And it requires Steam API services for many of its features, so there would be no benefit in most cases.)

If you still think your proposal might be accepted, feel free to send us a message on [the feedback website](https://feedback.reactivedrop.com/) or at [our support email address](mailto:support@reactivedrop.com). For example, announcing a game-related competition or event run by a third party is likely something we *will* be able to do. We are also open to proposals for in-game medals that can be earned via an achievement in another Steam game (these are not considered to be advertising).
