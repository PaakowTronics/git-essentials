# 16 — Working With Other People: Forks, Pull Requests, Reviews & GitHub Collaboration

## Mission

Learn how Git and GitHub become a collaboration system when more than one person is changing the same codebase.

This lesson goes beyond “create a branch and open a pull request.” You will learn the collaboration models used in real repositories, including direct collaboration, forks, upstream repositories, pull requests, reviews, issues, project tracking, repository permissions, protected branches, automation checks, and safe communication.

The goal is not to memorize a GitHub interface. The goal is to understand the **flow of work and responsibility**.

---

## Learning outcomes

You should be able to:

- explain why teams use branches instead of everyone editing the default branch;
- distinguish a branch from a fork;
- explain direct collaborator and fork-based contribution models;
- understand `origin` and `upstream` in a fork workflow;
- clone a fork and configure the remotes deliberately;
- keep a fork synchronized with its upstream repository;
- create focused branches and commits;
- push a branch safely;
- open a pull request with a clear purpose;
- understand base repository, base branch, head repository, and head branch;
- read the changed-files and commit views of a pull request;
- understand review comments, approvals, requested changes, and conversations;
- respond to review without destroying useful history accidentally;
- understand merge options at a conceptual level;
- recognize why squashing, merging, or rebasing can have different history consequences;
- use issues to record work and bugs rather than treating them as commits;
- understand labels, assignees, milestones, and project tracking at a practical level;
- understand repository permissions and why authentication does not imply write access;
- recognize protected branches/rules and required status checks;
- understand how GitHub Actions can act as automated reviewers/checks;
- recognize security implications of pull requests from forks;
- understand why secrets must not be exposed to untrusted code;
- communicate changes so another developer can review them efficiently;
- choose between direct collaboration and fork-based contribution based on the repository's access model;
- investigate a collaboration problem before changing history.

---

# Part 1 — Collaboration starts with a shared repository model

A team is not simply several people running Git commands.

A collaboration system has:

```text
people
  ↓
repositories
  ↓
branches
  ↓
commits
  ↓
pull requests
  ↓
review/checks
  ↓
merge/release
```

Each layer has a different purpose.

## A branch is not a person

A branch is a Git reference inside a repository.

A branch does not automatically mean:

> “This belongs to Alice.”

A team may have branches named:

```text
feature/customer-search
fix/login-timeout
release/2.4
```

The branch communicates the line of work, not ownership by itself.

---

# Part 2 — Fork versus branch

This distinction is essential.

## Branch

A branch exists **inside one repository**.

```text
One repository
├── main
├── feature/login
└── fix/payment-timeout
```

Branches share the repository's history and access model.

## Fork

A fork is a **separate GitHub repository** created from another repository, commonly called the upstream repository.

```text
Original repository
        │
       fork
        ↓
Contributor's repository
```

A fork has its own settings, permissions, branches, issues, pull requests, projects, and Actions context, while remaining connected to the upstream repository through GitHub's fork network.

### The simplest comparison

```text
Branch = another line of work inside the same repository
Fork   = another repository derived from an existing repository
```

Never describe a fork as “just a branch on GitHub.”

---

# Part 3 — Two common collaboration models

## Model A — Direct collaboration

You have permission to contribute to the repository.

```text
GitHub repository
      │
      ├── main
      ├── feature/a
      └── feature/b

Developer A ──┐
Developer B ──┼── same repository
Developer C ──┘
```

A developer can:

1. clone the repository;
2. create a branch;
3. commit;
4. push the branch;
5. open a pull request;
6. receive review;
7. merge according to project rules.

## Model B — Fork-based collaboration

You do not normally push branches directly to the upstream repository.

```text
                 upstream repository
                        │
                       fork
                        ↓
                 contributor fork
                        │
                      clone
                        ↓
                  local repository
                        │
                      branch
                        ↓
                     commits
                        │
                       push
                        ↓
                 contributor fork
                        │
                  pull request
                        ↓
                 upstream repository
```

Fork workflows are common for open-source projects and other environments where contributors are not granted direct write access.

---

# Part 4 — `origin` and `upstream`

These names are conventions, not Git keywords.

