---
{"dg-publish":true,"permalink":"/guides/getting-started/","created":"2025-04-09T17:28:08.000+04:00"}
---


DoppelBot is a free and open-source Discord bot for entertainment, with capabilities of playing music files and responding to the users' custom responses (known as "tags").

We encourage the bot to be self-hosted. Please follow this guide to install the bot.

> [!warning]
> Please read the [[Privacy Policy\|Privacy Policy]] before hosting the bot.
>
> Usage of some functions and commands may be restricted in some countries, such as Russia.
> Please host the bot in a neutral location.

### Basic Installation

1. [Create a new Discord application.](https://discord.com/developers/applications)
2. Install the latest version of Node.js and npm.
3. Clone our repository: `git clone https://github.com/alexavil/DoppelBot`
4. `cd` to the directory, for example `cd DoppelBot`.
5. Install all dependencies via `npm install`.
6. Create the `.env` file and fill it out according to [the example](https://raw.githubusercontent.com/alexavil/DoppelBot/refs/heads/master/.env.example).
7. Deploy the commands by running `node utils/deploy.js`.
8. Launch the `index.js` file: `node index.js`.

[[Home Page\|Home]]
