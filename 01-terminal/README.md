# 01 — Your Terminal: Starting From Zero

## Mission

Welcome,

In this lesson, you are not expected to know any terminal commands.

You will learn what the terminal is, how to open it, how to understand where you are, how to see what is around you, and how to create and manage folders and files.

By the end of this lesson, you should be comfortable enough to open a terminal and say:

> “I know where I am, I know what is here, and I know how to move around and create things.”

Do not try to memorize everything.

The goal is to understand **what each command does and why you are using it**.

---

# Part 1 — What Is the Terminal?

A terminal is a way of communicating with your computer by typing instructions.

Normally, you might use a graphical file manager:

- open a folder
- click another folder
- create a new folder
- rename a file
- delete a file

The terminal lets you do many of these things by typing commands instead.

For example, instead of clicking **New Folder**, you can type:

```bash
mkdir my-folder
```

The computer interprets that instruction by creating a folder with the name my-folder.

---

# Part 2 — What Is a Shell?

You will often hear the word **shell**.

For now, keep it simple:

> A shell is the program that reads the commands you type into the terminal and asks the operating system to carry them out.

You may be using CMD, Bash, Zsh, PowerShell, or another shell.

For this course, many examples will use Bash.

You do not need to understand how the shell is implemented.

You only need to understand this relationship:

```text
You
 ↓
type a command
 ↓
Shell reads the command
 ↓
Computer performs the requested action
 ↓
You see the result
```

---

# Part 3 — Open Your Terminal

Open your terminal.

Depending on your computer, it may be called:

- Terminal
- Terminal Emulator
- Powershell
- Git Bash
- Ubuntu Terminal
- Konsole
- GNOME Terminal

If you are using Windows and installed Git for Windows, you can use **Git Bash**.

If you are using Linux, use your normal terminal application.

Do not worry if your screen does not look exactly like someone else's.

Different operating systems and terminal programs can display slightly different prompts.

---

# Part 4 — What Are You Looking At?

When you open a terminal, you will normally see some text followed by a cursor.

For example:

```text
user@computer:~$
```

or:

```text
user@computer:~/Documents$
```

or in Git Bash:

```text
User@COMPUTER MINGW64 ~/Desktop
$
```

The exact appearance is not important.

The important part is:

> The terminal is waiting for you to type an instruction.

You will type a command and press **Enter**.

---

# Part 5 — Your First Command: `pwd`

Let's find out where we are or which folder you (the terminal) are in.

Type:

```bash
pwd
```

Then press **Enter**.

You might see:

```text
/home/user
```

or:

```text
/c/Users/YourName
```

Your result will probably be different.

That's okay.

## What does `pwd` mean?

It means:

**Print Working Directory**

You do not need to memorize the long explanation yet.

Think of it simply as:

> **`pwd` = Where am I?**

The computer is telling you which folder the terminal is currently working inside.

---

# Part 6 — What Is a Directory?

You will see the word **directory** frequently when learning Git and Linux.

A directory is simply another name for a **folder**.

For beginners, think:

```text
directory = folder
```

So if someone says:

> “Create a directory called projects.”

They mean:

> “Create a folder called projects.”

---

# Part 7 — Your First Folder

We are going to create a practice area.

First, make sure you know where you are:

```bash
pwd
```

make sure you are on the desktop. Now create a folder called:

```text
git-essentials-terminal-lab
```

The command for creating a folder is:

```bash
mkdir git-essentials-terminal-lab
```

## What does `mkdir` mean?

It means:

**make directory**

Again, you can think:

```text
mkdir = create a folder
```

Now check what is around you:

```bash
ls
```

You should see:

```text
git-essentials-terminal-lab
```

---

# Part 8 — What Does `ls` Do?

The command:

```bash
ls
```

means:

> **Show me what is inside the current location.**

Think of it like opening a folder and looking at its contents.

For example:

```bash
ls
```

might show:

```text
Documents
Downloads
Pictures
git-essentials-terminal-lab
```

It does not move you anywhere.

It simply shows you what is there.

### Remember

```text
pwd → Where am I?
ls  → What is here?
```

These two commands will become extremely useful.

---

# Part 9 — Entering a Folder With `cd`

We created:

```text
git-essentials-terminal-lab
```

