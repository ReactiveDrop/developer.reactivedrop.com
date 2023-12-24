# IAF Intelligence API Endpoint

The IAF Intel file, accessible at `https://stats.reactivedrop.com/game_dynamic_state.bin`, holds information about the dynamic state of Alien Swarm: Reactive Drop's configuration. In the future, this will hold information about HoIAF bounties (bonus points that can be earned the first time a specific campaign is played in a time window), but for now it simply replaces the `hoiaf_participating_servers.bin` file that used to reside in the `resource` folder.

This document is intended to explain the purpose of the file, as players who pay close attention to network requests may notice it, as well as the `cfg/iicache.dat` file, which contains a copy of the latest downloaded configuration in case the server cannot be reached.

The file is a binary KeyValues file with a single root key named `II` for "IAF Intel". Each subkey of the root is a command based on its name. For now, there are only two commands, but this will expand in the future:

## `expires` (type `uint64`)

The timestamp at which recipients of this file should redownload it to check for changes. The updated file will, at minimum, have a changed `expires` field. For the initial release, `expires` increases by 6 hours each time the file is updated, but this may be changed in the future. There is always exactly one of this command, and it is always the first command. The expiration timestamp is also sent as an HTTP header.

## `rankedIP` (type `int`)

An IPv4 address of a Participating Server for Heroes of the Interstellar Armed Forces. This is used to determine whether the ranked server icon should be displayed for a given lobby in the lobby browser. IP addresses are written in big endian byte order, so the highest eight bits of the number make up the first 1-3 digit number in the IP address as written, the opposite of how it is stored in the file.
