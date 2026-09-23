# 05 — Understanding Changes

## Outcomes

- inspect repository state;
- distinguish untracked and modified files;
- read a diff;
- compare expected and actual changes.

## Mental model

`git status` gives a high-level state report. `git diff` shows unstaged content differences. The learner should use both rather than guessing.

## Guided lab

Create `story.txt`, commit it, then modify one paragraph. Run `git status` and `git diff`. Explain what each command tells you.

## Practice drills

1. Modify one file.
2. Modify two files.
3. Stage one and leave one unstaged.
4. Compare the staged and unstaged parts using the appropriate inspection commands.
5. Predict output before each command.

## Break-It lab

Create a file that contains an accidental change. Your task is to determine whether it should be kept or discarded based on the diff, not the filename.

## Challenge

Given three modified files, produce a written change report with file name, state, and exact nature of change.

## Assignment

Create a three-file project and make a different change to each. Prepare one change for commit and leave two outside the staging area. Provide evidence.

## Check guidance

Learner must distinguish `git status` from `git diff` and demonstrate that staging changes what a plain `git diff` reports.

