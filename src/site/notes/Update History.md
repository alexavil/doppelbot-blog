---
{"dg-publish":true,"permalink":"/update-history/","created":"2025-03-29T23:11:14.753+04:00"}
---

These patch notes are preserved for historic purposes.

### DoppelBot Hotfix - April 16, 2025

- Fixed the 25 track & tag limit.
	- Interactions which depend on this limit may now display the "Previous" and "Next" buttons.
- Every track is now saved into a cache database.
- When using `/upload` to upload a track, you can now give it a user-friendly display name.
- Improved duplicate track detection.
	- DoppelBot will now verify the MD5 Hash against the database.
	- DoppelBot will now correctly keep track of deleted files.
- Cancelling a menu will no longer disconnect the bot if a track is currently playing.
- Added an emergency `/disconnect` command (same rules as for stop).
- Added character limits to tags.
	- A key phrase can be 256 characters long.
	- A tag response can be 1024 characters long.
- Added [[Privacy Policy\|Privacy Policy]] and [[Update History\|Update History]] links to the About command.

### DoppelBot Anniversary Update 2025, Part 1 - April 3, 2025

#### General

- ***BREAKING CHANGE / NEW FEATURE:*** Removed text-based commands. Most existing commands can now be executed with the newest Discord features including, slash commands, buttons, modals and menus. 
- ***BREAKING CHANGE / NEW FEATURE:*** Instance owners can now customize DoppelBot's name, avatar, games and other settings without the Developer Portal. 
	- [To edit the settings, please see this example file.](https://raw.githubusercontent.com/alexavil/DoppelBot/refs/heads/master/.env.example)
- You can now add multiple responses for a tag.
	- Please use the following format:
	  `response1`
	  `---`
	  `response2`
	- Responses will be chosen randomly.
- All tags can now be managed and wiped separately from settings.
- Settings and tags embeds now update automatically.
- Removed Backup/Restore.

#### Music Player Changes

- ***NEW FEATURE:*** The bot can now play local music files.
	- Local files must be uploaded to the bot's music cache.
	- The bot currently accepts `*.flac`, `*.mp3`, `*.ogg`, `*.wav`, and `*.m4a` files. More file types will be added in the future updates.
	- Files can be uploaded via the new `/upload` command or when you select a track to play.
	- Due to Discord's limitations, you can upload one file at a time. However, you can select multiple tracks to play from the cache.
	- *Sharing is caring:* Files will stay in the cache indefinitely and can be accessed by all guilds. There is currently no cache size limitation.
	- Instance owners can wipe the cache at any time. Wiping the cache will disconnect all active players.
	- ***NOTE:*** Online functionality is currently unavailable and will be restored in Part 2 of this update.
- Play, pause, stop, seek and skip can now be used with a single `/controls` command.
	 ![controls-command.png](/img/user/Attachments/controls-command.png)
- You can no longer skip if there's only one track in the queue. Use the Stop button instead.
	- Skip is greyed out in the controls panel to indicate this.
- `/queue` now includes the name of the current server.
- Improved stability and performance.
- Changed radio transmission frequency to comply with federal and state spectrum management regulations.

#### Technical Changes

- Sentry now collects performance data, as well as bugs.
	- Sentry reporting can now be toggled on and off.
	- In Debug Mode, Sentry reporting is always on.
- Improved Realtek Mode and DoppelBot Account support.
### DoppelBot Update - April 16, 2023

- All servers now start with the healthiest API-enabled instance by default.
- Admins are now allowed to pick the best default instance by typing `d!instance best`.
- Optimized adding large playlists.
- Added `d!seek`, which will show the current position in a song, and its total length.

### DoppelBot Anniversary Update 2023 - April 15, 2023

- **BREAKING CHANGE:** Added the new music module - InvidJS. 
	- You are allowed to use any public Invidious instance with API access.
	- For searching, YouTube links and Video IDs, DoppelBot will try to fetch the source via a default instance.
	- Admins can set their preferred default instance via `d!instance`.
	- Admins can set the preferred minimum instance health via `d!health`. Default is `75`. If a provided instance has health below that point, you will be sent a warning.
- **BREAKING CHANGE:** You can now loop a track using `d!loop`. Looped tracks will play indefinitely until skipped, stopped or unlooped.
- **BREAKING CHANGE:** The music code was re-written entirely. All commands are now separated, as in Classic DoppelBot.
- **BREAKING CHANGE:** You can only stop the bot or skip a track if you're the only user left in the VC. Admins are immune to this restriction.
- You can now queue entire playlists at once.
- You can now fetch search suggestions using `d!suggest`. This command does not require being in a voice channel.
- Made the music module more verbose by reporting actual errors.
- Added Debug Mode. It allows anyone who's running a copy of DoppelBot to receive verbose logs, and only intended to be used in testing environments.
- Revamped `d!settings` - every option is now explained.
- Admins now have more options of managing their server settings and tags.
	- `d!backup` will output a JSON file with all your settings and tags.
	- `d!restore` will allow you to restore a previous backup.
	- `d!defaults` will allow you to reset your settings and tags.
- Invalid settings are now wiped automatically.
- Other bug fixes and QOL improvements.

### DoppelBot Update - 13 March 2023 

- Updated the engine to the latest version. This fixes the VC connections cutting off.

### DoppelBot Update - 22 February 2023

Fixed errors reported by Sentry:
- Age-restricted videos are no longer allowed to be added to the queue.
- Implement sanity checks in the music module.

General changes:
- Edited `d!about` with a tags notice.
- `d!tags list` is now available to all members and will not send an empty embed if there are no tags on the server.
- Ported `d!adminhelp` from Classic DoppelBot (alias: `d!ahelp`)

### DoppelBot Update - 20 February 2023

Service Changes:
- DoppelBot will now automatically report errors. **This does not collect any server data, so you are not required to give your consent.**

General:
- Responses from Classic DoppelBot are back and can now be set per server with `d!tags`.
- All commands: 
	`d!tags create` - Creates a tag (alias: `d!t c`)
	`d!tags list` - Lists all server tags (alias: `d!t l`)
	`d!tags delete` - Creates a tag (alias: `d!t d`)
- Each tag requires a key phrase and a response. Tags can't start with a guild prefix or mention.
- Guild prefix is now visible in `d!settings`. You can no longer use `d!prefix` to view it.

### DoppelBot Update - 12 February 2023

**Service Changes:**
- Service Notifications are now opt-in by default.
- Reduced the amount of permission checks.

**General:**
- Added the pause command, which will pause the current track.
- Added aliases to several commands: e.g. `d!music play` = `d!m p`, `d!music queue` = `d!m q`, `d!music skip` = `d!m s`
- Disconnect timeout can now be set per server with `d!timeout` (accepts values in seconds)
- Ported `d!settings` from Classic DoppelBot.

### DoppelBot Update - February 7th, 2023

This update includes some changes, that will be applied as soon as the bot restarts.

__***Queue has finally been added!***__
You can now put multiple songs in DoppelBot for it to play. No more fighting for getting a song into DoppelBot!

This update also features Quality of Life changes and bug fixes.

### DoppelBot Update - April 1, 2022

This updates includes some important changes, and will be applied as soon as the bot restarts.

- Fixed some commands take the knowledge?
- Fixed some features.
- Fixed some comply with Arle, I wonder?
- Defeatings, and can be turned on across all guilds, as well as overhaul of some feature: Word Filter
- Toggle configurable per guild (more on, other responses include transmission frequency to commands)
- By default, Ace Attorney responses include Realtek and off at any time.
- Added aliases for some cases for May 2, 2021
- Responses are off, mention frequency to commands are off, and prefix can now be configured per guilds by default.

We would also like to inform users that it feels like I've become Legacy. Today you will include Realtek and Ina Unravel responses are on, other bots' mentions.

Thanks for supporting us!

### DoppelBot Update - October 20, 2021

- Fixed some cases of Engrish
- Added aliases for some commands
	- d!play = d!p
	- d!about = d!help
	- d!setprefix = d!prefix
	- Toggle commands take the last part as alias
- Changed radio transmission frequency to comply with federal and state spectrum management regulations.

### DoppelBot Update - May 14, 2021

- New Feature: Word Filter
	- Configurable per guild.
	- By default, it's **on** across all guilds, and can be turned on and off at any time.
	- `https://discordgift.site/` is banned across all guilds by default.
- Separated regular and administrator commands
	- Administrator commands are now available via `d!admhelp`
- Removed the Ina Unravel response.
- Updated localization files.

### DoppelBot Update - May 2, 2021

- New initiative: Server Settings.
	- Responses and bot prefix can now be configured per guild (more options coming soon!).
	- By default, Ace Attorney responses are **off**, mention responses are **on**, other responses are **off**, and prefix is set to "d!".
	- Other responses include Realtek and Ina Unravel responses.
- DoppelBot no longer listens to DMs or other bots' mentions.
- Updated localization files.

[[Home Page\|Home]]