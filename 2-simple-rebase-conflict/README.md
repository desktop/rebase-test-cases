# Simple Rebase, One Conflict

This test case defines a base branch and a target branch that update the same file.

`2-simple-rebase-conflict-base-branch` is a branch that has chosen the MIT license for the `LICENSE.md` file.

`2-simple-rebase-conflict-target-branch` is a branch that has chosen the MPL license for the `LICENSE.md` file.

Rebasing `2-simple-rebase-conflict-target-branch` onto `2-simple-rebase-conflict-base-branch` will trigger a conflict, asking the user to choose which license they want to use. Once that is resolved, the application should let the user continue and complete the rebase.

One interesting note here is whether the user chooses the MIT license (the base branch) or the MPL license (the target branch). If the user chooses the MIT license, there are no other changes to be added, so Git will ask the user to skip the commit as part of rebasing. The application will need to handle this scenario correctly.

