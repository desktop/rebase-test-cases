# Simple Rebase, One Conflict

This test case defines a base branch and a target branch that update the same file.

`2-simple-rebase-conflict-base-branch` is a branch that has chosen the MIT license for the `LICENSE.md` file.

`2-simple-rebase-conflict-target-branch` is a branch that has chosen the MPL license for the `LICENSE.md` file.

Rebasing `2-simple-rebase-conflict-target-branch` onto `2-simple-rebase-conflict-base-branch` will trigger a conflict, asking the user to choose which license they want to use. Once that is resolved, the application should let the user continue and complete the rebase.

To test this on the command line:

```shellsesssion
$ git rebase 2-simple-rebase-conflict-base-branch 2-simple-rebase-conflict-target-branch
```

When you encounter this error, you should be able to switch over to Desktop and see that it correctly detects that you're in a rebase and that there are conflicts.

One interesting note here is whether the user chooses the MIT license (the base branch) or the MPL license (the target branch). If the user chooses the MIT license, there are no other changes to be added, so Git will ask the user to skip the commit as part of rebasing. The application will need to handle this scenario correctly.
