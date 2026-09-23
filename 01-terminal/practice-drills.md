# Practice Drills — Your Terminal

Welcome to the practice area.

This is where you stop simply **following instructions** and start learning to **think with the terminal**. try not to refer to the notes to instill learning.

You will make predictions, test them, investigate mistakes, and prove that your work is correct.

> **Rule for this practice:** Predict first. Run second. Verify third.

If your prediction is wrong, that is not failure. It is useful information.

---

# How to Use This Practice

For every drill:

1. **Read the situation.**
2. **Predict what will happen.**
3. **Write down your prediction.**
4. **Run the command.**
5. **Compare the result with your prediction.**
6. **Explain why the result happened.**

Do not rush to the terminal.

The goal is not to see how quickly you can type commands.

The goal is to develop the habit of understanding what a command will do **before** you run it.

---

# Mission 1 — Where Am I?

Imagine you are standing inside this folder:

```text
terminal-project/
└── src/
    └── app/
```

Your current location is:

```text
terminal-project/src/app
```

## Your prediction

What will this command tell you?

```bash
pwd
```

Write your answer on in your lessons book before running anything.

### Check yourself

The result should identify the **complete location of the directory you are currently inside**.

The exact path on your computer will be different from another learner's path.

### Think about it

Why doesn't `pwd` tell you what files are inside the folder?

Because `pwd` answers:

> **Where am I?**

It does not answer:

> **What's here?**

For that, we use `ls`.

---

# Mission 2 — What's Around Me?

You are still here:

```text
terminal-project/src/app
```

Predict what this command does:

```bash
ls
```

Does it:

A. Move you into another folder?

B. Delete the current folder?

C. Show the contents of the current folder?

D. Tell you the complete path to the current folder?

Write your answer before running it.

### The idea

`ls` means:

> **Show me what is here.**

It does not move you.

---

# Mission 3 — Go Up One Level

You are here:

```text
terminal-project/src/app
```

Predict what happens when you run:

```bash
cd ..
```

Before running it, complete this sentence:

> After this command, I will be inside __________________.

### Draw it

```text
terminal-project/
└── src/
    └── app/   ← I am here
```

After `cd ..`, where will you be?

```text
terminal-project/
└── src/       ← I will be here
    └── app/
```

### Verify

Run:

```bash
pwd
```

Did the result match your prediction?

---

# Mission 4 — Two Steps Up

Now imagine you are here:

```text
terminal-project/src/app
```

You run:

```bash
cd ..
```

and then:

```bash
cd ..
```

Where are you now?

Don't run it yet.

Predict first.

### Draw the journey

```text
terminal-project/
└── src/
    └── app/
```

Start:

```text
app
```

First `cd ..`:

```text
src
```

Second `cd ..`:

```text
terminal-project
```

### Your turn

Explain in your own words:

> `cd ..` means ______________________________.

---

# Mission 5 — Create Something

You are inside:

```text
terminal-project
```

Predict what this does:

```bash
mkdir backup
```

Choose the correct answer:

A. Creates a file called `backup`.

B. Creates a folder called `backup`.

C. Moves you into a folder called `backup`.

D. Deletes a folder called `backup`.

### Now verify

Run:

```bash
ls
```

Can you see `backup`?

Then enter it:

```bash
cd backup
```

and verify:

```bash
pwd
```

You have just combined three skills:

```text
create → inspect → enter
```

---

# Mission 6 — Create a File

You are inside:

```text
terminal-project/backup
```

Predict what this does:

```bash
touch notes.txt
```

Will it:

- create a folder?
- create a file?
- move a file?
- display the contents of a file?

Now run:

```bash
ls
```

You should find:

```text
notes.txt
```

### Important observation

The command may produce **no message**.

That does not automatically mean it failed.

You verified the result with:

```bash
ls
```

This is a professional habit:

> **An operation can succeed without printing a success message. Verify the state instead of guessing.**

---

# Mission 7 — Rename or Move?

This command can be confusing at first:

```bash
mv notes.txt important-notes.txt
```

What do you predict?

A. The file is copied, leaving two files.

B. The file is renamed.

C. The file is deleted.

D. A folder is created.

Write your prediction.

Then run:

```bash
ls
```

You should see:

```text
important-notes.txt
```

and no longer see:

```text
notes.txt
```

### What did `mv` do?

In this situation, it **renamed** the file.

But `mv` can also move a file from one folder to another.

That is why its name means:

> **move**

---

# Mission 8 — Move a File to Another Folder

Imagine this structure:

```text
terminal-project/
├── docs/
│   └── setup.txt
└── src/
```

You are inside `docs`.

You want to move `setup.txt` into `src`.

Predict what this command does:

```bash
mv setup.txt ../src/
```

### Break it apart

`setup.txt`

means:

> the file I want to move.

`../`

means:

> go up one folder.

`src/`

means:

