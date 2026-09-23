# 04 — Your First Repository

## Outcomes

- Initialize a repository.
- recognize the `.git` directory.
- inspect repository status.
- identify untracked files.
- understand that initialization does not automatically create a useful history.

## Guided lab

Create a disposable project and run:
```bash
git init
ls -la
git status
```
Investigate what changed after initialization.

## Practice drills

Create three files. Inspect status. Add content to one file. Inspect status again. Predict what Git will report before running each inspection.

## Break-It lab

Initialize a repository inside a deliberately nested directory. Use `pwd`, `ls`, and `git status` to confirm exactly which directory is the repository root.

## Challenge

Find the repository root without relying on your file manager. Explain how you know you found it.

## Assignment

Create `mountain-cafe/` with `README.md`, `menu.txt`, and `hours.txt`. Initialize Git. Leave all files untracked. Submit the output/interpretation of `git status`.

## Check guidance

Expected: `.git` exists, files are untracked, and learner can explain that Git is now initialized but no commit exists yet.

