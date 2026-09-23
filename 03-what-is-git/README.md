# 03 — What Is Git?

## Welcome

You have now done something important.

You learned how to use the terminal.

Then you learned how to find instructions and use official documentation.

You also installed Git.

But we deliberately did **not** start using Git immediately.

Why?

Because typing commands without understanding what Git is would turn Git into a collection of mysterious instructions.

This lesson is different.

Today, you are going to understand:

> **What Git is, why it exists, what problem it solves, and how it thinks about your work.**

You will not need to memorize a long list of Git commands.

In fact, most of this lesson happens **before** we start seriously using Git.

---

# Mission

By the end of this lesson, you should be able to:

- explain Git in your own words
- explain the problem Git was created to solve
- understand what "version control" means
- understand what a repository is
- distinguish Git from GitHub
- understand the idea of a commit
- understand why Git records changes rather than simply making copies of a folder
- understand the basic idea of branches
- understand the difference between your files and Git's records about those files
- recognize why Git is useful when something goes wrong
- describe a simple Git workflow before learning the commands
- predict what Git might care about when a project changes

The goal is not:

> "I can repeat the definition of Git."

The goal is:

> **"I understand what Git is doing and why I would want it."**

---

# Part 1 — Imagine You Have No Git

Before learning Git, let's create a problem.

Imagine you are working on a project.

You create a folder:

```text
my-project/
```

Inside it:

```text
my-project/
├── index.html
├── style.css
└── app.js
```

You work on it for several days.

On Monday, everything works.

On Tuesday, you make some improvements.

On Wednesday, you add a new feature.

On Thursday, you change the design.

On Friday...

Something breaks.

You don't know exactly what you changed.

You think:

> "It worked on Wednesday."

But which Wednesday?

And what exactly did the project look like then?

---

# Part 2 — The Beginner's Version Control System

Without Git, someone might try this:

```text
my-project/
my-project-final/
my-project-final2/
my-project-final-new/
my-project-final-new2/
my-project-final-use-this/
my-project-final-use-this-real/
```

You may have seen something similar.

People create copies because they are trying to protect their work.

That instinct is understandable.

But it quickly becomes difficult to manage.

Imagine having 50 copies.

Which one is correct?

What changed between them?

Who changed it?

When?

Why?

Can you safely return to an earlier version?

---

# Part 3 — Another Problem: Multiple People

Now imagine you are not working alone.

You and another person are working on the same project.

You change:

```text
app.js
```

They also change:

```text
app.js
```

You both finish your work.

Now you need to combine the changes.

What happens if you both changed the same part of the file?

You need a system that can help you understand:

- what changed
- who changed it
- when it changed
- which version came before it
- how different changes relate to each other
- how to combine work

This is where version control becomes useful.

---

# Part 4 — What Is Version Control?

**Version control** is a way of keeping track of changes to files over time.

Think about the word:

> **version**

A version is a particular state of something at a particular point in time.

For example:

```text
Version 1
Version 2
Version 3
Version 4
```

A version control system helps you keep track of those changes in an organized way.

It can help answer questions such as:

> What changed?

> When did it change?

> Who changed it?

> What did the project look like before?

> Can I go back?

> Can I work on something separately?

> Can two people's work be combined?

Git is a version control system.

---

# Part 5 — So What Exactly Is Git?

A simple definition is:

> **Git is a version control system that records changes to files so you can understand, manage, compare, and recover different versions of a project.**

That sounds simple.

But there is an important detail.

Git does not simply make a new complete copy of your project every time you save something.

Instead, Git maintains information that allows it to understand the history of your project.

That history becomes extremely useful.

---

# Part 6 — Git Is Not a Backup Folder

This is an important distinction.

You might think:

> "Git is just a place where old copies of my files are stored."

Not quite.

Git tracks the history of a project.

It records snapshots of the project's state through **commits**.

It also records information about how those snapshots relate to one another.

That allows you to investigate your project's history.

For example:

```text
Project
  │
  ├── Version A
  │
  ├── Version B
  │
  ├── Version C
  │
  └── Version D
```

You can investigate how you moved from one state to another.

---

# Part 7 — Meet the Commit

One of the most important words in Git is:

> **commit**

A commit is a recorded point in the history of your project.

You can think of it as saying:

> "Record this state of my project as an important point in its history."

For example:

```text
Commit 1
"Created the project"
```

Then:

```text
Commit 2
"Added login page"
```

Then:

```text
Commit 3
"Fixed login validation"
```

Then:

```text
Commit 4
"Added password reset"
```

These aren't just random saves.

They are meaningful points in the project's history.

---

# Part 8 — A Commit Is More Than a Button

A beginner might think:

> "Commit means save."

That's close enough for a first mental model, but it is not quite accurate.

Your normal file-saving action and a Git commit are different things.

When you press Save in a text editor, you are saving changes to the file.

When you make a Git commit, you are telling Git:

> **"Record this selected state of my project in the project's history."**

That distinction becomes very important later.

---

# Part 9 — Think of a Project as a Timeline

Imagine the project as a timeline:

```text
START
  │
  ▼
Commit A
  │
  ▼
Commit B
  │
  ▼
Commit C
  │
  ▼
Commit D
```

Each commit is connected to the history before it.

This gives Git something extremely useful:

> **A record of how the project developed.**

You can investigate that history later.

---

# Part 10 — Why Would You Want History?

Imagine you discover this today:

> "The login stopped working."

Without useful history, you may have to search through everything manually.

With Git history, you can investigate:

> What changed recently?

> Which files changed?

> Which commit introduced the change?

> What did the project look like before that?

This turns debugging from:

> "What on earth happened?"

into:

> "Let's investigate what changed."

Git does not automatically solve every bug.

But it gives you information that makes investigation much more manageable.

---

# Part 11 — Git Gives You a Time Machine

This is a useful mental model.

Git is **not literally a time machine**.

But for learning purposes, imagine that your project's history is a timeline:

```text
                    NOW
                     │
                     ▼
Monday ── Tuesday ── Wednesday ── Thursday
  │          │            │            │
  ▼          ▼            ▼            ▼
  A          B            C            D
```

If something broke on Thursday, you can investigate what changed between Wednesday and Thursday.

You can also inspect earlier states.

That is one of Git's most powerful ideas.

---

# Part 12 — What Is a Repository?

You will hear this word constantly:

> **repository**

Often shortened to:

> **repo**

A Git repository is a project that Git is tracking, together with the Git information needed to manage its history.

A simple way to think about it:

> **A repository is a project under Git's version-control management.**

It contains your project files and Git's internal information about the project's history and state.

Later, when you run:

```bash
git init
```

you will turn an ordinary folder into a Git repository.

We are **not doing that yet**.

First understand what it means.

---

# Part 13 — An Ordinary Folder vs a Git Repository

Imagine this folder:

```text
my-project/
├── index.html
├── style.css
└── app.js
```

It is just a normal folder.

Your computer knows that the files exist.

But Git is not yet managing the project.

After Git initializes the folder, Git creates its own internal repository information.

Conceptually:

```text
my-project/
├── project files
│   ├── index.html
│   ├── style.css
│   └── app.js
│
└── Git information
```

The Git information is stored in a special hidden directory called:

```text
.git
```

You don't normally edit that directory manually.

Git manages it.

---

# Part 14 — The `.git` Folder

When a folder becomes a Git repository, Git creates a hidden directory named:

```text
.git
```

This is extremely important.

The `.git` directory contains information Git needs to manage the repository.

Do not treat it like an ordinary project folder.

Do not casually delete files from it.

Do not start changing things inside it manually.

A good beginner rule is:

> **Let Git manage `.git`.**

Your project files are yours to work on.

The `.git` directory is Git's internal machinery.

---

# Part 15 — Git Is Not GitHub

This causes confusion for almost every beginner.

**Git** and **GitHub** are not the same thing.

### Git

Git is the version control software.

It runs on your computer.

It can manage the history of a project locally.

### GitHub

GitHub is an online service that hosts Git repositories and provides collaboration features.

Think:

```text
Git
↓
The tool managing your project history

GitHub
↓
An online service where Git repositories can be hosted and shared
```

You can use Git without GitHub.

You can create a Git repository on your computer and never put it online.

Later, you can connect that repository to GitHub.

---

# Part 16 — A Simple Analogy

Imagine you are writing a book.

### Git is like your detailed version-history system.

It helps you keep track of:

```text
Draft 1
Draft 2
Draft 3
Draft 4
```

and understand what changed.

### GitHub is like an online place where the project can be stored and shared.

You could keep your manuscript's history on your own computer without using an online service.

Likewise, Git does not require GitHub.

---

# Part 17 — What Git Actually Watches

Git works with files inside a repository.

Imagine:

```text
website/
├── index.html
├── styles.css
└── script.js
```

You edit:

```text
styles.css
```

Git can detect that the project has changed.

You edit:

```text
script.js
```

Git can detect that too.

You create:

```text
login.html
```

Git can detect that a new file exists.

You delete:

```text
old.css
```

Git can detect that the file was deleted.

This is why the terminal work from Lesson 01 matters.

You are already comfortable creating, changing, moving and deleting files.

Now Git gives you a way to track those changes.

---

# Part 18 — Git Does Not Read Your Mind

Git knows that files changed.

It does not automatically know:

> "The developer changed this because the login button was broken."

It can record information about changes and commits.

But **you** provide the meaning.

That is why good commit messages matter.

For example:

Bad:

```text
changes
```

Better:

```text
Fix login button validation
```

Even better:

```text
Prevent login submission with empty password
```

A useful commit message helps the future you understand what happened.

---

# Part 19 — Git History Is a Story

Imagine these commits:

```text
1. Create project structure
2. Add login page
3. Add password validation
4. Fix login error
5. Add password reset
6. Improve password reset email
```

Someone looking at the history can understand how the project developed.

Compare that with:

```text
1. update
2. stuff
3. changes
4. fix
5. final
6. final2
```

The second history tells you almost nothing.

Git gives you the ability to create a useful project story.

---

# Part 20 — What Is a Branch?

Another important Git idea is:

> **branch**

Don't worry about the command yet.

First understand the problem.

Suppose your main project is working:

```text
main
  │
  A
  │
  B
  │
  C
```

Now you want to experiment with a completely new feature.

You don't necessarily want to make your main line messy while experimenting.

Git allows you to create another line of work:

```text
             D
            /
A ── B ── C
            \
             E ── F
```

These different lines are called branches.

A branch lets you work on something separately while keeping another line of development intact.

We will spend much more time on branches later.

For now, remember:

> **A branch is a separate line of development within a Git repository.**

---

# Part 21 — Why Branches Matter

Imagine a working project:

```text
MAIN PROJECT
```

Someone asks:

> "Can you experiment with a new design?"

You don't necessarily want your experiment to become the main project immediately.

You can work on a separate branch.

Later you can decide whether and how to bring the work back into the main line.

This becomes extremely useful when teams work together.

---

# Part 22 — Git's Big Picture

You can now think of Git like this:

```text
                    YOUR PROJECT
                         │
                         ▼
                    Git watches
                         │
                         ▼
                    You make changes
                         │
                         ▼
                  You choose what
                    to record
                         │
                         ▼
                     COMMIT
                         │
                         ▼
                  Project history
                         │
            ┌────────────┴────────────┐
            ▼                         ▼
       Investigate                 Develop
        history                  separate work
                                      │
                                   BRANCHES
```

This is the basic idea behind the entire course.

---

# Part 23 — Git's Core Vocabulary

You are going to hear these words repeatedly.

Don't try to memorize a dictionary.

Understand the basic idea.

| Word | Beginner-friendly meaning |
|---|---|
| Git | A version control system |
| Repository / repo | A project being managed by Git |
| Commit | A recorded point in the project's history |
| History | The recorded sequence of commits |
| Branch | A separate line of development |
| Working tree / working directory | The project files you are currently working with |
| `.git` | Git's internal repository information |
| GitHub | An online service for hosting and collaborating around Git repositories |
| Remote | Another copy/location of a repository, often online |
| Clone | Create a local copy of a repository |
| Merge | Combine work from different lines of development |

Some of these terms will become much clearer when you actually use them.

That is intentional.

---

# Part 24 — What Git Does NOT Do

Understanding what Git does **not** do is just as important.

Git does not automatically:

- write your code
- fix every bug
- understand your business logic
- decide whether your change is good
- replace backups for every situation
- automatically upload everything to GitHub
- prevent every mistake

Git is a tool.

You still make decisions.

---

# Part 25 — Git Is Powerful Because You Can Investigate

One of the most important ideas in this course is:

> **Git gives you evidence about what happened.**

Suppose someone says:

> "The project was working yesterday."

Instead of guessing, you can eventually investigate:

- What commits happened?
- What files changed?
- Which branch contains the work?
- What changed between two points?
- When was a particular change introduced?

Git turns project history into something you can inspect.

That is why Git is not merely a "save button."

---

# Part 26 — A Realistic Story

Imagine you are working on a staff management application.

On Monday:

```text
Login works.
```

