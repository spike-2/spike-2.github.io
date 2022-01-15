---
title: "Style Guide"
draft: false
categories:
    - Documentation
tags:
    - "Style Guide"
toc: true
---
This style guide should be followed for all code contributed to the Spike bot. When a specific rule is not specified here, use the existing code base as a guide, and keep your style to the spirit of the existing code.

## Automated Formatting: Prettier
We use the Prettier formatter to automatically format all code in the code base. We started using this tool midway through Spike development, so some files may not be formatted currently, but will be when they are next edited.

Our settings are present in `package.json`: the defaults. Please also format your code using this tool before submitting a PR. Note that some of our files may not be formatted with prettier currently, but will be formatted when they're next edited.

To install in VS Code, open the Command Pallette (`CTRL + P` on Windows/Linux, `SHIFT + CMD + P` on Mac), then enter

```sh
ext install esbenp.prettier-vscode
```

The workspace settings present in our repository will automatically set prettier as the code formatter and enable formatting on save.

## Encapsulated Functional Paradigm
// TODO

## Conventions
The following conventions to follow appear in no particular order.

### Be DRY
Don't Repeat Yourself. If you find yourself needing to use the same code in multiple places, refactor it as a function.

### Functions
Definitions of standalone functions should follow the standard JS syntax:

```js
function x(y) {

}
```

Lambda or in-line functions should use the arrow syntax when possible:

```js
(y) => {

}
```

### Documentation
Always include JSDoc style documentation with your functions. This is useful not only in understanding what a function does, but also for editors like VS Code to display helpful hints while programming. This example comes from SpikeKit:

```js
/**
 *
 * @param {string} title Title of the embed.
 * @param {string} content Content of the embed.
 * @param {boolean} [monotype=false] True if the content should be monospace (```yaml).
 * @param {string} [footer=null] Footer text of the embed.
 * @param {string} [footerImageURL=null] Fully qualified URL to image to include in footer.
 * @param {SpikeKit.COLORS} [color=COLORS.PURPLE] Color for the embed. If not defined in enum, embed will be purple.
 * @returns {Discord.MessageEmbed} Embed to send on via another function.
 */
function createEmbed(
...
```

### Use switch/case for simple selections
When a simple selection based on a value is needed (e.g. returning help text for a given command), using a `switch/case` statement is preferred over `if...else if...else` syntax.

### Never hard-code command prefixes
Always use the prefix passed through the provided mechanisms. Never assume it will always be `$`. In fact, our testing bot uses a separate prefix!

### Handle all exceptions
Handle any and all exceptions your code may produce. Never rely on a module above yours to handle them. This contributes to a highly stable bot.

All exceptions should be logged in one way or another. The log level depends on the severity of the detected exception. See the [Style Guide section on logging](#use-spikekits-logger-instead-of-the-console-logger) for more information.

### Use environment variables when necessary
Use environment variables for constants that can change from run-to-run or environment-to-environment, but not during a run of Spike. The log level of the console is a great example of this.

All environment variables should have, at minimum, their name included as part of `.env.template`. If having the variable undefined is permissible for your use case, comment out the line. If a default value makes sense for your use case, include it in the template file.

A real, non-template `.env` file should **_never_** be committed to the codebase. Precautions have been taken to avoid this, such as including the two known `.env` variants in use in the `.gitignore` file. Should a real config be committed, alert maintainers immediately so that secrets can be changed.

### Use SpikeKit functions, not Discord.js functions
SpikeKit functions serve as a stable base to build on top of. Should Discord.js change how a certain function works, it is much more maintainable to change it once rather than change it in dozens of places. If there isn't a SpikeKit analog for a function you'd like to use, add one.

### Use SpikeKit's logger instead of the console logger
Logging with SpikeKit is powered by [Winston](https://github.com/winstonjs/winston). This allows us to selectively log things that happen and better respond to errors in Spike. **Do not use `console.log` or `console.error` to log messages.** Visit the [SpikeKit Logging page](/docs/contributing/spikekit/logging/) for more guidance on using it.

### Use the correct message sending function for the purpose
Use `spikeKit.reply()` when an action is the result of a message in the same channel. This associates the reply with the initial request.

Use `spikeKit.send()` for timed or delayed messages; when the message initiating the action is deleted as a result of the action; or when the message initiating the action is in a different channel from where the resulting message is sent.

### Use the correct embed color for the result
Use `spikeKit.COLORS.PURPLE` as the embed color for successful commands. Use `spikeKit.COLORS.RED` as the embed color for failed commands. This provides a consistent experience for our users and an easy way to detect errors.

### Use SpikeKit as a common messenger
If multiple modules need to share data, use SpikeKit as a messenger. This can be through shared variables directly or library functions. Use your best judgement in determining which is correct for your use case.