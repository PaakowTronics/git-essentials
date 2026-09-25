# 04 — Your First Git Repository: Practice Drills

## The Rule

You already know the course routine:

> **Predict → Run → Verify**

For this lesson, add one more question:

> **What state am I in?**

Do not rush to commands.

First understand the situation.

---

# Mission 1 — Repository or Just a Folder?

You see:

```text
mountain-cafe/
├── README.md
├── menu.txt
└── hours.txt
```

Can you conclude that this is a Git repository?

```text
Yes / No
```

Why?

```text
________________________________________________
________________________________________________
```

What evidence would you look for?

```text
________________________________________________
```

---

# Mission 2 — Predict `git init`

You are inside the correct project folder.

You run:

```bash
git init
```

Before running it, predict:

### 1. Will the existing files disappear?

```text
Yes / No
```

### 2. Will the files move somewhere else?

```text
Yes / No
```

### 3. Will Git create repository information?

```text
Yes / No
```

### 4. Will a commit automatically be created?

```text
Yes / No
```

### 5. What evidence could you inspect afterward?

```text
________________________________________________
```

Now run it and compare your prediction.

---

# Mission 3 — The `.git` Discovery

After initializing the repository, run:

```bash
ls -la
```

Find:

```text
.git
```

Answer:

### What is `.git`?

```text
________________________________________________
________________________________________________
```

### Why is it hidden from a normal `ls` listing?

```text
________________________________________________
```

### Should you manually edit files inside it?

```text
Yes / No
```

Why?

```text
________________________________________________
```

---

# Mission 4 — What Does Git See?

Run:

```bash
git status
```

Read the output carefully.

Do not just look for the word "untracked."

Answer:

### What branch does Git report?

```text
________________________________________________
```

### Does Git report that there are commits yet?

```text
________________________________________________
```

### Which files are untracked?

```text
________________________________________________
________________________________________________
```

### What does "untracked" mean in your own words?

```text
________________________________________________
```

---

# Mission 5 — The Status Detective

Imagine Git says:

```text
Untracked files:
  README.md
  menu.txt
  hours.txt
```

A beginner says:

> "Git can't find those files."

Is that correct?

```text
Yes / No
```

Explain:

```text
________________________________________________
________________________________________________
```

---

# Mission 6 — Repository State Report

Complete this table after initializing your repository.

| Question | Your answer |
|---|---|
| Where am I? | |
| What project am I in? | |
| Is this a Git repository? | |
| Where is Git's internal directory? | |
| Have I made a commit? | |
| Which files are untracked? | |

The purpose is to make you describe the state instead of simply saying:

> "It worked."

---

# Mission 7 — The Wrong Folder

You have:

```text
projects/
├── mountain-cafe/
└── travel-blog/
```

You intend to make `mountain-cafe` a Git repository.

But your terminal is currently in:

```text
projects/
```

You accidentally run:

```bash
git init
```

### What problem have you created?

```text
________________________________________________
________________________________________________
```

### What should you have checked first?

```text
________________________________________________
```

### Which Lesson 01 command helps you confirm your location?

```bash
________________
```

---

# Mission 8 — Fix the Thinking

A learner says:

> "Git is confusing. I ran `git init`, but nothing happened."

What would you ask them to check?

Write a sensible investigation sequence.

```text
1. _____________________________________________

2. _____________________________________________

3. _____________________________________________
```

Think about:

- location
- hidden files
- repository status

---

# Mission 9 — Does `git init` Save Your Work?

You have:

```text
notes.txt
```

You run:

```bash
git init
```

Then you close the terminal.

### Has Git created a history entry containing `notes.txt`?

```text
Yes / No
```

### Why?

```text
________________________________________________
```

### What still needs to happen before a meaningful history entry exists?

```text
________________________________________________
```

Do not solve that process yet. Just explain the idea.

---

# Mission 10 — Repository vs Commit

Fill in the blanks.

```text
git init
   ↓
Git repository: __________
Commit history: __________
```

Now explain why:

```text
________________________________________________
________________________________________________
```

---

# Mission 11 — The `.git` Trap

Someone tells you:

> "I don't need this `.git` folder. My project files are all here."

Should they delete it?

```text
Yes / No
```

Why?

```text
________________________________________________
________________________________________________
```

What would deleting it potentially remove?

```text
________________________________________________
```

---

# Mission 12 — Move Into a Subfolder

Your repository is:

```text
mountain-cafe/
├── README.md
└── src/
    └── menu.txt
```

You move into:

```text
src/
```

### Are you still inside the Git repository?

```text
Yes / No
```

### What would you expect `git status` to do?

```text
________________________________________________
```

### Why?

```text
________________________________________________
```

Now test your prediction.

---

# Mission 13 — Find the Repository Root

You are somewhere deep inside:

```text
mountain-cafe/src/components/menu/
```

You know the repository root is higher up.

Without using a graphical file manager:

### What Lesson 01 skills could help you investigate where you are?

```text
________________________________________________
________________________________________________
```

### What Git command can help you inspect repository state?

```text
________________________________________________
```

The important thing is not the fastest route.

The important thing is being able to **find your way and prove where you are**.

---

# Mission 14 — Predict the Status

You initialize a repository containing:

```text
README.md
menu.txt
hours.txt
```

You have not staged or committed anything.

What do you expect `git status` to report?

