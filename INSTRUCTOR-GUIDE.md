# Git Essentials — Instructor Guide

## Purpose

Git Essentials is a hands-on course for taking a learner from **absolute beginner** to an **independent Git user**.

The course is not designed around memorising commands. A learner succeeds when they can enter an unfamiliar terminal or repository, understand what they are seeing, choose a sensible Git operation, verify the result, and recover when something goes wrong.

The instructor's job is therefore not to become a command dispenser. The instructor creates situations in which the learner has to **observe, reason, act, verify, and recover**.

---

# 1. Course Philosophy

The course follows this progression:

```text
Understand
    ↓
See
    ↓
Try
    ↓
Practice
    ↓
Break
    ↓
Fix
    ↓
Challenge
    ↓
Verify
```

A command should normally appear because it solves a problem the learner can already see.

Avoid teaching Git as:

```text
Here are 20 commands.
Memorise them.
```

Teach it as:

```text
Here is a repository.
Something changed.
What do you observe?
What do you expect?
What evidence do you need?
What operation could solve it?
How will you verify the result?
```

---

# 2. The Most Important Instructor Rule

## Do not rescue too quickly.

When a learner is stuck, do not immediately provide the command.

Ask questions such as:

- Where are you?
- What does `git status` say?
- What were you expecting?
- What actually happened?
- What changed immediately before the problem?
- What does the error message say?
- What evidence would confirm your theory?
- Which part of the documentation would answer this?
- What do you think will happen if you run that command?
- How will you verify it?

The goal is to build investigation habits.

---

# 3. The Predict → Run → Verify Habit

Use this throughout the entire course.

Before an important command:

### Predict

Ask:

> What do you think this will change?

Then run it.

### Observe

Ask:

> What did Git actually report?

Then verify.

### Verify

Ask:

> What evidence proves that the repository is now in the state we intended?

This habit should become automatic by Lesson 23.

---

# 4. Beginner Language Rules

The learner may be completely new to technical vocabulary.

Do not assume they know:

- repository
- working tree
- staging area
- branch
- remote
- HEAD
- commit
- ref
- upstream
- merge
- rebase
- reflog
- detached HEAD

Introduce each term before relying on it.

A good pattern is:

> **Term → plain-English meaning → small example → command → observation → practice**

For example:

> A branch is a movable name pointing to a line of commits. For now, think of it as a separate line of work that lets you develop without disturbing another line of work.

Then demonstrate it.

---

# 5. Do Not Teach From a Command List

A learner should not leave a lesson thinking:

> “I memorised seven Git commands.”

They should leave thinking:

> “I understand the problem these commands solve.”

Examples:

| Problem | Skill |
|---|---|
| I do not know what changed | Inspect repository state |
| I want to save a meaningful version | Commit |
| I need separate work | Branch |
| I need another person's changes | Fetch / pull |
| Two lines of work disagree | Merge / conflict resolution |
| I made a local mistake | Appropriate undo operation |
| I lost a commit reference | Reflog investigation |
| I need to temporarily put work aside | Stash |
| I need to reorganise commits | Rebase |
| I need one specific commit | Cherry-pick |

---

# 6. Instructor Flow for Every Lesson

Before class:

1. Read the lesson completely.
2. Run every practical exercise yourself.
3. Confirm commands are appropriate for the learner's operating system.
4. Prepare a clean repository.
5. Prepare at least one intentional mistake.
6. Know what evidence the learner should observe.
7. Do not prepare a command-by-command rescue script unless necessary.

During class:

1. Explain the goal.
2. Establish the starting state.
3. Demonstrate only enough to make the task understandable.
4. Ask the learner to predict.
5. Let the learner perform the operation.
6. Make them inspect the result.
7. Give independent practice.
8. Introduce an intentional mistake.
9. Let them investigate and recover.
10. End with a mastery check.

---

# 7. Lessons 01–04: Foundation

## Lesson 01 — Terminal

The learner should become comfortable moving around a filesystem.

Do not rush.

Make sure they understand:

```text
pwd = where am I?
ls  = what is here?
cd  = move to another folder
cd .. = go up one folder
```

The learner should be able to recover from being lost using `pwd` and `ls`.

## Lesson 02 — Documentation

This lesson is about independence.

The learner should practise:

```text
Find
→ Read
→ Understand
→ Run
→ Verify
```

They should learn to identify official documentation rather than blindly copying commands from search results.

## Lesson 03 — What Is Git?

The learner should understand:

```text
Git is a version-control system.
```

More importantly, they should understand why version control exists.

## Lesson 04 — First Repository

The learner should understand what changes when:

```bash
git init
```

is run.

They should know that a Git repository contains Git's internal data and that `git init` does not create a commit.

---

# 8. Lessons 05–08: Seeing Git's State

The key transition is:

> Stop thinking of Git as a command collection. Start thinking in terms of state.

The learner should repeatedly inspect:

```bash
git status
```

and compare versions with:

```bash
git log
git diff
```

Ask:

> What does Git know?

> What does Git not know?

> What changed?

> What is committed?

> What is only in the working tree?

---

# 9. Lessons 09–11: Branching and Integration

The learner should understand **why** branches exist before being taught advanced branch manipulation.

Use a realistic situation:

> You have working code. A second piece of work needs to happen without disturbing it.

Then introduce branches.

For merging, emphasise that two lines of history can become one history.

Do not introduce conflict resolution as a mysterious error.

A conflict means:

> Git needs a human to decide between incompatible changes.

---