Now we want to enter it.

The command is:

```bash
cd git-essentials-terminal-lab
```

## What does `cd` mean?

It means:

**change directory**

For beginners, remember:

```text
cd = move into a folder
```

Now run:

```bash
pwd
```

The result should now show that you are inside:

```text
git-essentials-terminal-lab
```

You can also run:

```bash
ls
```

It may show nothing.

That's okay.

The folder is currently empty.

---

# Part 10 — Going Back Up With `cd ..`

Now suppose you are inside:

```text
git-essentials-terminal-lab
```

and want to go back to the folder that contains it.

Run:

```bash
cd ..
```

The two dots mean:

> the directory above the current directory

Now run:

```bash
pwd
```

You should be back where you were before entering the lab folder.

Think of:

```text
cd ..
```

as:

> **Go up one folder.**

---

# Part 11 — Do Not Guess Where You Are

This is an important habit.

If you are unsure where you are, don't guess.

Run:

```bash
pwd
```

If you are unsure what is around you, run:

```bash
ls
```

So when confused:

```text
Where am I?
→ pwd

What's here?
→ ls
```

This habit will become extremely important when working with Git repositories.

---

# Part 12 — Create Several Folders

Now we are going to create folders inside our lab.

First enter the lab:

```bash
cd git-essentials-terminal-lab
```

Check:

```bash
pwd
```

Now create a folder called:

```text
projects
```

Use:

```bash
mkdir projects
```

Check:

```bash
ls
```

You should see:

```text
projects
```

Now enter it:

```bash
cd projects
```

Check:

```bash
pwd
```

You should now be inside:

```text
git-essentials-terminal-lab/projects
```

---

# Part 13 — Create a Folder Inside Another Folder

While inside `projects`, create:

```text
website
```

Run:

```bash
mkdir website
```

Then create:

```text
api
```

Run:

```bash
mkdir api
```

Now:

```bash
ls
```

You should see:

```text
api
website
```

Your structure now looks like:

```text
git-essentials-terminal-lab/
└── projects/
    ├── api/
    └── website/
```

---

# Part 14 — Create Another Folder

Go back to the lab folder:

```bash
cd ..
```

Remember:

```text
cd .. = go up one folder
```

You should now be inside:

```text
git-essentials-terminal-lab
```

Create:

```text
notes
```

```bash
mkdir notes
```

Create:

```text
exercises
```

```bash
mkdir exercises
```

Now your structure should be:

```text
git-essentials-terminal-lab/
├── projects/
│   ├── api/
│   └── website/
├── notes/
└── exercises/
```

---

# Part 15 — Creating a File

So far we have created folders.

Now we need to create a file.

The command commonly used to create an empty file is:

```bash
touch
```

Let's create:

```text
day-1.txt
```

inside the `notes` folder.

First enter `notes`:

```bash
cd notes
```

Then:

```bash
touch day-1.txt
```

Now:

```bash
ls
```

You should see:

```text
day-1.txt
```

So:

```text
mkdir → create a folder
touch → create an empty file
```

---

# Part 16 — Understanding Files and Folders

At this point you have created:

```text
folder
folder
folder
file
```

The computer treats files and folders differently.

For example:

```text
notes/
```

is a folder.

Inside it:

```text
day-1.txt
```

is a file.

The `.txt` part is the file extension.

It indicates that this is a text file.

---

# Part 17 — Renaming Something

You also need to know how to rename things.

Suppose we want to rename:

```text
day-1.txt
```

to:

```text
lesson-1.txt
```

A common command is:

```bash
mv day-1.txt lesson-1.txt
```

Here `mv` means **move**.

It can also be used to rename something.

After running it:

```bash
ls
```

You should see:

```text
lesson-1.txt
```

and not:

```text
day-1.txt
```

So remember:

```text
mv old-name new-name
```

can rename an item.

---

# Part 18 — Moving a File

`mv` can also move a file into another folder.

For example, from the `notes` folder:

```bash
mv lesson-1.txt ../exercises/
```

This means:

> Move `lesson-1.txt` into the `exercises` folder.

The `..` means:

> Go up one folder.

So:

```text
../
```

means:

> the parent folder

After moving the file, check:

```bash
ls
```

It should no longer be in `notes`.

