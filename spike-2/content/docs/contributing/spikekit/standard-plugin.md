---
title: "Standard Plugin"
draft: false
categories:
    - Documentation
tags:
    - "Standard Plugin"
    - SpikeKit
    - Contributing
---

Standard Plugins accept and act upon commands given with the bot's prefix.

## To start developing a SpikeKit Standard Plugin

1. Fork this repository to create your own working copy.
2. Copy `/src/plugins/blueprintPlugin` and rename the folder to something unique.
3. Edit `main.js` and add supplementary files as required.
4. Submit a Pull Request with your plugin.
5. Spike Collaborators will review your plugin and suggest any required changes.
6. Once approved, your plugin will go live with the next update of Spike.

## Required Blueprint Items

The items that appear in the blueprint plugin are required for your SpikeKit Plugin to function correctly. Nothing else should be exported from the `main.js` module.

+ `const NAME` - {`string`} The display name of your plugin.
+ `const SLUG` - {`string`} Slug used to programmatically refer to the plugin. Lowercase letters, numbers, and dashes only.
+ `const AUTHOR` - {`string`} The author(s) of your plugin.
+ `const COMMANDS` - {`string[]`} The commands your plugin supports. Do not include the prefix.
+ `function help(prefix, command, args)` - Handles help requests for commands in your plugin.
  + Returns a string containing relevant help information.
  + `prefix` - {`string`} The current prefix being used by the bot.
  + `command` - {`string`} The command the user is requesting help about.
  + `args` - {`string`} The rest of the message.
+ `function shortHelp(prefix)` - Handles the message your plugin displays on the main help screen.
  + Returns the string to be shown on the main help screen. This should be a summary of your commands. Extensive help text should be provided for each command via `help()`.
  + `prefix` - {`string`} The current prefix being used by the bot.
+ `function processCommand(command, args, bot, message)` - Handles the commands your plugin supports.
  + Does not return anything. You should instead send messages via SpikeKit as required.
  + `command` - {`string`} The command issued, without the prefix.
  + `args` - {`string`} The rest of the message.
  + `bot` - {`Discord.Client`} The instantiated Discord Client for use in SpikeKit functions.
  + `message` - {`Discord.Message`} The instantiated Discord Message representing the user's message for use in SpikeKit functions.

## Optional Blueprint Items
+ `function processReaction(reaction, user, add, bot)` - Handles reactions added/removed to/from embeds sent by this plugin.
  + For `processReaction` to be called on a plugin...
    + `processReaction` must be exported
    + Message reacted to must be an embed sent through Spike or Simone
    + Message must be cached. That means it's either been sent since the bot started or is manually cached
    + Title of embed must start with (case insensitive) `${NAME}:{space}`
    + Reaction must've been added or removed by a user other than Spike or Simone
  + Does not return anything. You should instead send messages via SpikeKit as required.
  + `reaction` - {`Discord.MessageReaction`} Message Reaction object for the reaction added/removed.
  + `user` - {`Discord.User`} User who applied reaction / User whose reaction was removed
  + `add` - {`boolean`} True if reaction added, False if removed
  + `bot` - {`Discord.Client`} The instantiated Discord Client for use in SpikeKit functions.
+ `function onBotStart(bot)` - Runs when the bot starts
  + Only runs if exported from the plugin module
  + `bot` - {`Discord.Client`} The instantiated Discord Client for use in SpikeKit functions.