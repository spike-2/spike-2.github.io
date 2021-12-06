---
title: "Bug Reports"
draft: false
categories:
    - Documentation
tags:
    - "Bug Reports"
    - Contributing
---

So, you've found a bug in Spike and want to report it, eh? It's a fairly simple endeavor, but please be sure to follow instructions carefully so we get all the information we need to reproduce and fix the bug!

To submit a Bug Report, visit [this link](https://github.com/jwMaxwell/Spike-2/issues/new?assignees=&labels=bug&template=bug_report.md&title=), or file a new issue and select "Bug Report" from the menu. You'll be presented with a template containing a few important questions to answer.

```md
<!-- Thanks for taking the time to report a bug! Please fill in the following. -->
<!-- We'll be in touch if we need any other information. -->
<!-- Once submitted, follow this issue's progress on the project board. -->
<!-- Notes like this are comments and won't appear in the report. -->


**Describe the bug**
<!-- A clear, concise description of the bug -->
```

Write a sentence or two explaining what went wrong.

```md
**To Reproduce**
<!-- Steps to reproduce the bug -->
```

1. I ran this command
2. I clicked this
3. This happened

```md
**Expected behavior**
<!-- A clear, concise description of what you expect to happen -->
```

This other thing should've happened.

```md
**Screenshots**
<!-- If applicable, add screenshots to help explain your problem -->
```

You can attach files by dragging-and-dropping them onto the editor, or by pasting them.

```md
**Runtime Info**
<!-- Run `$info` and copy the commit ID Spike is currently running -->
```
Go into any channel Spike is in, and run `$info`. You'll see an information embed like this:

![Screenshot of $info output](https://i.imgur.com/igMOoHF.png)

Copy and paste the value next to `Commit ID:` for the appropriate bullet point, as below.

```md
+ Commit ID: 2d2b552
```

When you submit the issue, this will automatically link to the commit Spike is running.

```md
<!-- Platform(s) and app version(s) of Discord used -->
```

This is to list what platform(s) and app version(s) you used to generate this bug. You can usually find this value in the settings. Please be sure to include your OS version as well in case there's a platform-specific discord issue causing this.

```md
+ App(s) Accessing Discord: Linux 64-bit v.0.0.15 (Linux 5.11.0-7620-generic), Android v.84.15 (Android 11)
```

```md
**Additional context**
<!-- Add any other context about the problem here -->
```

If you have anything else to add, do so here.

Once you've completed this, Click the green `Submit New Issue` button. After a minute or two, the GitHub bot will add it to our project board, and you can track the progress of it from within the Issue. Please also be on the lookout for comments from the development team asking for more information or updating progress! Thank you for taking the time to make Spike better!

To learn more about the states an issue can be in on the project board, visit the [Project Board Documentation](/docs/contributing/project-board).