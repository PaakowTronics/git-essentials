# 16 — Working With Other People — Practice Drills

## Drill philosophy

These drills simulate real collaboration rather than isolated commands.

Use:

```text
PREDICT → INSPECT → ACT → VERIFY → EXPLAIN
```

Whenever possible, work with a test repository and a second GitHub account/fork or a local simulation.

Never use production repositories to practice destructive history operations.

---

## Mission 1 — Branch or fork?

For each scenario, decide whether the first structural choice should be a branch or a fork.

### Scenario A

You are a member of your company's repository and have permission to contribute.

### Scenario B

You want to contribute a bug fix to a public project you do not control and cannot directly push to.

### Scenario C

Two developers on the same repository need independent feature work.

### Scenario D

You want your own GitHub-hosted copy of a public project to experiment with independently.

### Explain

For each answer, explain why the other option is less appropriate.

---

## Mission 2 — Build a real fork workflow

Use a public repository that explicitly permits contributions.

### Task

1. Fork the repository on GitHub.
2. Clone your fork.
3. Inspect the remote.
4. Add the original repository as `upstream`.
5. Verify both remotes.

Use:

```bash
git remote -v
```

### Evidence

Your final remote map should be understandable as:

```text
origin   → my fork
upstream → original repository
```

Do not continue until you can explain why these directions matter.

---

## Mission 3 — Fork synchronization investigation

### Scenario

The upstream repository has new commits.

Your fork is behind.

You also have local work on a feature branch.

### Predict

What could go wrong if you simply run random pull commands?

### Investigate

Collect:

```bash
git status
git branch -vv
git remote -v
git log --oneline --decorate --graph --all -n 30
```

### Plan

Write down whether you would:

- fetch;
- merge;
- rebase;
- push;
- or do something else.

Do not perform the operation until you can explain why.

---

## Mission 4 — Create a focused contribution

Create a branch for one small, realistic change.

Examples:

```text
docs/improve-installation
fix/validation-message
feature/search-filter
```

Make a change small enough that a reviewer can understand it quickly.

Create one or more meaningful commits.

### Verify

Your branch should tell a coherent story:

```text
base
 ↓
focused change
 ↓
verification
```

---

## Mission 5 — Open a pull request like a professional

Push your branch and open a pull request against the intended base.

Your PR description must contain:

```text
Problem
Why
What changed
Testing/verification
Reviewer focus
Known limitations
```

### Verify

Before asking for review, check:

- correct base repository;
- correct base branch;
- correct head repository;
- correct head branch;
- expected changed files;
- expected commits;
- no secrets;
- no unrelated files.

---

## Mission 6 — Review a pull request

Use a real public PR or a second account/test repository.

Review it as if you were responsible for production quality.

Inspect:

- description;
- commits;
- changed files;
- checks;
- issue linkage;
- security implications.

Write at least:

- one correctness observation;
- one scope/maintainability observation;
- one testing observation;
- one security question.

The goal is not to manufacture criticism. If something is good, say why.

---

## Mission 7 — Simulate requested changes

Have a second contributor/account review your PR and request a specific change.

Then:

1. understand the request;
2. make the smallest appropriate change;
3. verify it;
4. push the update;
5. respond to the reviewer.

### Reflection

Did you need to rewrite existing history to satisfy the review?

Explain why or why not.

---

## Mission 8 — Understand merge strategies

Using a disposable repository, create a small PR and inspect the available merge methods.

Research the repository's configured policy.

Explain the consequences of:

- merge commit;
- squash merge;
- rebase merge.

### Predict

Before merging, draw the expected commit graph for each strategy.

### Verify

After each experiment in a disposable repository, inspect:

```bash
git log --oneline --decorate --graph --all
```

Do not perform history experiments on a shared production branch.

---

## Mission 9 — Issue to implementation workflow

Create a practice issue describing a real problem.

Include:

```text
Problem
Expected behavior
Actual behavior
Reproduction/evidence
Acceptance criteria
```

Then create a branch and implement the change.

Connect the PR to the issue using the repository's supported GitHub workflow.

### Verify

Can another developer follow the chain?

```text
issue → branch/commits → PR → checks/review → merge
```

---

## Mission 10 — Labels, assignees, milestones and Projects

In a practice repository, inspect these features where available.

For each, explain:

- what it represents;
- who uses it;
- how it differs from a Git branch;
- how it helps organize work.

Then design a small project board for:

```text
Backlog
In progress
Review
Done
```

Do not confuse project status with Git branch state.

---

## Mission 11 — Permission investigation

### Scenario

You can clone a repository but cannot push to its default branch.

### Task

Do not change credentials.

Investigate these possibilities:

```text
Authentication
Authorization
Repository role
Branch protection/rules
Pull-request requirement
Organization policy
```

Write a diagnosis tree before testing.

### Mastery question

Why does successful `ssh -T git@github.com` not prove that you can push to a particular repository?

---

## Mission 12 — Protected branch simulation

Use a repository where you have administrative control.

Configure a rule that requires changes to go through a pull request or equivalent review protection supported by the repository.

Then try a direct push from a test branch/workflow.

### Goal

Observe the difference between:

```text
Git operation is valid
```

and:

```text
Repository policy permits the operation
```

### Verify

Record the rejection message and identify whether it is primarily:

- Git syntax;
- authentication;
- authorization;
- branch/repository policy.

