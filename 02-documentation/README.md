# 02 — Documentation: Learning How to Figure Things Out

## Welcome

In Lesson 01, you learned how to use the terminal.

You learned how to:

- find out where you are
- look at what is around you
- move between folders
- create folders
- create files
- rename things
- move things
- copy things
- remove things
- check your work
- recover when you become confused

That gave you a foundation.

But there is a problem.

You will eventually encounter something you have **never done before**.

You might need to:

- install a program
- configure a tool
- connect two programs
- change a setting
- fix an error
- use a command you have never seen
- set up a project you have never used before

Nobody can memorize instructions for every possible situation.

So the next skill is not another list of commands.

The next skill is:

> **Learning how to find and follow reliable instructions.**

That is what documentation is about.

---

# Mission

By the end of this lesson, you should be able to:

1. Explain what documentation is.
2. Understand why official documentation matters.
3. Find documentation for a piece of software.
4. Tell the difference between official documentation and a random tutorial.
5. Read an instruction before running it.
6. Identify what operating system an instruction applies to.
7. Recognize that different computers may require different installation methods.
8. Understand, at a basic level, what an installation command is asking the computer to do.
9. Use the terminal to check whether software is already installed.
10. Follow official documentation to install Git.
11. Verify that Git was installed successfully.
12. Investigate an error instead of immediately asking someone else to fix it.

You are **not** expected to memorize the installation commands.

The important skill is knowing how to find the correct instructions and use them safely.

---

# Part 1 — What Is Documentation?

You have probably seen instructions before.

For example:

> To assemble a chair:
>
> 1. Attach the legs.
> 2. Attach the seat.
> 3. Tighten the screws.

Software documentation is the same basic idea.

It is information written to explain how to use, install, configure, or troubleshoot software.

Documentation can tell you:

- what a program does
- how to install it
- how to start it
- how to configure it
- what commands are available
- what a particular option means
- what requirements you need
- how to fix common problems

Think of documentation as the **instruction manual for software**.

---

# Part 2 — Why You Need This Skill

Imagine that tomorrow you need to install a program you have never heard of.

You search the internet.

You find this:

> "Run this command. Trust me, it works."

You find another page:

> "Use this command instead."

Then another:

> "Download this script and run it."

Which one should you trust?

A beginner might simply copy the first command.

That is exactly the habit we do **not** want.

Instead, we want you to think:

> Who published this instruction?
>
> Is it for my operating system?
>
> Is it current?
>
> What is this command doing?
>
> Can I verify the result?

That is the beginning of independent technical problem solving.

---

# Part 3 — Official Documentation vs Random Instructions

There are many useful websites on the internet.

There are also many outdated, incomplete, or unsafe instructions.

For software installation, your first choice should normally be the **official source**.

For Git, the official website is:

**https://git-scm.com/**

The official Git installation page is:

**https://git-scm.com/install/**

The official Git documentation provides installation instructions for Windows, macOS, Linux, and other systems.

### A useful rule

When you need to install software:

> **Start with the software's official website.**

Do not start with a random command copied from a search result.

That does not mean every community tutorial is bad.

It means you should first establish the official instructions and then use other sources when appropriate.

---

# Part 4 — What Does "Official" Mean?

Suppose you want to install Git.

You search:

```text
install git
```

You may see many results.

Your first job is not to copy a command.

Your first job is to identify the official source.

For Git, the official site is:

```text
git-scm.com
```

You should become comfortable checking the website address.

### Why?

Because someone could create a page that says:

> "Official Git installation"

while actually giving you instructions for something completely different.

This is one reason we do not teach:

> "Google the command and copy the first result."

We teach:

> **Find the software's official documentation.**

---

# Part 5 — Documentation Contains New Words

You will notice something when you begin reading documentation:

It may contain words you have never seen before.

That is normal.

For example, documentation may mention:

- operating system
- package
- package manager
- installer
- repository
- dependency
- version
- architecture
- command
- option
- configuration

Do **not** panic when you see a new word.

You do not need to understand an entire page before continuing.

Instead:

1. Stop at the unfamiliar word.
2. Find out what it means.
3. Continue reading.
4. Return to the instruction.

This is an important learning habit.

> **Unfamiliar does not mean impossible.**

---

# Part 6 — Your Operating System Matters

Instructions are not always the same for every computer.

For example:

- Windows has its own software installation methods.
- macOS has its own methods.
- Linux distributions often use package managers.

So before following installation instructions, you need to know:

> **Which operating system am I using?**

You may already know this.

If you are using Linux, you should also learn which Linux distribution you are using.

For example:

- Debian
- Ubuntu
- Fedora
- Arch
- openSUSE

