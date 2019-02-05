# rebase-test-cases

This repository contains a number of rebase test cases, tailored to ensure GitHub Desktop handles them appropriately as part of the upcoming rebase workflows.

In all scenarios where a conflict is encountered, the user should be able to abort the rebase which returns them to the target branch.

## Scenarios

### Simple Rebase

 - simple rebase without conflicts 
    - changes in the target branch do not overlap with the base branch
    - Desktop should display the rebase progress, and then indicate the rebase completed without encountering conflicts
 - simple rebase with simple conflict
    - changes in the target branch overlap with work in the base branch
    - Desktop should display the rebase progress, ask the user to resolve a conflict, then indicate the rebase has completed  
 - simple rebase with multiple conflicts
    - changes in the target branch overlap with work in the base branch and need significant work to resolve
    - Desktop should display the rebase progress, ask the user to resolve a conflict whenever the rebase stops, then indicate the rebase has completed  

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
