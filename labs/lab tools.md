# Git Essentials — Lab Tools

## Purpose

This directory is reserved for reproducible practical lab environments.

The course currently keeps the main lesson content simple:

```text
lesson/
├── README.md
└── practice-drills.md
```

The lab-tools area exists so practical environments can be added without making every lesson directory complicated.

---

# What a Lab Tool Should Do

A lab should make it easy for a learner to practise a specific Git skill in a controlled repository.

Good labs should:

- start from a known state;
- be reproducible;
- explain the objective;
- avoid hiding the Git state;
- allow mistakes;
- make recovery possible;
- provide a way to reset the lab;
- clearly state the expected final state.

---

# Recommended Lab Structure

A future lab may look like:

```text
lab-tools/
└── merge-conflict-lab/
    ├── README.md
    ├── setup.sh
    ├── reset.sh
    └── expected-state.md
```

On Windows, a corresponding PowerShell setup may be added where appropriate.

Do not add scripts merely for the sake of having scripts.

A lab is useful only when it makes the exercise easier to reproduce.

---

# Lab Safety

Labs should use disposable repositories.

Avoid scripts that:

- modify the user's normal projects;
- delete arbitrary directories;
- require administrator privileges unnecessarily;
- overwrite unrelated files;
- download unexplained scripts and execute them;
- hide what they are doing.

A learner should be able to inspect the setup script before running it.

---

# Reproducibility

A lab should state:

```text
Starting directory
Starting branch
Starting commits
Expected files
Expected problem
Expected final state
Reset procedure
```

If a lab depends on external software, its README should identify the requirement.

---

# Suggested Future Labs

## 01 — Terminal Navigation

A disposable filesystem structure for:

- `pwd`
- `ls`
- `cd`
- paths
- files and folders

## 02 — Documentation Mission

A small project requiring the learner to read a README and install or verify a dependency.

## 05 — Git State

A repository containing:

- untracked files;
- modified files;
- staged files.

## 11 — Merge

Two branches containing compatible changes.

## 17 — Merge Conflict

Two branches deliberately editing the same area differently.

## 18 — Everyday Recovery

A repository prepared with several safe mistakes.

## 19 — Reflog Rescue

A repository where a branch has moved and a commit must be located.

## 20 — Stash

A task requiring temporary work to be set aside.

## 21 — Rebase

A small branch history designed to make commit replay visible.

## 22 — Cherry-pick

Several independent commits where only one is needed.

## 23 — Mastery

A realistic unfamiliar repository with multiple tasks.

---

# Design Principle

The lab should never replace understanding.

The learner should still have to answer:

```text
What is happening?
Why?
What do I expect?
What will I do?
How will I verify it?
```

---

# Current Status

The course can be completed without additional lab scripts.

This directory is intentionally a foundation for future reproducible environments rather than a collection of unnecessary automation.
