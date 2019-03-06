# Simple Rebase, Multiple Conflicts

This test case defines a base branch and a target branch that update the same file to trigger conflicts in multiple commits.

 - `4-manual-conflict-resolution-baseline` is a branch that contains a `CONTRIBUTING.md` file with some paragraphs of text.

 - `4-manual-conflict-resolution-base-branch` builds upon the baseline to delete the `CONTRIBUTING.md` document.

 - `4-manual-conflict-resolution-target-branch` builds upon the baseline to add a new paragraph at the end of the file.

The goal here is to ensure manual conflict resolution is working as expected.

By rebasing `4-manual-conflict-resolution-target-branch` onto `4-manual-conflict-resolution-base-branch` the user will need to resolve a conflict in the commit, without being able to open an external editor.

To test this on the command line:

```shellsesssion
$ git rebase 4-manual-conflict-resolution-base-branch 4-manual-conflict-resolution-target-branch
```

The command should fail, and you should then be able to switch over to Desktop and see that it  detects that have conflicts to resolve. Once you have chosen the right option for continuing the rebase, the application should let you continue.