In a fork workflow, a common arrangement is:

```text
origin   → your fork
upstream → original repository
```

For example:

```text
origin   git@github.com:YOUR-ACCOUNT/project.git
upstream git@github.com:ORIGINAL-OWNER/project.git
```

Inspect them:

```bash
git remote -v
```

Add upstream when appropriate:

```bash
git remote add upstream git@github.com:ORIGINAL-OWNER/project.git
```

Then verify:

```bash
git remote -v
```

### Important

Do not assume that `origin` means “the official repository.”

`origin` only means:

> “the remote repository associated with the local name `origin`.”

---

# Part 5 — Keeping a fork synchronized

A fork can become stale.

The upstream repository may receive commits while your fork remains unchanged.

A common conceptual workflow is:

```text
upstream changes
      ↓
fetch upstream
      ↓
inspect
      ↓
synchronize your branch
      ↓
push updated branch to origin
```

The exact integration strategy depends on the branch, project policy, and whether you have local work.

Never synchronize blindly.

Before integrating upstream changes, inspect:

```bash
git status
git branch --show-current
git remote -v
git log --oneline --decorate --graph --all -n 30
```

Then decide whether merge, rebase, or another operation is appropriate.

---

# Part 6 — Feature branches and focused commits

A collaboration branch should have a purpose.

Weak:

```text
my-work
stuff
changes
new
```

Better:

```text
feature/customer-search
fix/session-timeout
docs/setup-linux
```

Commit history should help reviewers understand the change.

A focused commit answers:

> “What coherent change does this commit represent?”

Avoid mixing:

```text
feature implementation
+ unrelated formatting
+ dependency upgrade
+ typo fixes
+ personal config
```

unless those changes genuinely belong together.

---

# Part 7 — What a pull request actually is

A pull request is a GitHub collaboration object proposing changes from one branch/repository into another.

A pull request has a source and a destination.

Think in four parts:

```text
HEAD repository
HEAD branch
      │
      │ proposed changes
      ↓
BASE repository
BASE branch
```

For direct collaboration:

```text
same-repository feature branch
            ↓
       main/default
```

For a fork workflow:

```text
your-fork:feature/login
          ↓
original-repository:main
```

The exact labels shown by GitHub may vary with the workflow, but the conceptual model remains.

---

# Part 8 — A good pull request is a review package

A pull request should answer:

1. What problem does this solve?
2. Why is the change needed?
3. What changed?
4. What did you test?
5. What should the reviewer pay particular attention to?
6. Are there known limitations or follow-up tasks?

A strong description reduces reviewer guesswork.

## Bad PR description

```text
fixed stuff
```

## Better

```text
Problem:
Customers could submit a search form without a query.

Change:
Added server-side validation and a user-facing error.

Verification:
Tested empty, whitespace-only, and valid queries.

Reviewer focus:
Please check validation behavior for existing API clients.
```

---

# Part 9 — Reading a pull request as a reviewer

Do not review only the final files.

Investigate:

- conversation;
- commits;
- changed files;
- additions/deletions;
- checks;
- linked issues;
- branch/base information;
- deployment previews where available;
- security implications.

Ask:

### Correctness

Does the code solve the stated problem?

### Scope

Does it change more than necessary?

### Maintainability

Will the next developer understand it?

### Tests

Is the behavior verified appropriately?

### Security

Could the change expose credentials, bypass authorization, introduce injection, or create unsafe behavior?

### Operations

Could this break deployment, migrations, configuration, or monitoring?

A review is not merely a spelling check.

---

# Part 10 — Review states

A reviewer may:

- comment;
- approve;
- request changes.

These are different signals.

## Comment

“I have a question/observation.”

## Approval

“I reviewed this and am satisfied enough under the repository's review policy.”

## Request changes

“The change should not be merged until specific concerns are addressed.”

The exact merge requirements depend on repository rules.

---

# Part 11 — Responding to review

When review identifies a problem:

```text
read feedback
    ↓
understand the concern
    ↓
make the change
    ↓
verify
    ↓
push new commit(s)
    ↓
respond to review
```

Do not rewrite history simply because a reviewer requested a typo fix.

History rewriting is a separate decision.

A mature contributor asks:

> “What history does the team expect this repository to preserve?”

---

# Part 12 — Merge strategies: understand the consequences

GitHub can offer different ways of integrating a pull request, depending on repository settings.

Conceptually, you may encounter:

### Merge commit

Preserves the branch topology by creating a merge commit.

### Squash merge

Combines the pull request's changes into a new commit on the target branch.

### Rebase merge

Replays commits onto the target branch and integrates the resulting linear history.

The right choice depends on project policy.

Do not assume one strategy is universally superior.

Before rewriting or deleting branches, understand what other people may still depend on.

---

# Part 13 — Issues are not commits

GitHub Issues are for work tracking and discussion.

Use an issue to record things such as:

- bug reports;
- feature requests;
- investigations;
- tasks;
- questions;
- follow-up work.

A useful issue usually includes:

```text
Problem
Expected behavior
Actual behavior
Reproduction steps
Environment/context
Evidence
Acceptance criteria
```

## Connecting issues and pull requests

A team can connect a PR to an issue so the relationship between:

```text
problem → implementation → review → completion
```

is visible.

Do not assume that closing an issue and merging a PR are the same operation. They are related workflow events.

---

# Part 14 — Labels, assignees, milestones and Projects

These features help teams organize work.

### Labels

Categorize issues and pull requests.

Examples:

```text
bug
security
documentation
priority-high
good-first-issue
```

### Assignees

Indicate who is responsible for moving work forward.

### Milestones

Group issues/PRs around a target or release objective.

### Projects

Provide broader planning views across GitHub work items.

A student does not need to master every project-board configuration. They should understand that GitHub can manage work **around** the Git repository, not just the Git history itself.

---

# Part 15 — Permissions and roles

A collaboration problem is often an access problem.

A person may be able to:

- view a repository;
- clone it;
- open an issue;
- open a pull request;
- comment;
- push a branch;
- merge a PR;
- change repository settings;

without necessarily having all of the other permissions.

Repository roles and organization policies determine what actions are allowed.

The practical debugging rule is:

```text
Authentication proves identity.
Authorization determines allowed actions.
```

If a push fails, do not immediately regenerate credentials.

Investigate:

1. Who am I authenticated as?
2. Which repository am I targeting?
3. Do I have access?
4. Is the target branch protected?
5. Are required checks/reviews missing?
6. Is an organization policy involved?

---

# Part 16 — Protected branches and rules

Important repositories commonly protect important branches.

Rules may require things such as:

- pull requests instead of direct pushes;
- approving reviews;
- passing status checks;
- resolving conversations;
- linear history;
- signed commits;
- restrictions on who can push.

This means:

```text
git push
```

can be technically correct while the repository still rejects the operation because policy says:

> “Changes must go through the review workflow.”

That is not necessarily a Git error.

It can be a repository policy decision.

---

# Part 17 — GitHub Actions as automated review infrastructure

GitHub Actions runs automated workflows.

A common pull-request pipeline is:

```text
Pull request opened/updated
          ↓
GitHub Actions
          ↓
install dependencies
          ↓
lint
          ↓
test
          ↓
build
          ↓
report status
```

A failing check does not necessarily mean Git is broken.

It may mean:

- the code fails tests;
- linting failed;
- the build failed;
- an environment is misconfigured;
- a workflow itself is broken.

The learner should inspect the workflow run and identify **which layer failed**.

## Fork security

Workflows triggered by pull requests from forks deserve special attention because contributor-controlled code can run in an environment with varying permissions.

Never assume that a fork PR is trusted code.

Never expose sensitive repository secrets to untrusted code merely to make a workflow convenient.

Repository Actions settings and workflow permissions should be designed deliberately.

---

# Part 18 — The direct collaboration workflow

A mature direct-collaboration workflow can look like:

```text
issue/problem
     ↓
understand acceptance criteria
     ↓
update local repository safely
     ↓
create feature/fix branch
     ↓
make focused changes
     ↓
run tests/checks
     ↓
commit meaningful history
     ↓
push branch
     ↓
open pull request
     ↓
automated checks
     ↓
human review
     ↓
respond to feedback
     ↓
merge according to policy
     ↓
verify target branch
     ↓
clean up branch if appropriate
```

