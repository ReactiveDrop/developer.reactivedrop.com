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
