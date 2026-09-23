# 03 — What Git Actually Is

## Outcomes

- Explain version control in plain language.
- distinguish working tree, staging area, local repository, and remote.
- explain what a commit represents.
- explain the purpose of GitHub without confusing it with Git.

## Mental model

Use this model:
```text
Working tree → Staging area → Local repository → Remote repository
```
A file can be modified without being staged. A change can be staged without being committed. A commit can exist locally without being pushed.

## Guided exercise

Imagine editing `README.md`. Describe the state after:
1. editing;
2. staging;
3. committing;
4. pushing.

Do this without typing commands first.

## Practice drills

### Drill A
Explain "uncommitted" in your own words.

### Drill B
Explain why a local commit is not automatically a GitHub commit.

### Drill C
Draw the four-state model on paper.

### Drill D
Given five scenarios, identify whether the change is working-tree, staged, committed, or remote.

## Challenge

A learner says: "GitHub is Git." Correct the statement without simply quoting a definition.

## Assignment

Write a plain-language explanation of Git for a non-developer. It must explain repository, commit, branch, and remote without using unexplained jargon.

## Check guidance

Look for correct distinctions, especially the fact that Git is version control software and GitHub is a hosting/collaboration service built around Git repositories.

