# Simple Rebase, Multiple Conflicts

This test case defines a base branch and a target branch that update the same file to trigger conflicts in multiple commits.

`3-simple-rebase-multiple-conflicts-baseline` is a branch that contains a `CHANGELOG.md` file with some release notes.

`3-simple-rebase-multiple-conflicts-base-branch` builds upon the baseline to add in two beta releases in separate commits.

`3-simple-rebase-multiple-conflicts-target-branch` builds upon the baseline to add in two production releases in separate commits.

By rebasing `3-simple-rebase-multiple-conflicts-target-branch` onto `3-simple-rebase-multiple-conflicts-base-branch` the user will need to resolve conflicts in multiple commits, and the end result should be a unified changelog.