You do not need to memorize the differences yet.

The important idea is:

> **Do not use instructions meant for a different system.**

---

# Part 7 — Checking Before Installing

Before installing software, check whether it is already installed.

This is an important habit:

> **Check first. Change second.**

For Git, the check is:

```bash
git --version
```

You may see something similar to:

```text
git version 2.55.0
```

The exact version may be different.

If Git is installed, you already have it.

If your terminal tells you that `git` cannot be found, Git may not be installed or may not be available in your terminal's command path.

Do not immediately panic.

That message is information.

It tells you what to investigate next.

---

# Part 8 — What Does `--version` Mean?

You have already used commands such as:

```bash
pwd
ls
cd
mkdir
```

Now you are seeing:

```bash
git --version
```

The first part:

```text
git
```

is the program you are asking the terminal to run.

The second part:

```text
--version
```

is an instruction asking Git to tell you its version.

You do not need to learn every possible option now.

Just understand the pattern:

```text
program + instruction
```

Many command-line programs provide options that let you ask questions or change how they behave.

---

# Part 9 — What Is a Package?

When you install software, you may hear the word **package**.

A package is a prepared collection of software files that can be installed by a package-management system.

You can think of it like this:

> Instead of manually collecting every file a program needs, a package gives the operating system an organized way to install the software.

You don't need to understand the technical internals yet.

Just remember:

> **A package is a prepared unit of software that can be installed.**

---

# Part 10 — What Is a Package Manager?

On many Linux systems, software can be installed using a **package manager**.

A package manager helps your operating system:

- find software
- install software
- update software
- remove software
- manage software dependencies

Different Linux distributions can use different package managers.

For example:

| Linux family | Common package manager |
|---|---|
| Debian / Ubuntu | `apt` |
| Fedora | `dnf` |
| Arch Linux | `pacman` |
| openSUSE | `zypper` |

You do **not** need to memorize this table.

The important lesson is:

> **Your operating system's documentation tells you which method to use.**

---

# Part 11 — Understanding an Installation Command

Suppose official documentation tells a Debian/Ubuntu user to run:

```bash
sudo apt install git
```

Do not just copy it.

Read it.

### `sudo`

This asks the system to run the following command with administrator privileges.

You may be asked for your password.

### `apt`

This is the package-management tool commonly used on Debian-based systems.

### `install`

This tells the package manager that you want to install something.

### `git`

This is the software package you want to install.

So, in plain English:

> "Use the system's package manager with administrator permission to install Git."

That is much better than memorizing:

```bash
sudo apt install git
```

as a magical spell.

### Important

Your computer may not use `apt`.

If you are using Fedora, Arch, openSUSE, or another system, the official instructions may give you a different command.

**Follow the instructions for your system.**

---

# Part 12 — Why `sudo` Matters

You may encounter commands beginning with:

```bash
sudo
```

Do not think:

> "sudo is something I put before every command."

It is not.

`sudo` is used when an operation requires elevated privileges.

Installing software for the whole system is one common example.

Because a command using `sudo` can make important changes to your computer, you should understand what follows it before pressing Enter.

This gives us another course rule:

> **Never give administrator privileges to a command you do not understand.**

You don't need to understand every technical detail.

You should at least know:

- what program you are running
- what it is supposed to do
- why administrator permission is required

---

# Part 13 — Windows, macOS and Linux

The official Git installation instructions are different depending on the operating system.

### Windows

Git is distributed through **Git for Windows**.

The official Git installation page provides the current Windows download and also documents an installation option using `winget`.

### macOS

Git can be installed in several ways, including Apple's Xcode Command Line Tools and package managers such as Homebrew.

### Linux

Git is generally installed using the package manager provided by the Linux distribution.

For example, Debian/Ubuntu use `apt`, while Fedora uses `dnf`.

### The lesson

Do not memorize all of those commands.

Instead remember:

> **Identify your system → read the instructions for that system → follow them → verify.**

---

# Part 14 — Installation Is Not Finished Until You Verify It

Suppose you run an installation command.

The terminal prints many lines.

It eventually returns to the prompt.

Is the software installed?

Maybe.

Don't guess.

Check.

For Git:

```bash
git --version
```

If you receive a Git version, you have evidence that Git is available.

This is a pattern you will use throughout your technical life:

```text
Do something
    ↓
Check the result
    ↓
Verify
```

---

# Part 15 — What If Something Goes Wrong?

Suppose you run an installation command and see an error.

Do not immediately:

- delete things
- reinstall your operating system
- run random commands
- copy a mysterious command from a forum

First, read the error.

Ask:

### 1. What was I trying to do?

Example:

> Install Git.

