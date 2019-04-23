# Gitignore change on base branch

This test case defines a base branch that contains a `gitignore` change which
impacts the target branch.

 - `5-gitignore-base-branch` is a branch with a nested `.gitignore` file which
 ignores all `.txt` files from Git.

 - `5-gitignore-target-branch` has diverged from `5-gitignore-base-branch` to
 commit two empty `.txt` files.

The goal here is to ensure a rebase works as expected.

First, checkout `5-gitignore-target-branch`

Then, b efore performing the rebase, create a new empty file at `5-gitignore-on-base-branch/untracked-file.txt`.

Confirm with `git status` that this file is visible to Git.

Now, try and rebase `5-gitignore-target-branch` on `5-gitignore-base-branch`.
There should be two commits to rebase.

Ensure you have `rebase.autostash` set to `true, otherwise Desktop will block
the rebase from starting because of uncommitted changes.

The rebase should apply cleanly, but because of the `.txt` rule added to the
base branch the new `untracked-file.txt` should not be visible to Git.
