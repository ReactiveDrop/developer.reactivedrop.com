# IAF Intelligence API Endpoint

The IAF Intel file, accessible at `https://stats.reactivedrop.com/game_dynamic_state.bin`, holds information about the dynamic state of Alien Swarm: Reactive Drop's configuration. In the future, this will hold information about HoIAF bounties (bonus points that can be earned the first time a specific campaign is played in a time window), but for now it simply replaces the `hoiaf_participating_servers.bin` and `rd_event_config.txt` files that used to reside in the `resource` folder.

This document is intended to explain the purpose of the file, as players who pay close attention to network requests may notice it, as well as the `cfg/iicache.dat` file, which contains a copy of the latest downloaded configuration in case the server cannot be reached.

The file is a binary KeyValues file with a single root key named `II` for "IAF Intel". Each subkey of the root is a command based on its name. For now, there are only a few commands, but this will expand in the future.

## Note on Translations

In this documentation, `%LANG%` is used to refer to any [Steam language API code](https://partner.steamgames.com/doc/store/localization/languages). Because the IAF Intel file is updated independently of the game, it cannot rely on translation strings being available in the game's files. If the player's selected language is not available for some text that needs to be shown, the `english` text will be shown instead.

## `expires` (type `uint64`)

The Unix timestamp at which recipients of this file should redownload it to check for changes. The updated file will, at minimum, have a changed `expires` field. For the initial release, `expires` increases by 6 hours each time the file is updated, but this may be changed in the future. There is always exactly one of this command, and it is always the first command. The expiration timestamp is also sent as an HTTP header.

## `rankedIP` (type `int`)

An IPv4 address of a Participating Server for Heroes of the Interstellar Armed Forces. This is used to determine whether the ranked server icon should be displayed for a given lobby in the lobby browser. IP addresses are written in big endian byte order, so the highest eight bits of the number make up the first 1-3 digit number in the IP address as written, the opposite of how it is stored in the file.

## `latestPatch` (type `int`)

The date of the latest Alien Swarm: Reactive Drop Update (not including hotfixes that have no release notes or updates to other branches such as beta or releasecandidate). The date is stored as a base 10 integer, with `year * 10000 + month * 100 + day` used to compose the number. This command will appear exactly once in the IAF Intel file.

## `featuredNews` (structured)

- `caption_%LANG%` (type `string`) - The caption of the news item on the main menu.
- `url` (type `string`) - The URL that will be opened when the news item is clicked. Contains a `%s` which is replaced with the player's Steam language API code.
- `texture_url` (type `string`) - The URL of a VTF file to be shown in the news area of the main menu.
- `texture_crc` (type `int`) - The CRC32 checksum of the VTF file to check whether the client needs to re-download it.
- `texture_index` (type `int`) - The filename where the VTF file will be stored is `materials/vgui/swarm/news_showcase_[texture_index].vtf`. Between 1 and 5 for now.

News items shown in the carousel on the main menu. There are a maximum of 5 copies of this command in the IAF Intel document for now.

## `eventTimer` (structured)

- `caption_%LANG%` (type `string`) - The caption of the event timer on the main menu.
- `url` (type `string`) - The URL that wil be opened when the event timer is clicked. Contains a `%s` which is replaced with the player's Steam language API code.
- `starts` (type `uint64`) - Unix timestamp when the event starts. The timer will not appear on the main menu if the current time is before `starts`.
- `ends` (type `uint64`) - Unix timestamp when the event expires. The timer will not appear on the main menu if the current time is after `ends`.

Event timers shown on the side of the main menu. There are a maximum of 3 copies of this command in the IAF Intel document for now.

## `chatAnnouncement` (structured)

- `id` (type `string`) - Arbitrary string that identifies the announcement. Each announcement is only shown once.
- `text_%LANG%` (type `string`) - The text of the announcement.
- `not_before` (type `uint64`) - Unix timestamp before which the announcement should not be shown.
- `not_after` (type `uint64`) - Unix timestamp after which the announcement should not be shown.
- `color` (type `Color`) - Color of the message in chat (default red).
- `font` (type `string`) - Font of the message (default `ChatFont`; defined in `ChatScheme.res`).

Announcements that appear in game chat, similar to Warframe's Red Text.
