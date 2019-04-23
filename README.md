# rebase-test-cases

This repository contains a number of rebase test cases, tailored to ensure GitHub Desktop handles them appropriately as part of the upcoming rebase workflows.

In all scenarios where a conflict is encountered, the user should be able to abort the rebase which returns them to the target branch.

## Scenarios

### Simple Rebase

 - [simple rebase without conflicts](https://github.com/desktop/rebase-test-cases/tree/1-simple-rebase-base-branch/1-simple-rebase-no-conflicts)
    - changes in the target branch do not overlap with the base branch
    - Desktop should display the rebase progress (even for a simple rebase), and then indicate the rebase completed without encountering conflicts
 - [simple rebase with simple conflict](https://github.com/desktop/rebase-test-cases/tree/2-simple-rebase-conflict-base-branch/2-simple-rebase-conflict)
    - changes in the target branch overlap with work in the base branch
    - Desktop should display the rebase progress, ask the user to resolve a conflict, then indicate the rebase has completed
 - [simple rebase with multiple conflicts](https://github.com/desktop/rebase-test-cases/tree/3-simple-rebase-multiple-conflicts-baseline/3-simple-rebase-multiple-conflicts)
    - changes in the target branch overlap with work in the base branch and need significant work to resolve
    - Desktop should display the rebase progress, ask the user to resolve a conflict whenever the rebase stops, then indicate the rebase has completed

### Manual resolution

 - [base branch deleted file, target branch modifies it](https://github.com/desktop/rebase-test-cases/tree/4-manual-conflict-resolution-baseline/4-manual-conflict-resolution)
    - conflict detected, but no text-base resolution available
    - Desktop should ask user which version of the file to use
    - application sets the right version and continues the rebase

### Edge cases

 - [gitignore change on base branch](https://github.com/desktop/rebase-test-cases/tree/5-gitignore-on-base-branch/5-gitignore-on-base-branch)
   - `gitignore` rules on base branch which clashes with target branch commits
   - tracked file matching pattern is included
   - untracked file matching pattern is hidden

### Complex Rebase

- complex rebase without conflicts
    - changes in the target branch do not overlap with the base branch
    - Desktop should display the rebase progress, and then indicate it has completed
 - complex rebase with simple conflict
    - changes in the target branch overlap with work in the base branch
    - Desktop should display the rebase progress, ask the user to resolve a conflict, then indicate the rebase has completed
 - complex rebase with multiple conflicts
    - changes in the target branch overlap with work in the base branch and need significant work to resolve
    - Desktop should display the rebase progress, ask the user to resolve a conflict whenever the rebase stops, then indicate

### Rebase with binary files

 - both branches modify the same image
    - conflict detected
    - application asks user to choose which version of the file to use
    - application sets the right version and continues the rebase
