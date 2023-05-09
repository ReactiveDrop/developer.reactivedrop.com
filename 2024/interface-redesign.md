# 2024 Interface Redesign

Alien Swarm: Reactive Drop's user-interface is aging, both due to the incremental approach we've used for making changes and due to changes in how players expect game user interfaces to act in the past 14 years. Therefore, we are redesigning the entirety of Alien Swarm: Reactive Drop's user interface for the 7th anniversary update, with some parts changing more than others.

The interfaces within the game are split between Menus (accessible from the moment the game is opened) and In-Game (accessible while connected to a server). The interfaces are then further divided within those two categories.

The overall goals of the redesign are:

- Bring AS:RD's user interface to match modern standards.
- Ensure important information for new players is immediately visible.
- Maintain access to all currently-existing player functionality.
- Ensure all UI works and is comfortable for any player count and on any common screen aspect ratio (4:3, 5:4, 16:9, 16:10, 21:9, ultra-wide)
- Maintain and expand mod-ability.

## Menus

### Main Menu

The main menu has, for a long time, been just a list of places away from the main menu that players are encouraged to go. There's a large amount of blank space on the main menu that could be better used to advertise trending workshop addons, new game updates, upcoming unlocks for the player, Heroes of the Interstellar Armed Forces, and maybe some live global stats.

Taking cues from Dota 2, Team Fortress 2, and CS:GO, this screen works best if the buttons players need to click are clearly labelled and in a consistent place (we will be adopting the power button style of exit button, the gear for settings, etc.) and the main content of the screen is interesting to look at but ignorable if you've seen it many times.

Additionally, only a small fraction of players read update notes, so highlighting major updates on the main menu may be a good use of space.

We'll create multiple new looping background videos for the main menu, with the first being an improved version of the current Landing Bay themed one and others being brand new (themed on other campaigns?)

The way the main menu chooses background videos will be moddable, with options to keep or remove the "vanilla" ones and support for multiple mods adding videos without overriding each other.

### Loading Screens

Loading screens have very little content, and therefore very little to adjust. Changes here are going to mostly relate to when things go wrong - loading screens need the ability to abort loading, and need to be better at telling players what went wrong and why when a player is disconnected.

### Settings

Alien Swarm: Reactive Drop's settings screens are a mess due to having been added and re-added over the course of multiple decades of Source Engine. The goal for this redesign is to make it closer to what modern multiplayer Source Engine games (CS:GO, Dota 2) use, with everything accessible from one tabbed settings screen with a custom layout and inline previews.

### Lobby List / Server Browser

The server browser is completely disconnected from the lobby browser, doesn't give anyone any ability to moderate it, and has some features that have broken over time (such as the tag list). Meanwhile, the lobby browser is hard to navigate, confusing to new players, and uses design cues from Left 4 Dead 2's lobby browser, which was designed to work well on a far-away television screen, whereas AS:RD is generally played on a much closer computer or Steam Deck screen. We've also added a lot of functionality to the lobby list without moving existing things around.

### Mission Chooser

The mission chooser is mostly in a good state already, but could use some minor touch-ups.

### Swarmopedia

We'll be splitting the medals tab out and making it part of [inventory management](inventory-management.html) and renaming "Collections" to "Swarmopedia" and the Swarmopedia tab to "Aliens". Additionally, we'll be adding a tab that contains information about obtainable Steam inventory items, a tab that contains information about marines, and a tab that contains general articles that can be about anything (predominantly lore). Apart from the changes to tabs, the Swarmopedia is mostly in a good state already.

### Stats / Achievements / Leaderboards

The global statistics on the weapon selection screen have been received well by new players, and the web version of the leaderboards is fairly popular. The current in-game representations of leaderboards and achievements, however, need a lot of work, and we don't really have an in-game way of viewing interesting personal or global stats other than the weapon selection screen.

### Workshop / Addons

The interface for configuring workshop and manually-installed addons in Alien Swarm: Reactive Drop is the bare minimum and needs to be updated to be more smoothly usable.

## In-Game

### Briefing

The briefing screen was not built with 8 player lobbies, multiple teams, medals, unique weapons, unique marine suits, and so on in mind. There is a very good 8 player lobby redesign on the Workshop, but the author has declined to make it part of the game, preferring to keep creative control over it.

We're going to make a brand new briefing screen that can handle everything the game currently has and hopefully most of what we throw at it in the future.

### Debriefing / Transition

TODO.

### Heads-Up Display

TODO.

### Closed Captions

TODO.

### Objectives

TODO.

### Hacking / Computers / PDAs

TODO.

### Spectating

TODO.

### Deathmatch

TODO.