# 10. Lessons 12–16: GitHub and Collaboration

Do not treat GitHub as if it were Git.

Explain:

```text
Git = version-control system
GitHub = hosted service for Git repositories and collaboration
```

Learners should understand:

```text
local repository
      ↕
remote repository
```

and the difference between:

```text
commit
push
fetch
pull
clone
```

Use multiple repositories where possible.

---

# 11. Lessons 17–19: Conflict and Recovery

These lessons are critical.

A learner who can only create clean commits is not yet independent.

Give them broken situations.

Examples:

- conflicting edits
- wrong branch
- accidental local changes
- mistaken commit
- missing commit reference

The instructor should resist the temptation to fix the repository personally.

The learner should investigate.

---

# 12. Lessons 20–22: Advanced Operations

Stash, rebase and cherry-pick should be taught as tools for specific situations.

Do not present rebase as a magical “better merge.”

Explain what it changes and why someone might choose it.

For rebase:

```text
Understand the original history
        ↓
Understand the new base
        ↓
Understand that commits are replayed
        ↓
Predict the resulting history
        ↓
Run
        ↓
Inspect
```

For cherry-pick:

> “I need this particular commit, not necessarily the entire branch.”

That problem should come before the command.

---

# 13. Lesson 23 — Real-World Git and Mastery

This lesson should feel different.

The learner should receive less instruction.

Give them:

- an unfamiliar repository
- a README
- a task
- a broken or incomplete state
- a small amount of context

Then step back.

The learner should:

1. inspect the repository
2. understand the current branch
3. inspect history
4. identify changes
5. create or switch branches where appropriate
6. make changes
7. commit
8. integrate work
9. recover from at least one mistake
10. explain what they did
11. verify the final state

---

# 14. How to Handle Mistakes

Never treat every error as failure.

Use errors as evidence.

For example:

```text
fatal: not a git repository
```

Ask:

> What does Git mean by “repository”?

Then:

> Where are you?

Then:

```bash
pwd
ls -la
```

The learner should discover the problem.

---

# 15. When to Give the Answer

Give the exact command when:

- the learner has demonstrated the concept but is blocked by syntax;
- the task is not intended to test recall;
- continuing without the command would waste time;
- safety or destructive consequences make guessing inappropriate.

Even then, ask them to predict the effect before execution.

---

# 16. Assessment

Do not grade learners primarily on command memorisation.

Evaluate:

### Understanding
Can they explain what Git is doing?

### Observation
Can they inspect repository state?

### Decision-making
Can they choose an appropriate operation?

### Execution
Can they perform the operation?

### Verification
Can they prove the result?

### Recovery
Can they investigate and recover from mistakes?

### Independence
Can they work without command-by-command instructions?

---

# 17. Signs the Learner Is Ready

A learner is progressing well when they naturally say things like:

> “Let me check `git status` first.”

> “I want to inspect the log before changing anything.”

> “I think this will create a conflict.”

> “Let me verify the branch.”

> “The error tells me I am probably in the wrong directory.”

> “I don't remember the syntax, so I will check the documentation.”

These behaviours matter more than speed.

---

# 18. Instructor Anti-Patterns

Avoid:

- command dumping
- unexplained jargon
- fixing repositories for learners
- saying “just run this”
- rewarding memorisation over understanding
- skipping verification
- hiding errors
- turning every exercise into a copy-and-paste exercise
- teaching destructive commands without explaining consequences
- treating GitHub and Git as the same thing

---

# 19. Final Instructor Standard

At the end of the course, the learner should be able to face:

```text
I have a repository.
I don't fully understand it.
Something is wrong.
I need to make a change.
I am not sure which Git operation I need.
```

and respond:

```text
I will inspect the repository.
I will read the relevant documentation.
I will form a hypothesis.
I will predict the effect of my operation.
I will make the change.
I will verify the result.
If it goes wrong, I will investigate and recover.
```

That is the target.


# 18. Official Final Mastery Assessment

The course's final practical assessment is conducted in the **PaakowTronics Service Desk Final Mastery** repository:

**https://github.com/PaakowTronics/paakowtronics-service-desk-final-mastery**

This is the standard assessment environment for learners who have completed Git Essentials. It replaces the idea of a generic instructor-created `mastery-project` with a consistent, reusable repository that learners can access and instructors can reset.

## Instructor preparation

Before assigning the assessment:

1. Give the learner the repository link.
2. Ask the learner to read the repository `README.md` and `FINAL-MASTERY-CHALLENGE.md`.
3. Have the learner follow the documented setup process.
4. Confirm the learner starts from the prepared `main` branch.
5. Keep the instructor answer key private.
6. Use the repository's reset/recovery tooling when preparing a new attempt.

## Instructor role

Do not turn the assessment into a command-recitation exercise. The learner should investigate the repository, read the documentation, make decisions, verify results, and recover from mistakes.

You may clarify the business scenario or assessment requirement, but avoid providing the exact command unless the situation genuinely requires syntax assistance rather than testing the learner's reasoning.

## What the assessment should demonstrate

The learner should be able to:

- orient themselves in an unfamiliar repository;
- inspect status, history, branches, and remotes;
- read and use repository documentation;
- make an appropriate change on an isolated branch;
- inspect and integrate existing work;
- resolve a realistic conflict;
- investigate and recover from a controlled mistake;
- understand local/remote relationships;
- verify the final state;
- explain the reasoning behind their actions.

The final question is not whether the learner remembered every command. It is whether they can **solve the Git problem and prove that they solved it safely.**
