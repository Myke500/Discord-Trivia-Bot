<img src=http://lakeys.net/triviabot/profile_t.png width=150 height=150>

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/2f6bcffc370943d4954606feb26e5873)](https://app.codacy.com/app/Lake/Discord-Trivia-Bot?utm_source=github.com&utm_medium=referral&utm_content=LakeYS/Discord-Trivia-Bot&utm_campaign=badger)

# TriviaBot
TriviaBot brings multiplayer trivia games to your Discord server! With over 3,000 questions and 24 categories, TriviaBot offers endless multiplayer trivia fun.

[__Invite TriviaBot to a server__](https://discordapp.com/oauth2/authorize?client_id=337654994461261825&scope=bot) | [Support it on Patreon](https://www.patreon.com/LakeYS) | [View updates & progress on Trello](https://trello.com/b/8QQm4ZPe/triviabot) | [Join the Discord](https://discord.gg/s3vCQba)
------------ | ------------- | ------------- | -------------

# Development and Support
For support, questions, and comments, you can join the Discord server or contact me directly at contact@LakeYS.net. You can also [submit an issue](https://github.com/LakeYS/Discord-Trivia-Bot/issues/new) for bugs and support.

# Features
- Access to a complete database of over 3,000 categorized, multiple-choice trivia questions. (Thanks to [OpenTDB](https://opentdb.com))
- Works across simultaneous channels and Discord servers. (For example, large servers can have multiple trivia channels)
- Responsive game system that automatically adapts to the player count.
- Single-player trivia games via DM.
- Easy to install and configure for server owners that wish to host the bot themselves.
- Play in random categories or choose a category to play in.
- A dynamic scoring system.
- Multiple modes of play to choose from.

# How to Install
If you'd like to install and host TriviaBot yourself, you can find out how to do so [here](http://lakeys.net/triviabot/install.html).

Support for custom questions is available for self-hosted bots.

# Commands
- `trivia play <category>` - The command to start a trivia game.
- `trivia help` - Shows information about the bot.
- `trivia categories` - Sends you a list of categories via DM.
- `trivia stop`

# Configuration
- The bot can be configured by editing config.json. See below for documentation on the config options.

# Game Configuration
- disable-admin-commands - Disables all commands that are only usable by administrators. (for example, the "trivia stop" command)
- use-reactions - Enables reaction mode. In reaction mode, answers are given using reactions rather than typed responses. NOTE: Reaction mode games can also be started using the 'trivia play advanced' command.
- hangman-mode - Enables hangman mode. In this mode, answers are given by typing them out rather than choosing from a list of choices. NOTE: Hangman games can also be started using the 'trivia play advanced' command.
- prefix - The prefix that users must type before each command. For example, changing this to "!" means users will need to type "!help" for the help command.
- hide-difficulty - When enabled, games will not show their difficulty color. The embed will be blue instead.
- auto-delete-msgs - The bot will automatically delete all of its messages after 15 seconds. The bot does not delete users' messages.
- auto-delete-answers - The bot will automatically delete players' typed answers. Does not apply to reaction mode.
- auto-delete-answers-timer - Approximate time in milliseconds until the bot deletes answers when auto-delete-answers is enabled. 0 being as quickly as possible. Accuracy may vary by network.
- round-length - How long each round lasts in milliseconds.
- round-timeout - The amount of time between rounds in milliseconds.
- round-end-warnings-disabled - Disables the "game will end if nobody participates" warnings.
- rounds-end-after - How many inactive rounds (where no answers are given) are allowed before a game automatically ends.
- disable-score-display - Prevents the bot from displaying users' scores. Games will still be scored internally.
- score-value - How many points are awarded for each question, based on difficulty.
- score-multiplier-max - Allows for setting a bonus multiplier for questions. Bonuses are given based on how many other players get the question incorrect. Default is 1, which has no effect. Recommended value is 2 for balance.
- command-whitelist - A whitelist of users that can use commands. 
Example: ["Lake#4898", "LakeTest#9924", "Cake#7123"]

# Global Configuration
- allow-eval - When enabled, the console will accept commands and JavaScript code. This is disabled by default due to known issues with the bot starting up.
- debug-mode - Debug mode for testing purposes. When enabled, the correct answer to each question will be marked.
- shard-count - How many shards will be spawned. This is only necessary if the bot is in over 2,000 guilds. See the Discord sharding documentation for more information.
- disable-version-check - When enabled, the application will not check for new versions on startup. It is strongly recommended that this stays enabled unless there is a severe problem with the version check.
- allow-bots - Whether other bots are allowed to provide answers. Please be mindful and avoid spamming the Open Trivia Database with unnecessary requests.
- databaseURL - The database URL you want to use. See Setting Up Custom Questions for more info. If using the http or https protocol, the server behind it must be functionally identical to the Open Trivia Database API.
- database-merge - For use with file-based custom trivia databases. Allows the use of custom trivia questions along with OpenTDB questions. See Setting Up Custom Questions for more info.
- database-cache-size - How many questions the bot will cache on startup. Max: 50
- stat-file - Which file to store statistics in.
- embed-color - The default color that the bot's embeds will use.
- channel-whitelist - If any channels are specified, the bot will only work in those channels. Can specify either a channel name or an ID. Example: "channel-whitelist": [ "trivia-dev", "trivia-dev2", "261705677943209984" ]

# Maintenance Configuration
A lot of the options in this section are deprecated and/or unused. Here are the ones that are still in use:
fallback-mode - When enabled, the bot will start in "fallback mode". The bot will not send any messages in fallback mode. Message IDs are displayed in the console.
fallback-silent - Disables the message ID display while in fallback mode.
fallback-exceptions - Channels where the bot will still send messages while in fallback mode.
Changing Configuration Using Commands
Setting the config-commands-enabled option to true enables the admin "trivia config" and "trivia reset" admin commands.

trivia config <option> <value> <channel (optional)>

The "trivia config" command can be used to change values in config. Values can be surrounded with quotes when necessary, for example to reset the prefix to "trivia " (trivia config prefix "trivia "). Options can be removed by typing "trivia config null".

Beware that this will change line spacing of the config file; it is recommended that you create a backup.

The "trivia reset" command restarts the bot to apply config changes. All options currently require a restart before they take effect.

Specifying a channel will cause the config to only take effect in that channel. Channel-based options are stored in Options/{channelid}_config.json in the bot's folder.
