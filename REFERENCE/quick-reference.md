# Git Essentials — Quick Reference

This is a **reference**, not a lesson.

If you do not understand a command, return to the appropriate lesson before using it.

---

# The Core Habit

For important operations:

```text
PREDICT
   ↓
RUN
   ↓
INSPECT
   ↓
VERIFY
```

When confused:

```text
Where am I?
→ pwd

What's here?
→ ls

What's the Git state?
→ git status

What happened recently?
→ git log
```

---

# Terminal

| Command | What it is for |
|---|---|
| `pwd` | Show current directory |
| `ls` | List directory contents |
| `ls -la` | List visible and hidden entries with details |
| `cd folder` | Enter a folder |
| `cd ..` | Go up one folder |
| `cd ~` | Go to home directory |
| `mkdir name` | Create a directory |
| `touch file` | Create an empty file |
| `mv old new` | Move or rename |
| `cp source destination` | Copy |
| `rm file` | Remove a file |
| `rmdir folder` | Remove an empty directory |

Be careful with destructive commands.

---

# Start or Inspect a Repository

```bash
git init
```

Create a Git repository in the current directory.

```bash
git status
```

Inspect the current repository state.

```bash
git branch
```

List local branches.

```bash
git remote -v
```

Inspect configured remotes.

---

# Inspect Changes

```bash
git status
```

What has changed?

```bash
git diff
```

What are the current unstaged content changes?

```bash
git diff --staged
```

What changes are staged?

---

# Commit

```bash
git add <file>
```

Stage a file.

```bash
git add .
```

Stage changes under the current directory. Inspect carefully before committing.

```bash
git commit -m "Describe the change"
```

Create a commit.

```bash
git log
```

Read commit history.

```bash
git log --oneline
```

Read compact history.

---

# Branches

```bash
git branch
```

List branches.

```bash
git switch -c <branch>
```

Create and switch to a branch.

```bash
git switch <branch>
```

Switch branches.

Before switching, inspect your working state.

---

# Merge

```bash
git merge <branch>
```

Integrate another branch into the current branch.

If a conflict occurs:

```text
1. Read status
2. Open conflicted files
3. Understand both changes
4. Edit intentionally
5. Stage resolved files
6. Complete the merge
7. Verify
```

---

# Remotes

```bash
git clone <repository>
```

Create a local copy of a remote repository.

```bash
git fetch
```

Download remote information without integrating it into the current branch.

```bash
git pull
```

Fetch and integrate according to the configured pull behaviour.

```bash
git push
```

Send local commits to the remote.

Remember:

```text
fetch ≠ merge your work
push ≠ commit
pull ≠ magic synchronization
```

Understand the state before using them.

---

# Undoing Everyday Mistakes

Do not choose an undo command merely because it sounds familiar.

First ask:

```text
What exactly happened?
What do I want to keep?
What do I want to remove?
Has the change been committed?
Has it been shared?
```

Then choose the operation.

Useful commands include:

```bash
git restore <file>
```

Restore a working-tree file from its source.

```bash
git restore --staged <file>
```

Remove a file from the staging area without necessarily discarding its working-tree changes.

For committed changes, consider whether you need to:

- correct a local commit;
- revert a shared change;
- inspect history first.

Never blindly use destructive commands.

---

# Reflog

```bash
git reflog
```

Show local reference movement.

Useful when:

- a branch moved;
- a commit seems lost;
- you switched or reset unexpectedly;
- you need to locate an earlier position.

Reflog is an investigation tool.

Do not panic when a commit disappears from normal branch history.

---

# Stash

```bash
git stash
```

Temporarily save suitable local working changes.

```bash
git stash list
```

List stashes.

```bash
git stash pop
```

Apply a stash and remove it from the stash list if successful.

Use stash for a clear temporary-work problem. Do not use it simply because the working tree looks complicated.

---

# Rebase

```bash
git rebase <base>
```

Replay commits onto another base.

Before rebasing:

- understand the branch;
- understand which commits will be replayed;
- know whether the branch is shared;
- be prepared to resolve conflicts.

After rebasing, inspect history.

---

# Cherry-pick

```bash
git cherry-pick <commit>
```

Apply the change introduced by a specific commit to the current branch.

Use it when the problem is:

> “I need this particular commit.”

Do not use it merely because you know the command.

---

# Useful Inspection Commands

```bash
git status
git log --oneline --decorate --graph --all
git diff
git diff --staged
git branch -vv
git remote -v
git show <commit>
git reflog
```

These are often more valuable than immediately changing repository state.

---

# When You Are Stuck

Use this sequence:

```text
STOP
 ↓
Read the error
 ↓
Run git status
 ↓
Inspect the relevant history/diff
 ↓
Identify what you expected
 ↓
Identify what actually happened
 ↓
Check documentation
 ↓
Choose the smallest appropriate action
 ↓
Verify
```

---

# The Most Important Rule

Do not memorise this page instead of understanding Git.

Use it as a map.

The real skill is knowing:

> **What problem am I solving?**

and:

> **What evidence do I need before I change anything?**
