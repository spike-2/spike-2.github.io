---
title: "Core"
draft: false
categories:
    - Documentation
tags:
    - "Core"
    - Manual Pages
---

This module contains some of the core functions of Spike.

## `$remindme`

`$remindme [HH:MM:SS] [text]`  
Sends a reminder message to the same channel in the given time.

## `$embedify`

`$embedify [title] ; [content]`  
Creates a message embed with the given title and content.

## `$echo`

`$echo [text]`  
Sends a message as Spike. To use this command, you need to purchase access in the [Spike Store](/docs/manual-pages/spike-store).

## `$clear`

`$clear [2 <= x <= 100]`  
Deletes the last `x` messages from the channel, including the command invocation. You must be an administrator or Bot Expert to use this.

## `$info`

Shows information about the bot and the version currently running. This also contains the names of all contributors to the Spike-2 repository.