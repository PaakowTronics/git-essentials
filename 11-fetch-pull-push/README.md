# 11 — Fetch, Pull & Push

## Outcomes

- distinguish fetch, pull, and push;
- synchronize two clones;
- inspect remote-tracking state;
- integrate remote work intentionally.

## Mental model

Push sends eligible local commits to a remote. Fetch updates local knowledge of remote refs without, by itself, changing the current branch's files. Pull fetches and then integrates according to the configured strategy.

## Guided lab

Clone a repository twice. Treat the directories as Developer A and Developer B. A makes and pushes a change. B fetches and investigates before integrating.

## Practice drills

- fetch without merging;
- inspect remote-tracking branches;
- integrate a fetched change;
- push a local commit;
- compare states before and after each operation.

## Challenge

Explain why fetching can be useful when you want to inspect incoming work before changing your current branch.

## Assignment

Complete a two-clone synchronization scenario and document the state at four points: before remote change, after remote push, after fetch, after integration.

## Check guidance

Learner should demonstrate conceptual understanding, not simply say "pull gets updates.

