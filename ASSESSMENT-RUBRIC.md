# Git Essentials — Assessment Rubric

## Purpose

This rubric measures practical Git competence.

It intentionally avoids treating command memorisation as the main measure of success.

A learner can forget the exact syntax of a command and still be highly competent if they know:

1. what problem they are solving;
2. where to find the correct documentation;
3. what the operation is supposed to do;
4. how to execute it safely;
5. how to verify the result;
6. how to recover if something goes wrong.

---

# Level 1 — Beginner

The learner:

- recognises basic terminal commands;
- can follow a demonstration;
- can create a repository;
- can make simple commits with guidance;
- can read basic `git status` output;
- still depends heavily on step-by-step instructions.

Typical behaviour:

> “Tell me what command to run.”

This is a normal starting point.

---

# Level 2 — Developing

The learner:

- understands basic Git vocabulary;
- can inspect repository state;
- can create branches;
- can make commits independently in familiar exercises;
- can read simple history;
- can follow documentation;
- can troubleshoot simple mistakes with hints.

Typical behaviour:

> “I think I know what is wrong, but I need some help confirming it.”

---

# Level 3 — Capable

The learner:

- works independently in familiar repositories;
- chooses appropriate basic Git operations;
- understands local and remote repositories;
- can push, fetch, pull and clone;
- can merge branches;
- can resolve straightforward conflicts;
- can undo common mistakes;
- verifies important operations;
- uses documentation instead of guessing.

Typical behaviour:

> “Let me inspect the state first, then I'll decide what to do.”

---

# Level 4 — Independent

The learner:

- can enter an unfamiliar repository;
- understands the current state without a scripted walkthrough;
- forms a plan before acting;
- predicts the effect of important operations;
- uses Git history as evidence;
- handles conflicts;
- recovers from mistakes;
- can use reflog when appropriate;
- understands stash, rebase and cherry-pick;
- can explain trade-offs between operations;
- verifies the final state;
- can continue learning without an instructor.

Typical behaviour:

> “I don't know the exact command yet, but I know what I need to find out and where to look.”

This is the target level.

---

# Skill Dimensions

## 1. Terminal Navigation

### Beginner
Can follow navigation commands.

### Developing
Can navigate familiar structures.

### Capable
Can independently find and manipulate files.

### Independent
Can recover when lost and reason from filesystem evidence.

---

## 2. Documentation

### Beginner
Can follow a provided documentation link.

### Developing
Can locate a relevant section.

### Capable
Can install or configure software by following official documentation.

### Independent
Can investigate unfamiliar tools, compare instructions, verify results and troubleshoot documentation-related problems.

---

## 3. Repository State

### Beginner
Recognises that Git reports repository changes.

### Developing
Can interpret basic `git status`.

### Capable
Can accurately describe working-tree and staging state.

### Independent
Can inspect an unfamiliar repository and form a reliable mental model before changing anything.

---

## 4. History

### Beginner
Can view recent commits.

### Developing
Can inspect a particular commit.

### Capable
Can compare versions and use history to answer questions.

### Independent
Uses history as an investigation and recovery tool.

---

## 5. Branches

### Beginner
Can follow a branch demonstration.

### Developing
Can create and switch branches.

### Capable
Can independently use branches for isolated work.

### Independent
Can reason about branch pointers and choose an appropriate branching strategy for a task.

---

## 6. Integration

### Beginner
Can follow a merge demonstration.

### Developing
Can perform a simple merge.

### Capable
Can resolve ordinary conflicts.

### Independent
Can diagnose why integration failed, resolve conflicts carefully and verify the resulting history.

---

## 7. Remotes and GitHub

### Beginner
Can follow a push demonstration.

### Developing
Can push and clone with guidance.

### Capable
Can independently work with local and remote repositories.

### Independent
Can diagnose common remote problems and understand what local and remote state means.

---

## 8. Recovery

### Beginner
Needs direct help after mistakes.

### Developing
Can recover simple mistakes with guidance.

### Capable
Can choose an appropriate everyday undo operation.

### Independent
Can investigate complex mistakes using history and reflog without making the situation worse.

---

## 9. Advanced Operations

### Beginner
Recognises the terms.

### Developing
Can follow guided exercises.

### Capable
Can use stash, rebase and cherry-pick in controlled situations.

### Independent
Understands when these operations are appropriate, predicts their effects and verifies the resulting history.

---

## 10. Professional Behaviour

### Beginner
Runs instructions.

### Developing
Begins asking why.

### Capable
Inspects and verifies.

### Independent
Consistently follows:

```text
Observe
→ Understand
→ Predict
→ Act
→ Verify
→ Recover if necessary
```

---

# Final Practical Assessment

The learner should receive an unfamiliar repository and a written task.

The assessment should deliberately avoid giving exact commands.

The learner should have to:

1. inspect the repository;
2. read its README;
3. determine the current state;
4. inspect history;
5. create appropriate work;
6. make a meaningful change;
7. commit it;
8. integrate another line of work;
9. resolve at least one conflict;
10. recover from one intentional mistake;
11. use documentation where necessary;
12. verify the final state;
13. explain the decisions made.

---

# Assessment Questions

Ask the learner:

### Before changing anything

> What is the current state?

### Before running an important command

> What do you expect this to do?

### After running it

> What evidence shows that it worked?

### When something fails

> What does the error actually say?

### Before recovering

> What information do you need before changing anything else?

### At the end

> Explain the repository history you created.

---

# Completion Standard

The course is complete when the learner can demonstrate **Independent** behaviour across the major skills.

The goal is not:

> “The learner knows every Git command.”

The goal is:

> **“The learner can solve Git problems.”**
