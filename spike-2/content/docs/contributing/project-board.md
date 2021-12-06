---
title: "Project Board"
draft: false
categories:
    - Documentation
tags:
    - "Project Board"
    - Contributing
---

We use a [Kanban-style project board](https://github.com/jwMaxwell/Spike-2/projects/1) to keep organized with feature and bug requests, as well as outstanding pull requests for code changes. As you follow your issue (you did file an issue for a bug report or feature request, right?) or PR, you'll notice it head through several columns in the board. Here's what they mean.

*Collaborators: Note that Issues are not automatically progressed through the board. You'll have to do that manually.*

Column|Description
---|---
Ideas|New issues go here automatically. They'll either be accepted and put in the queue or denied. **Please do not start work on these Issues until they are accepted.**
Accepted/To-Do|The queue (in no particular order) of accepted issues.
On Hold|Someone started working on it, but something else came up. This may be due to a dependency, waiting on information, or something more important came up. *Collaborators: Always comment with a reason why the issue is being put on hold when you do so.*
In Progress|Someone's working on it now. *Collaborators: Please assign the issue to yourself when you start work if it isn't already. Please start branch names with the name of the issue if applicable (e.g. `#13-info-to-wiki`). Please start commit messages with the name of the issue if applicable (e.g. `#13: Added wiki to $info`).*
Needs Review|Code is done, but a peer needs to review the work. New or Reopened PRs go here automatically. *Collaborators: Make sure you assign yourself or your chosen reviewer in a PR before moving it on.*
Reviewed|The code passed peer review, but isn't merged into `main` yet. PRs with a passing review go here automatically.
Mastered/To Be Released|The code has been merged into `main`, but not officially announced or released yet. Merged PRs go here automatically.
Released/Announced|Spike's running this and we announced it as such. *Collaborators: Feel free to archive cards in this column after a period of time.*
Won't Do|Rejected issues go here. Closed PRs with unmerged commits also go here automatically. *Collaborators: Feel free to archive cards in this column after a period of time.*