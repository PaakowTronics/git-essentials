# 02 — Documentation Practice Drills

# Mission: Install Git Using Official Documentation

## The Rule

This drill is different from the exercises in Lesson 01.

You have already learned how to use the terminal.

Now you must learn how to **find instructions yourself**.

You will install an important developer tool:

> **Git**

There is one important rule:

# You are NOT being given the installation command.

You must find the correct command by following the official documentation.

That is the point of the exercise.

If you finish this drill knowing the command but not knowing how you found it, you have missed the main lesson.

The skill is:

> **Find → Read → Understand → Run → Verify**

---

# Before You Begin

You will need:

- a computer
- a terminal
- an internet connection
- access to a web browser
- enough permission to install software on your computer

You should already know from Lesson 01 how to:

```text
open the terminal
check where you are
read what the terminal displays
run a command
recognize when something has gone wrong
```

You do **not** need to know Git yet.

In fact, that is intentional.

Lesson 03 will explain Git.

---

# Part 1 — The First Investigation

## Mission 1: Is Git Already Installed?

Open your terminal.

Before searching the internet, check whether Git is already available.

### Your task

Find a way to ask Git for its version.

You learned in Lesson 02 that programs often provide a `--version` option.

Try:

```bash
git --version
```

### Stop and observe.

You should get one of two broad outcomes.

### Outcome A — Git is installed

You may see something similar to:

```text
git version 2.55.0
```

The exact version may be different.

### Outcome B — Git is not available

Your terminal may tell you that the command cannot be found, or your system may suggest installing Git.

That is useful information.

It does not mean you did something wrong.

---

# Mission 2 — Do Not Install Yet

Even if Git is not installed, **do not immediately run an installation command**.

Open your web browser.

Search for:

```text
Git official installation
```

Your job is to find the official Git website.

The official Git website is:

```text
https://git-scm.com/
```

The official installation page is:

```text
https://git-scm.com/install/
```

Open it.

---

# Mission 3 — Explore the Documentation

Before doing anything, look at the installation page.

Answer these questions.

### Question 1

What operating systems are listed?

Write them down.

```text
1. __________________
2. __________________
3. __________________
```

### Question 2

Which operating system are you using?

```text
My operating system: __________________
```

### Question 3

Does Git use exactly the same installation method on every operating system?

```text
Yes / No
```

Explain:

```text
________________________________________________
________________________________________________
```

### Question 4

If you are using Linux, what Linux distribution are you using?

Examples include:

```text
Debian
Ubuntu
Fedora
Arch
openSUSE
```

Write yours:

```text
My Linux distribution: __________________
```

If you are not using Linux, write:

```text
Not using Linux
```

---

# Mission 4 — Find Your Instructions

Now find the section of the official documentation that applies to your computer.

Do not copy a command yet.

First identify:

```text
Operating system:
____________________

Installation method:
____________________

Command or installer described by the documentation:
____________________
```

If the documentation gives more than one method, read the descriptions and decide which one is appropriate for your environment.

---

# Mission 5 — Understand Before Running

You have now found an installation instruction.

Before running it, answer:

### What software are you installing?

```text
____________________
```

### Why are you installing it?

```text
________________________________________________
```

### Where did you get the instruction?

```text
________________________________________________
```

### Is the source official?

```text
Yes / No
```

### Does the instruction apply to your operating system?

```text
Yes / No
```

### Does the command require administrator privileges?

```text
Yes / No / Not applicable
```

If you see something like:

```bash
sudo ...
```

you should recognize that the command is asking for elevated privileges.

If you are unsure what a command does, **stop and investigate before running it.**

---

# Mission 6 — Run the Installation

Now follow the official Git documentation.

Run the appropriate installation command for your operating system.

### Important

Do not use a command from:

- a random blog
- a random YouTube description
- an unrelated forum post
- an old tutorial

Use the official Git documentation first.

The official Git installation page is:

**https://git-scm.com/install/**

---

# Mission 7 — Watch the Terminal

While the installation is running, don't just stare at the screen.

Pay attention.

You may see messages telling you:

- what is being downloaded
- what is being installed
- what is being changed
- whether dependencies are required
- whether the installation succeeded
- whether something failed

You don't need to understand every line.

But don't automatically assume that a screen full of text means something went wrong.

Wait for the process to finish.

---

# Mission 8 — Verify the Installation

When the installation is complete, do not simply assume Git works.

Check.

Run:

```bash
git --version
```

### Record the result

```text
Git version reported by my computer:

____________________________________
```

### Did it work?

```text
Yes / No
```

If yes, you have completed the installation.

But you're not finished with the exercise.

We are testing whether you can explain what you did.

---

# Mission 9 — Explain Your Installation

Without looking back at the documentation, try to explain:

### 1. How did you find the official Git documentation?

```text
________________________________________________
________________________________________________
```

### 2. How did you determine which instructions applied to your computer?

```text
________________________________________________
________________________________________________
```

### 3. What installation method did you use?

```text
________________________________________________
```

### 4. What command did you use?

```text
________________________________________________
```

### 5. How did you verify the installation?

```text
________________________________________________
```

### 6. What version of Git is installed?

```text
________________________________________________
```

---

# Mission 10 — Documentation Detective

Now go back to the official Git installation page.

Find the installation instructions for a **different operating system** from yours.

You do not need to install it.

For example:

- Linux learner → inspect Windows or macOS instructions.
- Windows learner → inspect Linux or macOS instructions.
- macOS learner → inspect Linux or Windows instructions.

Answer:

### Is the installation method identical?

```text
Yes / No
```

### What is one difference you noticed?

```text
________________________________________________
________________________________________________
```

### Why do you think the instructions are different?

```text
________________________________________________
________________________________________________
```

This is teaching you an important idea:

> **Software instructions depend on the environment.**

---

# Mission 11 — The Fake Shortcut

Imagine you search:

```text
how to install git
```

You find this page:

> "Install Git in 10 seconds! Just copy this command."

The page does not identify who maintains it.

The command is:

```bash
curl https://example.com/install.sh | sh
```

You have never heard of the website.

### Would you run it immediately?

```text
Yes / No
```

### Why?

Write at least two reasons.

```text
1. _____________________________________________

2. _____________________________________________
```

### What would you do instead?

```text
________________________________________________
________________________________________________
```

You are not being asked to decide whether every such command is malicious.

The lesson is simpler:

> **Don't blindly execute commands from sources you have not evaluated.**

---

# Mission 12 — The Documentation Translation Exercise

Documentation often uses technical language.

Suppose you see:

```text
Install Git using your distribution's package manager.
```

You may not understand that sentence yet.

Break it down.

### What is "distribution"?

```text
________________________________________________
```

### What is a "package manager"?

```text
________________________________________________
```

### What does "install Git" mean?

```text
________________________________________________
```

Now rewrite the original sentence in your own beginner-friendly words:

```text
________________________________________________
________________________________________________
```

This exercise matters.

If you can translate technical instructions into ordinary language, you are beginning to understand rather than merely copy.

---

# Mission 13 — The Error Investigation Drill

This is a **thinking exercise**.

Imagine you are using Linux and the documentation tells you to install Git.

You run the command.

Instead, the terminal says:

```text
E: Unable to locate package git
```

Do not immediately invent a solution.

Answer:

### What were you trying to do?

```text
________________________________________________
```

### What does the error appear to be saying?

```text
________________________________________________
```

### What would you investigate first?

Choose one:

```text
A. Delete the computer's operating system.

B. Run random commands until something works.

C. Read the documentation and investigate the package manager/repository situation.

D. Assume the computer is permanently broken.
```

Correct approach:

```text
C
```

Now explain why:

```text
________________________________________________
________________________________________________
```

---

# Mission 14 — The "Check Before Change" Drill

You are helping someone install Git.

They tell you:

> "I think Git might already be installed."

What should you do first?

```text
A. Install Git anyway.

B. Delete their old software.

C. Check whether Git is already available.

D. Restart the computer.
```

Correct approach:

```text
C
```

What command can check the Git version?

```bash
________________________
```

---

# Mission 15 — Predict Before You Run

This course uses an important habit:

> **Predict → Run → Verify**

Before running:

```bash
git --version
```

predict what will happen.

### If Git is installed:

```text
I expect:
________________________________________________
```

### If Git is not installed:

```text
I expect:
________________________________________________
```

Now run it.

### Was your prediction correct?

```text
Yes / No
```

### What actually happened?

```text
________________________________________________
________________________________________________
```

---

# Mission 16 — Documentation Scavenger Hunt

Return to the official Git installation page.

Find these pieces of information.

| Item | Your answer |
|---|---|
| Official Git website | |
| Installation page | |
| Windows installation method | |
| macOS installation methods | |
| Linux installation method | |
| Git version currently shown by the documentation | |
| Method used on your computer | |

Do not guess.

Find each answer from the documentation.

---

# Mission 17 — Teach Someone Else

Pretend someone who has never installed software asks you:

> "How did you install Git?"

Do **not** answer:

> "I ran a command."

Give them the process.

Your explanation should contain these ideas:

```text
1. Check whether Git is already installed.
2. Find the official Git documentation.
3. Identify your operating system.
4. Find the instructions for that system.
5. Read and understand the instruction.
6. Run the appropriate installation method.
7. Verify Git.
```

Write your explanation here:

```text
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
```

---

# Part 18 — Break-It Challenge