Tuesday:

```text
Password reset added.
```

Wednesday:

```text
Email verification added.
```

Thursday:

```text
Something is wrong with login.
```

Without Git, you might start searching through every file.

With Git, you can eventually ask:

> What changed between Wednesday and Thursday?

You may discover that a particular commit changed the login process.

Then you can investigate that change.

Git does not tell you:

> "This developer is wrong."

It gives you a record you can inspect.

---

# Part 27 — Git and Teamwork

Now imagine five people work on the same project.

Without a version-control system, coordinating changes can become difficult.

Git provides mechanisms for:

- separate lines of development
- recording changes
- comparing work
- combining changes
- reviewing history
- recovering from mistakes

Later, GitHub adds online collaboration tools such as pull requests and code review.

But Git itself is already useful even when you are working alone.

---

# Part 28 — Git Can Be Useful Even If You Are the Only Developer

You might think:

> "I'm working alone. Why do I need Git?"

Because future you is another developer.

You might make a change today and forget why.

You might break something tomorrow.

You might want to compare the current project with an earlier version.

You might want to experiment without disturbing stable work.

You might want a record of how the project evolved.

Git helps with all of those situations.

---

# Part 29 — The Git Workflow You Will Learn

You don't need to memorize commands yet.

Just understand the journey:

```text
1. Have a project
       ↓
2. Put the project under Git
       ↓
3. Make changes
       ↓
4. Inspect what changed
       ↓
5. Choose what should be recorded
       ↓
6. Create a commit
       ↓
7. Continue working
       ↓
8. Inspect history when needed
```

Later:

```text
Branches
   ↓
Separate work
   ↓
Merge
   ↓
Collaboration
   ↓
GitHub
   ↓
Remote repositories
```

And eventually:

```text
Mistake
   ↓
Investigate
   ↓
Recover
```

---

# Part 30 — Your First Important Git Question

Before moving on, think about this:

> If Git records project history, **when** should you create a commit?

Not every five seconds.

Not after every character.

A commit should represent a meaningful point in the development of the project.

For example:

```text
Add login page
```

is meaningful.

```text
Changed one letter
```

usually isn't.

Later, you will learn how to decide what belongs in a commit.

---

# Part 31 — The Three Questions

Whenever you start using Git, develop these three questions:

### 1. What is the state of my project?

What files changed?

### 2. What does Git know about those changes?

What does Git currently see?

### 3. What do I want to record?

Which changes belong in the next meaningful point in history?

These questions will become more important than memorizing commands.

---

# Part 32 — Prediction Before Commands

You are now ready to start experimenting.

But before Lesson 04, there is one more important habit.

When you encounter a Git command, don't immediately type it.

First ask:

> **What do I expect this command to do?**

Then:

> **What evidence would prove that it worked?**

Then run it.

Then:

> **Did reality match my prediction?**

This is the same habit you learned in Lesson 01:

```text
Predict
   ↓
Run
   ↓
Verify
```

Now we are applying it to Git.

---

# Part 33 — Your Mental Model

At this point, imagine Git as a historian standing beside your project.

Your project:

```text
┌──────────────────────────────┐
│        YOUR PROJECT          │
│                              │
│  index.html                  │
│  styles.css                  │
│  app.js                      │
│                              │
└──────────────┬───────────────┘
               │
               │ changes
               ▼
        ┌───────────────┐
        │      GIT      │
        │               │
        │ records       │
        │ project       │
        │ history       │
        └───────┬───────┘
                │
                ▼
             HISTORY
```

You make the changes.

You decide what is meaningful.

Git records the history.

You can later investigate it.

---

# Part 34 — What You Should Know Before Lesson 04

You should now understand:

- Git is version-control software.
- Version control means tracking changes over time.
- A Git repository is a project managed by Git.
- A commit is a recorded point in project history.
- Git history helps you investigate what happened.
- A branch is a separate line of development.
- `.git` contains Git's internal repository information.
- Git and GitHub are different.
- Git can be used without GitHub.
- Git does not replace your judgment.
- Git does not automatically fix your problems.
- Good Git use involves inspecting and verifying state.

You don't need to know all the commands yet.

That comes next.

---

# Final Thought

Think back to Lesson 02.

You installed Git because you needed a tool.

Now you know why the tool exists.

The next lesson is where things become practical.

You will take an ordinary folder and say, in effect:

> **"Git, start keeping track of this project."**

That is when you create your first Git repository.

