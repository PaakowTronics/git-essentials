# 17 — Rebase

## Outcomes

- understand history rewriting;
- rebase a feature branch in a disposable lab;
- resolve rebase conflicts;
- understand collaboration implications.

## Mental model

Rebase replays commits onto a different base and can create new commit identities. It changes history rather than merely adding a merge point.

## Guided lab

Create divergent histories, rebase a feature onto updated main, inspect the resulting graph, and compare it with a merge-based integration.

## Practice drills

- simple rebase;
- rebase with a conflict;
- inspect rewritten commit IDs;
- interactive rebase in a disposable repository to edit/squash/reorder.

## Challenge

Compare merge and rebase for a shared branch. Identify why rewriting history can be disruptive.

## Assignment

Produce two equivalent integrations—one merge, one rebase—in separate disposable repositories and explain the resulting graphs.

## Check guidance

Never encourage force-pushing shared history as a casual exercise. If force push is discussed, teach the risks and safer variants in a controlled lab.

