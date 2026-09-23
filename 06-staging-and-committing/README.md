# 06 — Staging & Committing

## Outcomes

- select changes for a commit;
- create meaningful commits;
- inspect commit state;
- understand why staging is useful.

## Mental model

Staging is a selection area. It lets the learner decide exactly what the next snapshot should contain.

## Guided lab

Create two files and modify both. Stage only one. Inspect status. Commit it. Inspect status again. Determine what happened to the other file.

## Practice drills

- Stage one file.
- Stage all intended files.
- Unstage a file without losing its content.
- Create two logical commits rather than one giant mixed commit.
- Compare a meaningful message with a vague message.

## Break-It lab

Create a mixed change touching unrelated concerns. Stage only one concern. Explain why this is preferable to blindly staging everything in that scenario.

## Challenge

Build a five-commit history where each commit represents a logical project step. Another person should be able to understand the project evolution from the log.

## Assignment

Create a mini project through five meaningful commits. No empty or duplicate commits. Submit `git log --oneline` and explain each commit.

## Check guidance

Check logical separation, useful messages, and a clean final state. Do not require a particular commit-message convention unless the course later establishes one.