This challenge is about what happens when you cannot follow the instructions exactly.

Imagine the documentation says:

```bash
sudo apt install git
```

but your computer responds:

```text
sudo: command not found
```

### Question 1

Should you keep typing different versions of `sudo` until one works?

```text
Yes / No
```

### Question 2

What should you investigate?

Possible areas:

- What operating system am I using?
- Is this actually a Debian/Ubuntu system?
- Does the documentation apply to my system?
- Does my environment provide `sudo`?
- Is there another official installation method?

Write your investigation plan:

```text
1. _____________________________________________
2. _____________________________________________
3. _____________________________________________
```

The purpose is not to solve this particular error.

The purpose is to learn:

> **An error is a clue. Investigate it.**

---

# Part 19 — Real-World Documentation Mission

Now pretend nobody is teaching you Git.

Your only instruction is:

> **"Get Git installed on your computer."**

You are not allowed to ask:

> "What command should I run?"

Instead, you must solve the problem yourself.

### Rules

You may:

- use a web browser
- read official documentation
- search for definitions of unfamiliar words
- use your terminal
- read terminal error messages
- return to the documentation
- search an exact error message if necessary

You may not:

- blindly copy commands from random websites
- ask someone to give you the installation command
- skip verification
- claim success without checking

### Your mission

Get from:

```text
"I need Git."
```

to:

```text
"Git is installed and I verified the version."
```

Record your journey.

---

# Mission 20 — Your Installation Report

Complete this after finishing the installation.

## Environment

Operating system:

```text
____________________________
```

Linux distribution, if applicable:

```text
____________________________
```

## Investigation

How did you find the official Git documentation?

```text
________________________________________________
```

## Installation

Installation method:

```text
________________________________________________
```

Command used, if applicable:

```text
________________________________________________
```

## Verification

Verification command:

```text
________________________________________________
```

Installed Git version:

```text
________________________________________________
```

## Problem solving

Did anything go wrong?

```text
Yes / No
```

If yes, what did you do?

```text
________________________________________________
________________________________________________
```

## Reflection

What was the hardest part?

```text
________________________________________________
```

What new word did you learn?

```text
________________________________________________
```

What would you do differently next time?

```text
________________________________________________
```

---

# Boss Challenge — Install Git Without Being Told How

This is the final test.

Imagine the instructor says:

> **"You need Git. Get it working."**

That's all.

No command.

No operating-system-specific instructions.

No tutorial.

No step-by-step walkthrough.

You must:

1. Open the terminal.
2. Check whether Git is already installed.
3. Find the official Git documentation.
4. Identify your operating system.
5. Find the correct installation instructions.
6. Read the instructions.
7. Understand the installation method.
8. Install Git if necessary.
9. Verify Git.
10. Record the installed version.
11. Explain how you solved the task.

### Success condition

You are successful if you can explain:

> **Where you found the instructions, why you trusted them, why they applied to your computer, what you did, and how you verified the result.**

The exact command you typed is **not** the main measure of success.

---

# Final Knowledge Check

Answer without looking back.

### 1. What is documentation?

________________________________________________

### 2. Why should you prefer official documentation for installation instructions?

________________________________________________

### 3. Why should you identify your operating system before following installation instructions?

________________________________________________

### 4. What does this do?

```bash
git --version
```

________________________________________________

### 5. What is a package manager?

________________________________________________

### 6. Why can two Linux distributions have different installation commands?

________________________________________________

### 7. What should you do if an installation command fails?

________________________________________________

### 8. Complete the process:

```text
__________
↓
__________
↓
__________
↓
__________
↓
__________
```

The intended process is:

> **Find → Read → Understand → Run → Verify**

---

# Mastery Check

Before moving to Lesson 03, you should be able to do all of these without being given a command:

- [ ] Check whether Git is installed.
- [ ] Find the official Git website.
- [ ] Find the official installation instructions.
- [ ] Identify your operating system.
- [ ] Find the instructions appropriate for your system.
- [ ] Explain what the installation command is doing at a basic level.
- [ ] Install Git using the appropriate official method.
- [ ] Verify that Git works.
- [ ] Find the installed Git version.
- [ ] Read an installation error and begin investigating it.
- [ ] Explain where you found your instructions.
- [ ] Explain why you trusted the source.
- [ ] Explain how you verified success.

## The real mastery question

Ask yourself:

> **"If I needed to install a different piece of software tomorrow, and nobody gave me the command, would I know what to do?"**

If your answer is **yes**, then you are learning the right skill.

---

# What Comes Next?

You now have Git available.

But there is an obvious question:

> **What exactly is Git?**

You installed it before fully learning it.

That was intentional.

Lesson 03 will answer that question.

We will stop thinking of Git as something we merely installed and begin understanding **the problem Git was created to solve**.
