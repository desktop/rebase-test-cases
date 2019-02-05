# 1 - Simple Rebase, No Conflicts

This test case defines a base branch and a target branch that update unrelated files.

 - `1-simple-rebase-base-branch` is a branch that has some changes to it's `README.md` file that have not reached `master`.

 - `1-simple-rebase-target-branch` is a branch that adds a `CONTRIBUTING.md` file to the same folder.

Rebasing  `1-simple-rebase-target-branch` onto `1-simple-rebase-base-branch` should create a linear history with both files in the same folder.

To test this on the command line:

```shellsesssion
$ git rebase 1-simple-rebase-base-branch 1-simple-rebase-target-branch
```

This should complete without error, so it's not really useful for testing before `1.7.0` where the UI to initiate a rebase is planned.
