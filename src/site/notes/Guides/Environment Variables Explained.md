---
{"dg-publish":true,"permalink":"/guides/environment-variables-explained/","created":"2025-05-26T21:39:38.992+04:00"}
---


This guide will explain how to format the environment file for DoppelBot.

> [!NOTE] Before we start...
> This guide makes sure you've followed the steps in the [[Guides/Getting Started\|Getting Started]] guide and copied [the example](https://raw.githubusercontent.com/alexavil/DoppelBot/refs/heads/master/.env.example) from the repository to a `.env` file.

DoppelBot uses some environment variables which must be stored in the `.env` file. The file must be created at the root folder of the bot, where your `index.js` file is located.
#### Variables Cheat Sheet

| Variable     | Description                                                                                                                                                                                              | Example                                |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------- |
| `NAME`       | The username. <br>***Required.***                                                                                                                                                                        | `NAME=DoppelBot`                       |
| `TOKEN`      | The bot token. Get the token [here](https://discord.com/developers/applications)and store it in a safe place. <br>***Never share your token with anyone, including the developers.***<br>***Required.*** | `TOKEN=xxx`                            |
| `CLIENTID`   | The Discord application ID. Get it [here](https://discord.com/developers/applications).<br>***Required for deploying commands.***                                                                        | `CLIENTID=000`                         |
| `OWNERS`     | The user ID(s) of the bot owner(s). The list must be comma-separated.<br>Owners have access to special administrator features.<br>***Required.***                                                        | `OWNERS=000,111`                       |
| `AVATAR`     | The avatar. Can be a path to a file or a link.<br>***Optional, will use Discord's default avatar if not set.***                                                                                          | `AVATAR=./avatar.png`                  |
| `ACTIVITIES` | A list of possible bot status messages. The list must be comma-separated.<br>***Optional, status will be empty if not set.***                                                                            | `ACTIVITIES=Portal 2, Team Fortress 2` |
| `TELEMETRY`  | Activates Sentry. Accepts only `true` and `false` values.<br>***Optional, defaults to `false`.***                                                                                                        | `TELEMETRY=true`                       |
| `DEBUG`      | Activates Debug Mode. Accepts only `true` and `false` values.<br>***Optional, defaults to `false`.***                                                                                                    | `DEBUG=true`                           |


[[Home Page\|Home]]
