---
title: "Logging"
draft: false
categories:
    - Documentation
tags:
    - "Logging"
    - SpikeKit
    - Contributing
---

Logging with SpikeKit is powered by [Winston](https://github.com/winstonjs/winston). This allows us to selectively log things that happen and better respond to errors in Spike. **Do not use `console.log` or `console.error` to log messages.** Instead, use one of the log levels below with the SpikeKit logger.

## Log Levels

Log levels in SpikeKit go along with npm convention. Here are the log levels we use, in order of highest to lowest priority:

Level | Function Call | Meaning
---|---|---
Error|`spikeKit.logger.error(message)`|Something definitely went wrong with the bot.
Warning|`spikeKit.logger.warn(message)`|Something went wrong. It might be user error, might be something wrong in the code, or might not be a real issue.
Info|`spikeKit.logger.info(message)`|Something went wrong, but it was user error and didn't actually break anything. For example, invalid syntax for a command.
Verbose|`spikeKit.logger.log("verbose", message)`|Info, but longer
Debug|`spikeKit.logger.log("debug", message)`|This is only really useful if you're actively developing.
Silly|`spikeKit.logger.log("silly", message)`|You wanted someone to maybe eventually see this, but they probably won't ever.

## Transports

Transports are how the Spike maintainers get these logged messages. Here are the current transports and the lowest priority they receive. Please keep these in mind while choosing between log levels.

- Console (the terminal where Spike is running): Info
- Discord (a special channel available to maintainers): Warning
- Combined Log (rotated monthly or at 20mb, whichever first; 3 files kept): Info
- Error Log (rotated monthly or at 20mb, whichever first; 3 files kept): Warning