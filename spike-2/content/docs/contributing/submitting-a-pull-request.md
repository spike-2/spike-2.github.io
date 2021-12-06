---
title: "Submitting a Pull Request"
draft: false
categories:
    - Documentation
tags:
    - "Submitting a Pull Request"
    - Contributing
---

So, you want to add a new feature in Spike, eh? It's a fairly simple endeavor, but please be sure to follow instructions carefully so we get all the information we need to approve this feature!

## Before You Begin Work on an Existing Issue
Please make sure that an Issue is in the `Accepted/To-Do` state before beginning work on it. You can check by looking at the Projects section of the sidebar for where it is on the Roadmap. Issues still in the `Ideas` state haven't been considered by the maintainers, so there's a chance those requests could be denied.

If you're actively working on an Issue that's in `Accepted/To-Do`, please leave a comment indicating such, and we'll move it to `In Progress` so others don't also work on it unnecessarily!

## Code Formatting
We use `prettier` for formatting code. Our settings are present in `package.json`: the defaults. Please also format your code using this tool before submitting a PR. Note that some of our files may not be formatted with prettier currently, but will be formatted when they're next edited.

To install in VS Code, open the Command Pallette (`CTRL + P` on Windows/Linux, `SHIFT + CMD + P` on Mac), then enter

```sh
ext install esbenp.prettier-vscode
```

The workspace settings present in our repository will automatically set prettier as the code formatter and enable formatting on save.

## Submitting the Pull Request

To submit a Pull Request, visit [this link](https://github.com/jwMaxwell/Spike-2/compare), or select "Pull requests" from the menu. You'll be presented with a template containing a few important questions to answer. Not all questions will pertain to all PRs.

```md
<!-- Thanks for taking the time to work on a patch! Please fill in the following. -->
<!-- We'll be in touch if we need any other information. -->
<!-- Once submitted, follow this PR's progress on the project board. -->
<!-- Notes like this are comments and won't appear in the PR. -->

**Related bugs/feature requests**
<!-- e.g. Resolves #2 -->
<!-- New bullet point for each issue if there's more than one. -->
```

Link this PR to any issues this implements. For example...

```md
+ Resolves #2
+ Resolves #6
```

```md
**Describe the changes**
<!-- A clear, concise description of the changes. -->
```

I altered the core plugin to add this functionality.

```md
**Expected behavior**
<!-- A clear, concise description of what you expect to happen. -->
```

Running `$command` should print out an "I'm a teapot" message.

```md
**Screenshots**
<!-- If applicable, add screenshots to help explain your problem -->
```

You can attach files by dragging-and-dropping them onto the editor, or by pasting them.


```md
**New npm dependencies**
<!-- If there are new npm dependencies, list them below with their versions -->
<!-- Make sure changes to package.json and package-lock.json are committed as well -->
```

List any new packages you installed. We should be able to install them with `npm install` with no issue.

+ DiscordJS version 2500
+ NewPackage version 2

```md
**Testing Instructions**
<!-- Instructions to thoroughly test this patch. -->
```

Write clear instructions to thoroughly test your contribution. PRs lacking adequate testing instructions will be closed and not investigated further. Instructions like switching to the feature branch, enabling a plugin, and `npm install` can be left out.

- [ ] Run `$command`
- [ ] Verify that `I'm a teapot` shows as a response
- [ ] Verify that `$help` shows the new `$command`
- [ ] Verify that `$help command` shows the appropriate help text

```md
**Additional context**
<!-- Add any other context about the problem here -->
```

If you have anything else to add, do so here.

Once you've completed this, Click the green `Create pull request` button. After a minute or two, the GitHub bot will add it to our project board, and you can track the progress of it from within the Issue. Please also be on the lookout for comments from the development team asking for more information or updating progress! Thank you for taking the time to make Spike better!

To learn more about the states a PR can be in on the project board, visit the [Project Board Documentation](/docs/contributing/project-board).