```text
________________________________________________
________________________________________________
```

Now run it.

### Was your prediction correct?

```text
Yes / No
```

### What surprised you?

```text
________________________________________________
```

---

# Mission 15 — Create Another File

Inside the repository, create:

```text
prices.txt
```

Use what you learned in Lesson 01.

Then run:

```bash
git status
```

### What changed in Git's report?

```text
________________________________________________
```

### Why?

```text
________________________________________________
```

---

# Mission 16 — Rename a File

Rename:

```text
hours.txt
```

to:

```text
opening-hours.txt
```

Use the terminal skill from Lesson 01.

Then run:

```bash
git status
```

### What does Git report?

```text
________________________________________________
________________________________________________
```

Don't worry if the exact wording looks more complicated than expected.

Your task is to investigate what Git is telling you.

---

# Mission 17 — The Investigation Challenge

You open a project and see:

```text
.git
README.md
src/
tests/
```

Someone asks:

> "Is this a Git repository?"

What evidence do you have?

```text
________________________________________________
________________________________________________
```

What command would you use to ask Git directly?

```bash
________________
```

Why is using both evidence sources useful?

```text
________________________________________________
```

---

# Mission 18 — Break-It: Initialize the Wrong Place

Create:

```text
practice/
├── project-a/
└── project-b/
```

Now deliberately initialize Git in:

```text
practice/
```

instead of `project-a/`.

### Stop.

Do not immediately delete anything.

Investigate:

```bash
pwd
ls -la
git status
```

Answer:

### Where is the repository?

```text
________________________________________________
```

### Is that where you intended it to be?

```text
Yes / No
```

### What did this exercise teach you?

```text
________________________________________________
________________________________________________
```

This is a **break-it exercise**.

The point is to experience why location matters.

---

# Mission 19 — Recovery Thinking

You initialized Git in the wrong directory.

Before changing anything, write an investigation plan.

```text
1. _____________________________________________

2. _____________________________________________

3. _____________________________________________

4. _____________________________________________
```

Do not blindly delete `.git`.

Think first.

The course is training you to investigate before making destructive changes.

---

# Mission 20 — Command Detective

Match each question with the most appropriate tool.

| Question | Tool |
|---|---|
| Where am I? | |
| What files are here? | |
| Show hidden entries too. | |
| What does Git think about this repository? | |
| Start Git management in this folder. | |

Possible tools:

```text
pwd
ls
ls -la
git status
git init
```

---

# Mission 21 — Build It Yourself

Starting from an empty location, create:

```text
mountain-cafe/
├── README.md
├── menu.txt
├── hours.txt
└── notes/
```

Then:

1. Enter the project.
2. Confirm your location.
3. Inspect it.
4. Initialize Git.
5. Confirm `.git`.
6. Check Git status.
7. Leave all project files untracked.
8. Verify the final state.

### Important

Do not look at a command recipe.

Use what you learned in Lessons 01 and 04.

---

# Mission 22 — The Three-Question Test

For your `mountain-cafe` repository, answer:

### Where am I?

```text
________________________________________________
```

### What state is the project in?

```text
________________________________________________
```

### What evidence proves that?

```text
________________________________________________
```

This is the beginning of thinking like a Git user.

---

# Mission 23 — Teach Back

Explain to a beginner:

> "How do I turn an ordinary folder into a Git repository?"

You may mention commands, but explain **why** each step exists.

```text
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
```

---

# Boss Challenge — Your First Repository Rescue

You are given this folder:

```text
company-menu/
├── README.md
├── menu.txt
├── prices.txt
└── images/
```

You are told:

> "Start tracking this project with Git."

But you are given no command list.

You must:

### Stage 1 — Identify

Find the project.

### Stage 2 — Verify

Confirm you are in the correct folder.

### Stage 3 — Initialize

Turn it into a Git repository.

### Stage 4 — Inspect

Find the Git repository information.

### Stage 5 — Investigate

Use Git status.

### Stage 6 — Explain

Tell the instructor:

- what changed;
- what `.git` is;
- what files Git sees;
- what "untracked" means;
- whether a commit exists;
- how you verified everything.

### Success condition

You are not successful merely because:

```bash
git init
```

ran without an error.

You are successful when you can **prove and explain the resulting state**.

---

# Reflection

### What was easiest?

```text
________________________________________________
```

### What was confusing?

```text
________________________________________________
```

### What did `git status` teach you?

```text
________________________________________________
```

### Why does `pwd` still matter now that you are learning Git?

```text
________________________________________________
```

### What is one mistake you are now less likely to make?

```text
________________________________________________
```

---

# Mastery Check

- [ ] I can explain what a Git repository is.
- [ ] I can initialize a repository.
- [ ] I know what `.git` represents.
- [ ] I know not to casually modify `.git`.
- [ ] I can use `git status`.
- [ ] I understand "untracked."
- [ ] I know `git init` does not create a commit.
- [ ] I can identify the correct repository directory.
- [ ] I use `pwd` and `ls` before important operations.
- [ ] I predict Git's state before checking.
- [ ] I verify the result after an operation.
- [ ] I can explain what happened without relying on a command recipe.

## The Real Mastery Question

Ask yourself:

> **"If someone gave me an ordinary project folder and said 'put this under Git', could I do it safely and explain what happened?"**

If yes, you are ready for Lesson 05.

