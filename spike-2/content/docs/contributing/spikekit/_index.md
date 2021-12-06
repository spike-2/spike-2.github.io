---
title: SpikeKit
categories:
    - Documentation
tags:
    - SpikeKit
---

SpikeKit is the plugin mechanism for Spike, allowing community members to more easily add functionality to the bot. SpikeKit offers two types of plugins:

+ **Standard Plugins** accept and act upon commands given with the bot's prefix.
+ **Cron Plugins** execute code on an interval.

SpikeKit also provides plugins with a Standard Library of Functions and Constants to aid development. Please see the in-code documentation in [`spikeKit.js`](https://github.com/jwMaxwell/Spike-2/blob/main/src/spikeKit.js) for more information.

**Do not use console.log or console.error to log messages.** Instead, use the SpikeKit logger.