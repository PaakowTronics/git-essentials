# 04 — Your First Git Repository

## Welcome

You have spent the first three lessons preparing for this moment.

In Lesson 01, you learned how to work with folders and files from the terminal.

In Lesson 02, you learned how to find reliable documentation, follow instructions, install software, and verify that it works.

In Lesson 03, you learned **why Git exists**.

Now you are going to use Git for the first time.

But we are going to do something important:

> **We will not start by memorizing Git commands.**

You are going to create an ordinary project folder, turn it into a Git repository, investigate what changed, and prove that Git is actually managing the project.

The central question for this lesson is:

> **What changes when an ordinary folder becomes a Git repository?**

---

# Mission

By the end of this lesson, you should be able to:

- explain the difference between an ordinary folder and a Git repository;
- initialize a Git repository;
- recognize the `.git` directory;
- understand that `.git` is Git's internal repository information;
- use `git status` to inspect repository state;
- identify untracked files;
- understand that `git init` does not create a commit;
- identify the repository root;
- avoid accidentally initializing the wrong folder;
- use `pwd`, `ls`, and `git status` together;
- predict what Git will report before checking;
- verify the result instead of assuming it worked;
- explain what you did in your own words.

---

# Part 1 — Start With an Ordinary Folder

Before Git gets involved, a project is simply a collection of files and folders.

For this lesson, imagine:

```text
mountain-cafe/
├── README.md
├── menu.txt
└── hours.txt
```

There is nothing special about this folder yet.

Your operating system knows that these files exist.

You can open them.

You can edit them.

You can rename them.

You can delete them.

But Git is not yet managing their history.

---

# Part 2 — What Does "Initialize" Mean?

You will hear the word:

> **initialize**

In everyday language, initialize means to prepare something so it can begin being used.

When we initialize a Git repository, we are telling Git:

> **"Start managing this project as a Git repository."**

The command that does this is:

```bash
git init
```

You do not need to run it yet.

First, predict what should happen.

---

# Part 3 — Before You Touch Anything: Know Where You Are

Lesson 01 taught you an important habit:

> **Know where you are before changing things.**

Use:

```bash
pwd
```

Then inspect the folder:

```bash
ls
```

Ask yourself:

- Am I in the folder I intended to use?
- Is this the project I want Git to manage?
- Are there files here?
- Is this the project root?

Do not rush.

A surprising number of Git problems begin because someone initialized the wrong folder.

---

# Part 4 — The Repository Boundary

Imagine this structure:

```text
projects/
└── mountain-cafe/
    ├── README.md
    ├── menu.txt
    └── hours.txt
```

If you initialize Git inside:

```text
mountain-cafe/
```

then that project becomes a Git repository.

But if you accidentally initialize Git inside:

```text
projects/
```

you may have created a repository around more than you intended.

That is why we care about your current location.

The terminal skill from Lesson 01 is now directly supporting your Git skill.

---

# Part 5 — Your First `git init`

Once you are certain you are inside the correct project folder, run:

```bash
git init
```

You may see a message explaining that an empty Git repository has been initialized.

The exact wording may vary depending on your Git version.

Do not just accept the message.

Investigate.

---

# Part 6 — What Changed?

Immediately after running `git init`, ask:

> **What changed?**

Run:

```bash
ls -la
```

You should now be able to see a hidden directory named:

```text
.git
```

This is the first major piece of evidence that Git has been initialized.

Before initialization, the project did not have this Git repository information.

After initialization, it does.

---

# Part 7 — What Is `.git`?

Remember Lesson 03.

We said that a Git repository contains Git's internal information.

The `.git` directory is where Git stores the information it needs to manage the repository.

Think of it like:

```text
mountain-cafe/
│
├── README.md
├── menu.txt
├── hours.txt
│
└── .git/
      ↑
      Git's internal repository information
```

Your project files remain your project files.

The `.git` directory belongs to Git.

---

# Part 8 — Do Not Work Inside `.git`

You should normally **not** manually create, delete, rename, or edit things inside `.git`.

Git manages that directory.

