# 1 - Simple Rebase, No Conflicts

This test case defines a base branch and a target branch that update unrelated files.

`1-simple-rebase-base-branch` is a branch that has some changes to it's `README.md` file that have not reached `master`.

`1-simple-rebase-target-branch` is a branch that adds a `CONTRIBUTING.md` file to the same folder.

Rebasing  `1-simple-rebase-target-branch` onto `1-simple-rebase-base-branch` should create a linear history with both files in the same folder.
