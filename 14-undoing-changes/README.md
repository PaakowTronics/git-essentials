# 14 — Undoing Changes

## Outcomes

- choose an undo strategy based on repository state;
- understand restore, revert, and reset at a conceptual level;
- avoid destructive shortcuts on shared history.

## Mental model

The right undo operation depends on whether the change is uncommitted, staged, committed, shared, and whether history preservation matters.

## Guided scenarios

Solve separately:
A. discard an uncommitted file change;
B. unstage a change;
C. reverse a shared commit with a new commit;
D. move local history backward in a disposable repository.

## Practice drills

For each scenario, first write the current state and desired state. Then choose the operation. Finally verify.

## Break-It lab

In a disposable repository, perform a controlled reset and observe the history. Do not use an important repository.

## Challenge

A bad commit is already on a shared branch. Explain why rewriting shared history can disrupt collaborators and choose a safer approach.

## Assignment

Create an 'undo decision table' with at least eight scenarios and justify the operation selected in each.

## Check guidance

Credit reasoning. There is not one universal undo command.