A good beginner rule is:

> **Work on your project files. Let Git manage `.git`.**

Deleting or damaging `.git` can destroy the repository's local history and configuration.

For now, simply inspect it.

Do not modify it.

---

# Part 9 — Your First `git status`

Now run:

```bash
git status
```

This is one of the most important Git commands you will learn.

It asks Git:

> **"What is the current state of this repository?"**

Git should report that the files are not yet being tracked.

You may see something similar to:

```text
Untracked files:
  README.md
  menu.txt
  hours.txt
```

The exact formatting may differ.

---

# Part 10 — What Does "Untracked" Mean?

This is our first important Git status word.

**Untracked** means Git sees a file in the repository, but that file has not yet been added to Git's tracked set.

Think:

```text
Your project
     │
     ├── README.md   ← Git sees it
     ├── menu.txt    ← Git sees it
     └── hours.txt   ← Git sees it
```

But Git is effectively saying:

> "I know these files exist, but you have not told me to start tracking them."

Do not confuse this with:

> "The files don't exist."

They do exist.

Git simply isn't tracking them yet.

---

# Part 11 — Why Didn't `git init` Track Everything?

This is a very important question.

You ran:

```bash
git init
```

Why didn't Git automatically create a commit containing all the files?

Because initializing a repository and recording a version are two different actions.

Think of it this way:

```text
git init
    ↓
Prepare the project for Git
```

Later:

```text
staging + commit
    ↓
Record a meaningful point in history
```

We are not learning staging and committing yet.

That comes in a later lesson.

For now, the important idea is:

> **`git init` creates the repository. It does not create your first project history entry.**

---

# Part 12 — Repository vs Commit

These two ideas are easy to confuse.

### Repository

The project is now being managed by Git.

### Commit

A particular state of the project has been recorded in Git history.

So after:

```bash
git init
```

you can have:

```text
Repository: YES
Commit:     NO
```

That is completely normal.

---

# Part 13 — Inspecting Without Changing

Notice something about the commands we have used:

```bash
pwd
ls
ls -la
git status
```

These commands mainly help us **inspect**.

They help answer:

> Where am I?

> What is here?

> What hidden things are here?

> What does Git think?

This is an important professional habit:

> **Inspect before you change.**

When something goes wrong later, you will repeatedly use inspection commands to understand the current state.

---

# Part 14 — The Git State Conversation

You can now imagine yourself having a conversation with Git.

You:

> "Where am I?"

Terminal:

```bash
pwd
```

You:

> "What is in this folder?"

Terminal:

```bash
ls
```

You:

> "Is this a Git repository?"

Git:

```bash
git status
```

You:

> "What does Git currently know about my files?"

Git:

```bash
git status
```

This is why `git status` will become one of your most frequently used Git commands.

---

# Part 15 — What Happens to Your Existing Files?

A common beginner fear is:

> "If I run `git init`, will Git move my files?"

No.

Your files remain where they were.

For example:

Before:

```text
mountain-cafe/
├── README.md
├── menu.txt
└── hours.txt
```

After:

```text
mountain-cafe/
├── README.md
├── menu.txt
├── hours.txt
└── .git/
```

Your project files are still there.

Git has added its own repository information.

---

# Part 16 — What Happens If You Run `git init` Again?

This is a useful investigation.

Suppose you already initialized:

```text
mountain-cafe/
```

and run:

```bash
git init
```

again from the same repository.

Git will generally tell you that the repository was reinitialized.

You have not created a second history inside the same folder.

This does **not** mean:

> "Run `git init` repeatedly."

It means Git recognizes that the directory is already a repository.

---

# Part 17 — How Do You Know Where the Repository Starts?

At this stage, you should be able to reason about the repository root.

Suppose:

```text
mountain-cafe/
├── README.md
└── src/
    └── menu.txt
```

If you initialize Git in:

```text
mountain-cafe/
```

and then move into:

```text
mountain-cafe/src/
```

Git can still understand that you are working inside the repository.

Your current directory and the repository root are not always the same thing.