Now enter:

```bash
cd ../exercises
```

and run:

```bash
ls
```

You should find:

```text
lesson-1.txt
```

---

# Part 19 — Copying a File

Sometimes you don't want to move something.

You want to make a copy.

The command is:

```bash
cp
```

which means **copy**.

Suppose:

```text
lesson-1.txt
```

is inside `exercises`.

Create a copy called:

```text
lesson-1-copy.txt
```

Run:

```bash
cp lesson-1.txt lesson-1-copy.txt
```

Then:

```bash
ls
```

You should see:

```text
lesson-1-copy.txt
lesson-1.txt
```

There are now two files.

---

# Part 20 — Removing a File

Be careful with this command.

To remove a file:

```bash
rm
```

means **remove**.

For example:

```bash
rm lesson-1-copy.txt
```

Then:

```bash
ls
```

The copy should be gone.

### Important

Unlike a graphical file manager, terminal deletion can be much less forgiving.

Do not randomly type `rm` commands.

Before deleting something, make sure you know:

1. where you are
2. what you are deleting
3. why you are deleting it

When in doubt:

```bash
pwd
ls
```

---

# Part 21 — Removing an Empty Folder

Suppose you have an empty folder called:

```text
old-folder
```

You can remove an empty directory with:

```bash
rmdir old-folder
```

`rmdir` means:

**remove directory**

We will learn more powerful deletion commands later.

For now, don't experiment with commands such as:

```bash
rm -rf
```

unless the lesson specifically teaches them.

---

# Part 22 — Going Home

There is another useful command:

```bash
cd ~
```

The `~` symbol represents your home directory.

So:

```bash
cd ~
```

means:

> Go to my home directory.

You don't have to understand every detail about `~` yet.

Just remember that it is a convenient way to return home.

---

# Part 23 — Absolute and Relative Paths

Now we can introduce an important idea.

There are two common ways to describe where something is.

## Absolute path

An absolute path gives the complete location.

For example:

```text
/home/paakow/projects/website
```

or on Git Bash:

```text
/c/Users/Owner/Downloads/git-essentials-terminal-lab
```

It tells you the complete route from the filesystem's starting point.

## Relative path

A relative path describes a location based on **where you are now**.

For example, if you are inside:

```text
git-essentials-terminal-lab
```

you can refer to:

```text
projects
```

without writing the entire path.

This is why your current location matters.

---

# Part 24 — The Most Important Mental Model

The terminal always has a current location.

Think of yourself as standing inside a folder.

```text
computer
└── Downloads
    └── git-essentials-terminal-lab
        ├── projects
        ├── notes
        └── exercises
```

If you are standing here:

```text
git-essentials-terminal-lab
```

then:

```bash
cd projects
```

means:

> Go into the `projects` folder from where I currently am.

If you are standing inside:

```text
projects
```

then:

```bash
cd ..
```

means:

> Go back to the folder above me.

This is the foundation of terminal navigation.

---

# Part 25 — Hidden Files

You already learned:

```bash
ls
```

There is another version:

```bash
ls -la
```

For now, don't worry about every letter.

Understand the result:

```bash
ls
```

shows normal visible items.

```bash
ls -la
```

also shows hidden items and provides additional information.

Later, when we work with Git repositories, you will encounter a very important hidden folder:

```text
.git
```

Do not delete it.

That folder is what turns an ordinary project directory into a Git repository.

We will learn exactly what it does in a later lesson.

---

# Part 26 — Practice: Build This Yourself

Now stop following commands one by one.

Your job is to build this structure:

```text
terminal-project/
├── src/
│   ├── app/
│   └── config/
├── docs/
└── tests/
```

And create these files:

```text
docs/setup.txt
src/app/main.txt
```

### Important

Do not copy a command sequence from the lesson.

First think:

1. Where should `terminal-project` be?
2. How do I create a folder?
3. How do I enter it?
4. How do I create `src`?
5. How do I create `app` and `config`?
6. How do I create `docs` and `tests`?
7. How do I create the files?

Use the commands you have learned.

---

The goal is not:

> “I memorized 12 commands.”

The goal is:

> **“I understand what I'm doing in the terminal, and I can figure out what to do next.”**

> **Now, proceed with the practice drill**
