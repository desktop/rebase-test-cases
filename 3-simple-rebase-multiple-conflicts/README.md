# Simple Rebase, Multiple Conflicts

This test case defines a base branch and a target branch that update the same file to trigger conflicts in multiple commits.

`3-simple-rebase-multiple-conflicts-baseline` is a branch that contains a `CHANGELOG.md` file with some release notes.

`3-simple-rebase-multiple-conflicts-base-branch` builds upon the baseline to add in four beta releases in separate commits.

`3-simple-rebase-multiple-conflicts-target-branch` builds upon the baseline to add in four production releases in separate commits.

The goal here is to ensure each commit keeps the changelog in order while also preserving the changelog entries (because they might be the same between versions).

By rebasing `3-simple-rebase-multiple-conflicts-target-branch` onto `3-simple-rebase-multiple-conflicts-base-branch` the user will need to resolve conflicts in multiple commits, and the end result should be a unified changelog with the releases sorted from latest to earliest.

To test this on the command line:

```shellsesssion
$ git rebase 3-simple-rebase-multiple-conflicts-base-branch 3-simple-rebase-multiple-conflicts-target-branch
```

The command should fail, and you should then be able to switch over to Desktop and see that it  detects that have conflicts to resolve. Once resolved you should then continue the rebase, and have to repeat the process a few times - once you are done you will be 8 commits ahead and 4 behind, which will require a force push to resolve.