This distinction will become important later.

---

# Part 18 — The Most Important Habit in This Lesson

When using Git, don't ask only:

> "What command do I type?"

Ask:

> **"What state am I in?"**

Then:

> **"What state do I want?"**

Then:

> **"What operation gets me there?"**

Then:

> **"How will I verify it?"**

For this lesson:

```text
Current state:
ordinary project folder

Desired state:
Git repository

Operation:
initialize Git

Verification:
.git + git status
```

This way of thinking will carry through the entire course.

---

# Part 19 — A Complete First Repository Workflow

Your first repository workflow is:

```text
1. Create or find the project
          ↓
2. Enter the correct project folder
          ↓
3. Confirm your location
          ↓
4. Inspect the project
          ↓
5. Initialize Git
          ↓
6. Inspect hidden files
          ↓
7. Check Git status
          ↓
8. Explain what Git reports
```

Notice that we have not committed anything.

That is intentional.

We are learning one layer at a time.

---

# Part 20 — Common Beginner Mistakes

## Mistake 1 — Initializing the wrong folder

You think you're in:

```text
mountain-cafe/
```

but you're actually in:

```text
projects/
```

### Prevention

Use:

```bash
pwd
ls
```

before:

```bash
git init
```

---

## Mistake 2 — Thinking `.git` is a normal project folder

It isn't.

Let Git manage it.

---

## Mistake 3 — Thinking `git init` creates a commit

It doesn't.

It initializes the repository.

---

## Mistake 4 — Thinking "untracked" means "missing"

It doesn't.

The file exists.

Git simply isn't tracking it yet.

---

## Mistake 5 — Assuming success without checking

Seeing:

```text
Initialized empty Git repository
```

is useful.

But verification is better.

Check:

```bash
ls -la
git status
```

---

# Part 21 — Your First Git Prediction

Before running:

```bash
git init
```

predict:

### What will happen to the existing files?

```text
________________________________________________
```

### What new thing do you expect to appear?

```text
________________________________________________
```

### Will Git create a commit?

```text
Yes / No
```

### What will `git status` probably tell you about the existing files?

```text
________________________________________________
```

Now perform the operation and compare reality with your prediction.

---

# Part 22 — What You Should Know Now

You should now understand:

- an ordinary project folder is not automatically a Git repository;
- `git init` initializes a repository;
- `.git` is Git's internal repository information;
- your project files remain where they were;
- `git status` reports repository state;
- newly visible project files may be untracked;
- untracked does not mean missing;
- initialization does not create a commit;
- repository root and current directory can be different;
- inspection and verification are essential.

---

# Final Challenge

You are given an ordinary folder:

```text
mountain-cafe/
├── README.md
├── menu.txt
└── hours.txt
```

Your task is:

> **Turn this folder into a Git repository without creating a commit.**

You must:

1. Find the folder.
2. Enter it.
3. Confirm where you are.
4. Inspect its contents.
5. Initialize Git.
6. Confirm that `.git` exists.
7. Check Git status.
8. Explain why the files are untracked.
9. Explain why there is no commit.
10. Verify that the original files are still present.

Do not treat this as a command-copying exercise.

The goal is to demonstrate that you understand what happened.

---

# Mastery Check

Before moving to Lesson 05, you should be able to answer:

### 1. What is the difference between an ordinary folder and a Git repository?

### 2. What does `git init` do?

### 3. What is `.git`?

### 4. Why should you normally leave `.git` alone?

### 5. What does `git status` tell you?

### 6. What does "untracked" mean?

### 7. Does `git init` create a commit?

### 8. How can you verify that a repository was initialized?

### 9. Why should you use `pwd` before initializing a repository?

### 10. What is the difference between "repository initialized" and "project committed"?

If you can explain all ten in your own words, you are ready for the next stage.

---

# The Big Idea

You have now crossed an important line.

Before this lesson:

> **Git was software installed on your computer.**

After this lesson:

> **Git is now managing one of your projects.**

In the next lesson, we will start changing that project and asking the question:

> **"What does Git see?"**