> then enter the `src` folder.

So the path:

```text
../src/
```

means:

> From where I am now, go up one level and then into `src`.

### Challenge

Before running the command, draw the file's journey:

```text
docs/setup.txt
       ↓
      ?
       ↓
src/setup.txt
```

Then run it and verify both locations.

---

# Mission 9 — Copy Instead of Move

You have:

```text
src/app/main.txt
```

You want another copy called:

```text
main-backup.txt
```

Predict what this does:

```bash
cp main.txt main-backup.txt
```

After running:

```bash
ls
```

you should see **both** files.

```text
main.txt
main-backup.txt
```

### Important difference

With `mv`:

```text
old → new
```

the original location/name is no longer there.

With `cp`:

```text
original → copy
```

the original remains.

---

# Mission 10 — Safe Deletion

You have:

```text
main.txt
main-backup.txt
```

You only want to remove the backup.

Before running anything, answer:

> Which exact file will this command remove?

```bash
rm main-backup.txt
```

Now verify:

```bash
ls
```

You should still have:

```text
main.txt
```

### Safety habit

Before using `rm`, ask yourself:

1. Where am I?
2. What exactly am I removing?
3. Do I really want it gone?

If you are unsure, stop and investigate with:

```bash
pwd
ls
```

---

# Mission 11 — The Lost Developer

This one is intentionally different.

You are working on a project and suddenly realize:

> “I don't remember where I am.”

Don't panic.

You have two clues available:

```bash
pwd
```

and:

```bash
ls
```

Use them to investigate.

## Your objective

Find out:

1. Where am I?
2. What is around me?
3. Which directory should I enter next?
4. How do I return to the project root?

### Rule

Do **not** use the graphical file manager.

The terminal is your investigation tool.

---

# Mission 12 — The Wrong Turn

Start from:

```text
terminal-project
```

Navigate into:

```text
src/app
```

Now pretend you accidentally went too far.

Your goal is to return to:

```text
terminal-project
```

without using an absolute path.

### Challenge

How many times do you need:

```bash
cd ..
```

?

Predict first.

Then test your prediction.

Finally run:

```bash
pwd
```

to prove where you ended up.

---

# Mission 13 — The Mystery Command

Your colleague gives you this command:

```bash
mkdir archive
```

They ask:

> “What do you think this will do?”

Don't run it immediately.

Investigate the command's meaning.

You already know enough to make a prediction, but the important habit is this:

> **When you encounter a command you do not understand, don't blindly copy it. Find out what it does first.**

If you are unsure, use the command's manual/documentation.

For example:

```bash
man mkdir
```

On systems where `man` is available, read the relevant information.

You do not need to understand every line.

Find the part that tells you what `mkdir` does.

Then make your prediction.

---

# Mission 14 — Break the Navigation

This is your first deliberate **break-and-fix** exercise.

Create this structure:

```text
navigation-lab/
├── project/
│   ├── src/
│   │   └── app/
│   └── docs/
└── notes/
```

Now intentionally enter the wrong directory.

For example:

```text
navigation-lab/project/src/app
```

Pretend you forgot where you are.

### Your job

Without using a graphical file manager:

1. Discover your current location.
2. Look at what is around you.
3. Work out how many levels you need to go up.
4. Return to `navigation-lab`.
5. Prove that you are there.

### Evidence

Finish with:

```bash
pwd
```

and:

```bash
ls
```

The final output should prove that you are back at the lab root.

---

# Mission 15 — The Command Sequence Detective

Consider this sequence:

```bash
mkdir demo
cd demo
touch first.txt
mkdir backup
mv first.txt backup/
```

Do not run it yet.

Predict the final structure.

Draw it:

```text
demo/
├── ?
└── ?
```

Where is `first.txt`?

### Then test yourself

Run the commands one at a time.

After each command, ask:

> What changed?

Use:

```bash
pwd
ls
```

whenever you need evidence.

This is how you learn to understand a sequence rather than memorizing it.

---

# Mission 16 — What Went Wrong?

You are told:

> “I created a folder called `projects`, but when I run `ls`, I can't see it.”

What should you investigate first?

Choose the best first step:

A. Delete everything and start again.

B. Restart the computer.

C. Run `pwd` to find out where you are.

D. Run a random command from the internet.

### Why?

The folder may exist somewhere else because you created it from a different location.

Remember:

> **Commands act from your current location unless you tell them otherwise.**

---

# Mission 17 — Predict the Final Structure

Starting from an empty folder, these commands are run:

```bash
mkdir company
cd company
mkdir projects
mkdir documents
cd projects
mkdir website
touch README.txt
cd ..
touch notes.txt
```

Predict the final structure:

```text
company/
├── ?
├── ?
└── ?
```

Fill it in before running the commands.

### Then verify it yourself

Use the commands you know.

Don't worry if your terminal does not have a fancy tree display.