---

## Mission 13 — GitHub Actions investigation

Find a repository with a visible Actions workflow.

Open a workflow run.

Identify:

- event that triggered it;
- workflow name;
- jobs;
- steps;
- successful checks;
- failed checks, if any;
- logs.

### Explain

What is Git doing?

What is GitHub doing?

What is the workflow runner doing?

These are not the same layer.

---

## Mission 14 — Failed CI investigation

Use a disposable workflow or an existing failed public workflow.

Your task is not to fix it immediately.

First classify the failure:

```text
Git history problem?
Dependency problem?
Application test failure?
Lint failure?
Build failure?
Workflow configuration failure?
Environment failure?
Permission/security issue?
```

Then identify the exact log line or step that supports your diagnosis.

---

## Mission 15 — Fork security scenario

### Scenario

A pull request comes from a fork. The workflow requests access to repository secrets.

### Task

Before approving anything, investigate:

- who controls the source branch;
- what code would execute;
- what permissions the workflow has;
- whether secrets are exposed;
- whether the workflow requires approval;
- whether the repository's policy permits the workflow.

### Explain

Why can code from a fork be considered untrusted even when the pull request itself looks legitimate?

---

## Mission 16 — Two-person collaboration simulation

Use two GitHub identities or a fork plus an alternate contributor workflow.

### Person A

Creates an issue and opens a feature branch.

### Person B

Reviews the resulting PR.

### Person A

Responds to requested changes.

### Person B

Re-reviews and approves.

### Final verification

Both contributors must be able to explain:

```text
who changed what
which repository they pushed to
which branch contained the work
which repository/branch the PR targeted
what checks ran
what review decisions were made
what finally entered the target branch
```

---

## Mission 17 — Origin/upstream rescue

### Scenario

A contributor says:

> “I accidentally pushed my feature branch to the original project instead of my fork.”

### Investigation

Ask for:

```bash
git remote -v
git branch -vv
git status
```

Determine:

- what `origin` means in this repository;
- whether an `upstream` remote exists;
- where the branch was pushed;
- whether repository policy was violated;
- what should happen next.

Do not prescribe a destructive fix before understanding the repository's history and team policy.

---

## Mission 18 — PR quality challenge

Take a deliberately poor pull request and improve it.

The poor PR should contain:

- vague title;
- no problem statement;
- mixed unrelated changes;
- no test evidence;
- unclear target branch.

Your task:

1. identify every reviewability problem;
2. improve the branch/commits where appropriate;
3. rewrite the PR description;
4. provide evidence of verification.

---

## Break-It Exercise — Collaboration failure lab

Create a disposable repository and intentionally produce one of these conditions:

### A

Your fork's `origin` points to the upstream repository.

### B

Your `upstream` remote points to the wrong repository.

### C

Your PR contains an unrelated generated file.

### D

A required check fails.

### E

You cannot push because repository policy requires a pull request.

### F

Your feature branch is based on an outdated target branch.

For each exercise:

```text
break
→ inspect
→ diagnose
→ fix
→ verify
→ explain
```

---

## Troubleshooting Drill — Choose the layer

Classify each problem before proposing a fix.

### Problem 1

```text
Permission denied (publickey)
```

### Problem 2

SSH authentication succeeds, but GitHub says you cannot push to the repository.

### Problem 3

You opened a PR, but it contains the wrong repository's changes.

### Problem 4

The PR cannot merge because a required check fails.

### Problem 5

A fork's workflow tries to access sensitive secrets.

### Problem 6

A contributor cannot find the issue they were told to work on.

For each, write:

```text
Likely layer:
Evidence needed:
Safe first action:
```

---

## Independent Challenge — Contribute to an unfamiliar open-source repository

Choose a public repository with contribution instructions.

You are not allowed to use a tutorial that gives you a command-by-command recipe for that exact repository.

You must:

1. read the repository's README;
2. read contribution guidelines;
3. identify the correct fork/branch workflow;
4. fork the repository if appropriate;
5. clone your fork;
6. configure `origin` and `upstream` correctly;
7. choose a small contribution;
8. create a focused branch;
9. make a focused commit;
10. verify the change;
11. push to your fork;
12. open a pull request;
13. describe the change professionally;
14. respond to at least one review/check outcome.

Your final report must explain **why** you chose each major step.

---

# Mastery Check

Without notes, explain:

1. What is a branch?
2. What is a fork?
3. Why are they not the same thing?
4. What does `origin` normally mean?
5. What does `upstream` normally mean in a fork workflow?
6. What is the source/head of a pull request?
7. What is the base of a pull request?
8. What is an issue?
9. What is a review?
10. What is a required check?
11. What is GitHub Actions?
12. Why can a successful SSH test still be followed by a rejected push?
13. Why might a branch be unable to push directly to `main`?
14. Why should a fork PR be treated carefully from a security perspective?
15. What makes a pull request easy to review?
16. When should you synchronize a fork?
17. Why should you inspect remotes before changing them?
18. Why should you avoid exposing secrets to code from untrusted forks?

Then demonstrate both workflows:

```text
DIRECT
repository → branch → commit → push → PR → review → merge

FORK
upstream → fork → clone → origin/upstream → branch → commit → push → PR → review → synchronization
```

The final test is not whether you can repeat the workflow. It is whether you can **diagnose where the workflow is currently broken and choose the correct next action**.