The exact order can vary, but the reasoning remains.

---

# Part 19 — The fork workflow

A common open-source contribution workflow is:

```text
1. Find upstream repository
2. Fork on GitHub
3. Clone your fork
4. Add upstream remote
5. Inspect repository instructions
6. Create a focused branch
7. Make changes
8. Commit
9. Push branch to your fork
10. Open pull request to upstream
11. Respond to review
12. Keep branch synchronized if needed
13. Merge according to upstream policy
```

The key remote relationship is:

```text
origin   = your fork
upstream = original repository
```

Do not reverse them accidentally.

---

# Part 20 — Communication is part of version control

A technically correct change can still be a poor contribution if nobody understands it.

Before asking someone to review a change, make sure:

- the branch has a clear purpose;
- commits are understandable;
- the PR description explains the problem;
- tests are reported;
- known limitations are disclosed;
- screenshots/logs/evidence are included when useful;
- reviewers know what kind of feedback you want.

Good collaboration reduces the amount of information another developer must reconstruct.

---

# Part 21 — Common collaboration failures

## “I pushed to main by accident.”

Investigate repository rules and history before attempting cleanup.

## “My fork is months behind.”

Inspect remotes and synchronize deliberately.

## “My PR includes hundreds of unrelated changes.”

Investigate branch ancestry, base branch, working tree state, and accidental changes.

## “The PR check failed.”

Inspect the actual workflow run. Do not immediately change Git history.

## “I cannot push, but SSH works.”

Authentication succeeded. Investigate authorization, repository access, branch rules, and target remote.

## “The maintainer says my fork PR is unsafe.”

Investigate workflow permissions, secrets, untrusted code, and repository policy. Do not assume the concern is about Git syntax.

---

# Part 22 — Collaboration investigation checklist

Before changing anything:

```text
Where am I?
What repository am I in?
What is my current branch?
What is the target branch?
What remotes exist?
Which remote is upstream?
Which remote is my fork?
What is the PR base?
What is the PR head?
What changed?
What checks ran?
What failed?
What permissions do I have?
What repository rules apply?
What history must be preserved?
```

Then choose the smallest appropriate action.

---

# Command reference

## Inspect branches

```bash
git branch
git branch -a
git branch -vv
git log --oneline --decorate --graph --all -n 30
```

## Inspect remotes

```bash
git remote -v
git remote show origin
git remote show upstream
```

## Add upstream

```bash
git remote add upstream <UPSTREAM-URL>
```

## Fetch upstream

```bash
git fetch upstream
```

## Push a feature branch

```bash
git push -u origin <branch-name>
```

## Update local information

```bash
git fetch --all --prune
```

Do not confuse fetching with integrating changes.

---

# Practical vocabulary

| Term | Meaning |
|---|---|
| repository | A Git project/history; on GitHub, a hosted repository plus platform features |
| branch | A Git reference representing a line of development |
| fork | A separate GitHub repository derived from another repository |
| upstream | Common local name for the original repository in a fork workflow |
| origin | Common local name for the repository a clone came from; in a fork workflow, often your fork |
| issue | GitHub work/discussion record |
| pull request | GitHub proposal to integrate changes |
| review | Human evaluation of a pull request |
| check | Automated result associated with a change/PR |
| Actions | GitHub automation system |
| project | GitHub work-planning system |
| release | GitHub presentation/distribution of a version, often associated with a tag |
| protected branch/rule | Repository policy controlling how changes may reach important branches |

---

# Mastery standard

You are ready to leave this lesson when you can do both of these workflows without a recipe.

## Direct collaboration

```text
clone → branch → commit → push → PR → checks → review → merge
```

## Fork collaboration

```text
fork → clone → origin/upstream → branch → commit → push → PR → review → synchronization
```

You must also be able to explain:

- branch versus fork;
- origin versus upstream;
- authentication versus authorization;
- issue versus commit;
- pull request versus merge commit;
- check versus review;
- GitHub Actions versus Git itself;
- repository access versus branch protection.

Most importantly, when collaboration fails, you should investigate **the repository, remotes, branches, permissions, policies, and evidence** before changing history.
