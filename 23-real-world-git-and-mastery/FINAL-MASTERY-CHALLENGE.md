# Git Essentials — Final Mastery Challenge

## Purpose

This is the final practical assessment.

It is intentionally different from the lessons.

You are given a repository and a task.

You are **not** given a command-by-command recipe.

Your job is to investigate, plan, act, verify and recover.

---

# Rules

You may use:

- the repository README;
- Git's built-in help;
- official Git documentation;
- normal terminal documentation;
- your course notes.

You may not ask the instructor:

> “What exact command should I type?”

You may ask for clarification about the business requirement or task itself.

---

# Official Assessment Repository

The official final assessment is the **PaakowTronics Service Desk Final Mastery** repository:

**https://github.com/PaakowTronics/paakowtronics-service-desk-final-mastery**

This repository was created specifically for learners who have studied the **Git Essentials** course. It is not another lesson. It is a realistic environment in which you demonstrate independent Git skills.

The repository contains:

- existing commits and history;
- multiple lines of work represented by branches;
- project and Service Desk documentation;
- a prepared integration/conflict situation;
- remote-tracking information;
- a controlled recovery exercise introduced by the instructor.

## Before you start

1. Read the repository's `README.md`.
2. Read `FINAL-MASTERY-CHALLENGE.md` in the assessment repository.
3. Follow the documented setup instructions.
4. Do not modify the prepared source repository directly; work in the assessment repository created by the setup process.
5. Treat the repository documentation as part of the assessment.

The repository's own instructions are the source of truth for the current assessment environment.

---

# Mission 1 — Orient Yourself

Without changing anything, determine:

- where you are;
- whether this is a Git repository;
- current branch;
- repository status;
- recent history;
- available branches;
- configured remotes.

### Requirement

Explain what you discovered before proceeding.

---

# Mission 2 — Understand the Project

Read the README.

Determine:

- what the project does;
- how it is structured;
- what change you have been asked to make;
- whether there are setup or test instructions.

If setup is required, follow the documentation.

---

# Mission 3 — Create Isolated Work

Create an appropriate branch for your task.

Make the requested change.

Before committing:

- inspect the changes;
- check the repository status;
- review the diff.

Then create a meaningful commit.

---

# Mission 4 — Investigate Another Line of Work

The repository contains another branch with related work.

Your task is to understand:

- what it changed;
- which commits are involved;
- whether it should be integrated.

Do not integrate blindly.

Inspect first.

---

# Mission 5 — Integrate

Bring the required work together.

If Git reports a conflict:

1. inspect the conflict;
2. understand both changes;
3. make an intentional decision;
4. resolve the conflict;
5. inspect the result;
6. complete the integration;
7. verify the final history.

---

# Mission 6 — Recovery Test

The instructor introduces an appropriate mistake.

Examples may include:

- an accidental local edit;
- an unnecessary staged change;
- a mistaken recent commit;
- a branch pointer problem;
- a seemingly lost commit.

Your task is to investigate and recover.

### Important

Do not immediately run a destructive reset.

First gather evidence.

Use:

```text
status
history
diff
reflog
```

or other appropriate inspection tools.

---

# Mission 7 — Remote Awareness

The repository has a remote.

Determine:

- what the remote represents;
- whether your local branch tracks a remote branch;
- whether your local information is current;
- what would happen if you pushed.

Do not push destructive changes merely to prove that you can.

---

# Mission 8 — Final Verification

Before declaring the work complete, verify:

- correct branch;
- clean or intentionally modified working tree;
- expected commits exist;
- expected changes exist;
- conflict is resolved;
- no accidental files were committed;
- history makes sense;
- remote relationship is understood.

---

# Final Explanation

The learner must explain, in plain language:

1. What was the repository state when you started?
2. What did you change?
3. Why did you create the branch?
4. What commits did you create?
5. How did you integrate work?
6. Did you encounter a conflict?
7. How did you resolve it?
8. What mistake did you recover from?
9. What evidence proves the final state is correct?
10. What would you do differently if you repeated the task?

---

# Pass Standard

A learner demonstrates mastery when they can complete the challenge without command-by-command instruction.

The key question is not:

> “Did they remember every command?”

The key question is:

> **“Could they solve the problem?”**

---

# Instructor Observation Sheet

| Skill | Observed independently? | Notes |
|---|---|---|
| Repository orientation | | |
| Documentation use | | |
| State inspection | | |
| Branching | | |
| Committing | | |
| History inspection | | |
| Integration | | |
| Conflict resolution | | |
| Recovery | | |
| Verification | | |
| Explanation | | |

---

# Final Reflection

Complete these sentences:

> Before this course, I thought Git was...

> Now I understand Git as...

> When I get stuck, my first step is...

> When I make a mistake, I will...

> When I do not know a command, I will...

> The Git skill I am most confident about is...

> The skill I still need to practise is...

---

# Completion Statement

The course is successful when the learner no longer needs a tutorial for every Git problem.

They should be able to investigate the situation, find reliable information, make a reasoned decision, perform the operation and verify the result.