Use `pwd`, `ls`, and `cd` to investigate.

---

# Mission 18 — Build It Without Instructions

Now you are going to work independently.

Create:

```text
practice-project/
├── src/
│   ├── app/
│   └── config/
├── docs/
│   ├── README.txt
│   └── setup.txt
├── tests/
└── notes/
```

Do not copy a command sequence from this page.

Plan the work yourself.

When finished, verify:

- the folders exist
- the files exist
- the files are in the correct folders
- you can navigate into each major folder
- you can return to the project root

---

# Mission 19 — The Rename Challenge

Inside:

```text
practice-project/docs
```

you have:

```text
README.txt
setup.txt
```

Your team decides that `setup.txt` should be called:

```text
installation.txt
```

Predict the command you would use.

Then perform the rename.

Finally prove that:

```text
setup.txt
```

is gone and:

```text
installation.txt
```

exists.

---

# Mission 20 — The Verification Challenge

You have finished building your project.

Your colleague says:

> “Don't tell me you think it's correct. Prove it.”

This is a verification exercise.

Using only the terminal, prove that your project contains:

```text
practice-project/
├── src/
│   ├── app/
│   └── config/
├── docs/
│   ├── README.txt
│   ├── setup.txt
│   └── installation.txt
├── tests/
└── notes/
```

You may use commands you already know.

The important thing is not the exact command sequence.

The important thing is that your evidence is convincing.

---

# Mini Troubleshooting Lab

## Problem A — “I don't know where I am.”

Use:

```bash
pwd
```

---

## Problem B — “I don't know what's here.”

Use:

```bash
ls
```

---

## Problem C — “I went into the wrong folder.”

First investigate:

```bash
pwd
```

Then decide how many levels you need to move.

Usually:

```bash
cd ..
```

moves you up one level.

---

## Problem D — “I created something but can't see it.”

Ask:

> Where did I create it?

Check:

```bash
pwd
```

Then:

```bash
ls
```

You may simply be looking in a different directory.

---

## Problem E — “The command produced no output.”

Don't automatically assume it failed.

Ask:

> What should have changed?

Then verify the state.

For example:

```bash
ls
```

or:

```bash
pwd
```

This is one of the most important habits in this course.

---

# Boss Challenge — The Terminal Rescue Mission

You have joined a project team.

Your colleague leaves you this message:

> “I was organizing the project and now I don't know where I am. There should be a folder called `team-project` somewhere under my home directory. Inside it there should eventually be `src`, `docs`, and `tests`. I also need a file called `setup.txt` inside `docs`.”

You are not given a command sequence.

Your mission:

1. Find your home directory.
2. Locate or create `team-project`.
3. Build the required folder structure.
4. Create `docs/setup.txt`.
5. Navigate into different parts of the project.
6. Intentionally get yourself into the wrong directory.
7. Recover using investigation.
8. Return to the project root.
9. Prove the final structure.

### Rules

- Do not use a graphical file manager.
- Do not blindly copy commands.
- If you encounter a command you do not understand, investigate it first.
- Use `pwd` and `ls` whenever you are uncertain.
- Verify the final state.

### Success condition

You should be able to explain **what you did and why**, not just show that the final folders exist.

---

# Reflection — What Did You Actually Learn?

Answer these questions in your own words.

### 1. What does `pwd` answer?

> __________________________________________

### 2. What does `ls` answer?

> __________________________________________

### 3. What does `cd` do?

> __________________________________________

### 4. What does `cd ..` mean?

> __________________________________________

### 5. What does `mkdir` do?

> __________________________________________

### 6. What does `touch` do?

> __________________________________________

### 7. What can `mv` be used for?

> __________________________________________

### 8. What is the difference between `mv` and `cp`?

> __________________________________________

### 9. Why should you be careful with `rm`?

> __________________________________________

### 10. What should you do when you are lost?

> __________________________________________

---

# Mastery Test

You are ready to move on when you can complete the following without being given the exact commands:

- [ ] Find your current location.
- [ ] List the contents of a folder.
- [ ] Enter a folder.
- [ ] Move back to the parent folder.
- [ ] Return to your home directory.
- [ ] Create a folder.
- [ ] Create an empty file.
- [ ] Rename a file.
- [ ] Move a file.
- [ ] Copy a file.
- [ ] Safely remove a file.
- [ ] Remove an empty folder.
- [ ] Explain what `..` means.
- [ ] Explain the difference between a file and a folder.
- [ ] Explain the basic idea of an absolute path.
- [ ] Explain the basic idea of a relative path.
- [ ] Recover after intentionally entering the wrong directory.
- [ ] Investigate a simple terminal problem instead of guessing.
- [ ] Verify that a command produced the intended result.

## The real test

Don't ask yourself:

> “Can I remember every command?”

Ask:

> **“If I forget a command tomorrow, do I know how to figure out what I need to do?”**

That is the skill we are building.