### 2. What command did I run?

Write it down.

### 3. What did the terminal say?

Read the actual message.

### 4. Does the documentation mention this problem?

Search the official documentation first.

### 5. If necessary, search the exact error message

When searching, include useful context.

Instead of:

```text
git broken
```

use something closer to:

```text
"exact error message" Git install Ubuntu
```

The exact wording can help you find the relevant explanation.

---

# Part 16 — Documentation Is Not Something You Read Once

Documentation is not a textbook you must memorize.

It is a resource you return to.

Even experienced developers constantly read documentation.

Why?

Because software changes.

Commands have options.

Tools have different versions.

Operating systems differ.

New problems appear.

The professional skill is not:

> "I remember every command."

It is:

> **"I know how to find the correct information."**

---

# Part 17 — Your First Documentation Reading Exercise

Before installing anything, open the official Git installation page:

**https://git-scm.com/install/**

Do not run any commands yet.

Read the page.

Answer:

1. What operating systems are listed?
2. Which one applies to you?
3. Does the page provide a different installation method for different systems?
4. Does it mention a package manager for Linux?
5. Where would you go if you needed Windows instructions?
6. Where would you go if you needed macOS instructions?
7. What would you do before installing Git?

Do not worry if some words are unfamiliar.

Look them up.

That is part of the exercise.

---

# Part 18 — A Documentation Reading Method

When you open documentation, use this five-step method.

## Step 1 — Identify

What software or task is this documentation about?

## Step 2 — Find the relevant section

Don't read the entire website.

Find the section related to your task.

## Step 3 — Check the environment

Does the instruction apply to:

- Windows?
- macOS?
- Linux?
- your particular Linux distribution?

## Step 4 — Read before running

Understand what the command is intended to do.

## Step 5 — Verify

After completing the instruction, find out how to confirm that it worked.

Remember:

> **Find → Read → Understand → Run → Verify**

---

# Part 19 — What You Should NOT Do

### Don't do this

> "Someone online said to run this command, so I'll run it."

### Do this

> "Where did this instruction come from?"

---

### Don't do this

> "The command failed, so I'll try five other commands."

### Do this

> "What does the error say?"

---

### Don't do this

> "The tutorial is three years old, but it worked for someone."

### Do this

> "What does the current official documentation say?"

---

### Don't do this

> "I don't know what this word means, so I can't continue."

### Do this

> "I'll find out what this word means."

---

# Part 20 — Your First Professional Habit

From now on, whenever you need to learn something new, use this sequence:

```text
I don't know.
     ↓
Find the official source.
     ↓
Read the relevant instructions.
     ↓
Identify what applies to my computer.
     ↓
Understand what I am about to do.
     ↓
Do it.
     ↓
Verify the result.
     ↓
Investigate if something went wrong.
```

This habit is more valuable than memorizing dozens of commands.

---

# Part 21 — Preparation for the Drill

The next file contains your practical drill.

You will be asked to install Git.

But there is a rule:

> **You are not allowed to receive the installation command from the instructor.**

You must find it yourself.

This is intentional.

The goal is not to see whether you can type:

```bash
some-command
```

The goal is to see whether you can go from:

> "Git isn't installed."

to:

> "I found the official instructions, followed the correct instructions for my computer, and verified that Git works."

That is the real skill.

---

# Lesson Summary

You now know:

- what documentation is
- why documentation matters
- why official sources are important
- why operating system differences matter
- what a package is
- what a package manager does
- what `git --version` does
- what `sudo` means at a basic level
- why you should check before installing
- why you should understand commands before running them
- how to verify an installation
- how to investigate errors
- how to approach unfamiliar software

Most importantly:

> **You do not need to know everything before you begin. You need to know how to find out.**

---

# Mastery Check

Before moving to Lesson 03, you should be able to answer these questions in your own words.

### 1. What is documentation?

### 2. Why should you look for official documentation when installing software?

### 3. Why can't you always use the same installation command on every computer?

### 4. What does this command ask Git to do?

```bash
git --version
```

### 5. What is a package manager?

### 6. Why might a Linux computer use `apt` while another Linux computer uses `dnf`?

### 7. Why should you check whether Git is already installed before installing it?

### 8. What should you do if an installation command produces an error?

### 9. What are the five steps for reading documentation?

```text
________________
________________
________________
________________
________________
```

### 10. Complete this sentence:

> When I don't know how to do something, I should not immediately ______________________.

---

# Before Lesson 03

You should have Git installed and verified.

You should also understand **how you found the installation instructions**.

You are not expected to memorize the installation command.

In Lesson 03, we will finally answer:

> **What exactly is Git, and why did we just install it?**
