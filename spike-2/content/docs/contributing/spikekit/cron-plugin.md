---
title: "Cron Plugin"
draft: false
categories:
    - Documentation
tags:
    - "Cron Plugin"
    - SpikeKit
    - Contributing
---

Cron Plugins execute code on an interval.

## To start developing a SpikeKit Cron Plugin

1. Fork this repository to create your own working copy.
2. Copy `/src/plugins/blueprintCronPlugin` and rename the folder to something unique.
3. Edit `main.js` and add supplementary files as required.
4. Submit a Pull Request with your plugin.
5. Spike Collaborators will review your plugin and suggest any required changes.
6. Once approved, your plugin will go live with the next update of Spike.

## Required Blueprint Items

The items that appear in the blueprint plugin are required for your SpikeKit Plugin to function correctly. Nothing else should be exported from the `main.js` module.

+ `const NAME` - {`string`} The display name of your plugin.
+ `const SLUG` - {`string`} Slug used to programmatically refer to the plugin. Lowercase letters, numbers, and dashes only.
+ `const AUTHOR` - {`string`} The author(s) of your plugin.
+ `function startCron(bot)` - Called to start tasks on an interval.
  + `bot` - {`Discord.Client`} The instantiated Discord Client for use in SpikeKit functions.
  + This function will be called on bot start.
  + You should only use asynchronous functions for timing, such as `setInterval` and `setTimeout`.
  + The `AsyncInterval` class is provided as an alternative for `setInterval` when dealing with `async` functions.

## `AsyncInterval`

This class is provided as a convenience to mimic `setInterval` with asynchronous functions.

+ Constructor: `new AsyncInterval(cb, interval)`
  + `cb` - {`function`} The callback function for the interval.
  + `interval` - {`number`} The interval in milliseconds (> 0) to wait between executions.
    + `spikeKit.SECOND`, `spikeKit.MINUTE`, and `spikeKit.HOUR` are provided for convenience.
+ `async start()` - Starts the task.
  + Note: If the task is stopped with `stop()`, you must first set the interval to the desired value explicitly (`myAsyncInterval.interval`). Otherwise, this function acts the same as `runOnce()` in this scenario.
+ `async runOnce()` - Awaits the callback function once.
+ `stop()` - Stops the task. Any scheduled runs will still run, but no new ones will be scheduled.

See the [`itsServiceNotes` plugin](https://github.com/jwMaxwell/Spike-2/tree/main/src/plugins/itsServiceNotes) for an example usage of `AsyncInterval`.