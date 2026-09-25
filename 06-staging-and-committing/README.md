# 06 — Staging & Committing: Choosing What to Record

## Mission

Learn why Git separates changing files, selecting changes, and recording history.

## Learning outcomes

- working tree versus staging area
- git add
- selective staging
- git add .
- commits
- commit messages
- verification
- meaningful history

## The mental model

Before learning the commands for **Staging & Committing: Choosing What to Record**, understand the problem they solve. Git operations are safest when you can describe the current state and the desired state in ordinary language first.

### The core loop

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **The core loop** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **the core loop**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


```text
UNDERSTAND
   ↓
INSPECT
   ↓
PREDICT
   ↓
ACT
   ↓
VERIFY
```

If the result is not what you expected:

```text
STOP → INSPECT → UNDERSTAND → RECOVER → VERIFY
```

## Before you begin

### What you should already know

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **What you should already know** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **what you should already know**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


- Lesson 05: how Git describes untracked and modified files.

## Detailed teaching guide

### 1. Why staging exists

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **1. Why staging exists** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **1. why staging exists**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


The staging area lets you choose which current changes should become part of the next commit. It prevents unrelated edits from automatically becoming one historical event.

### 2. Working tree, staging area, and commit

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **2. Working tree, staging area, and commit** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **2. working tree, staging area, and commit**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Keep these separate: the working tree contains current files; the staging area is your selection for the next commit; a commit is a recorded historical point. Moving through these states is a deliberate process.

### 3. Stage one file

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **3. Stage one file** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **3. stage one file**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Use `git add <file>` when you want one file's current change selected for the next commit. Immediately run `git status` so you can see the selection.

### 4. Stage several files selectively

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **4. Stage several files selectively** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **4. stage several files selectively**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


You can stage files individually. This is useful when several unrelated changes exist and only some belong in the next commit.

### 5. What git add . means

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **5. What git add . means** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **5. what git add . means**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


`git add .` is convenient, but it should not be a reflex. It stages eligible changes under the current directory. Inspect status first when the working tree contains unrelated work.

### 6. Inspect before commit

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **6. Inspect before commit** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **6. inspect before commit**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Before committing, ask what the staged set represents. The question is not "Did I run git add?" but "If I commit now, am I recording the change I intend?"

### 7. Commit messages

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **7. Commit messages** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **7. commit messages**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


A commit message should communicate purpose. Prefer concise descriptions such as `Fix empty password validation` over `update` or `changes`.

### 8. Create and verify a commit

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **8. Create and verify a commit** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **8. create and verify a commit**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Create the commit from the staged changes, then run `git status` and `git log --oneline`. Verification is part of the operation, not an optional extra.

### 9. Meaningful commit boundaries

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **9. Meaningful commit boundaries** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **9. meaningful commit boundaries**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


A useful commit usually represents a coherent piece of work. Avoid both extremes: one enormous mixed commit and hundreds of meaningless micro-commits.

### 10. What a commit is not

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **10. What a commit is not** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **10. what a commit is not**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


A commit is not the same as saving a file, pushing to GitHub, backing up your computer, or proving that the software works. It is a recorded point in Git history.

## Command reference

### `git add <file>`

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **`git add <file>`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git add <file>`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Stages the current change to the named file.

### `git add .`

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **`git add .`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git add .`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Stages eligible changes under the current directory.

### `git status`

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **`git status`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git status`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Shows repository state, including branch and reported changes.

### `git commit -m "message"`

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **`git commit -m "message"`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git commit -m "message"`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Creates a commit from the currently staged changes.

### `git log --oneline`

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **`git log --oneline`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git log --oneline`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Shows a compact commit history.

## Common mistakes and troubleshooting

### Running commands in the wrong folder

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **Running commands in the wrong folder** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **running commands in the wrong folder**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Use `pwd`, `ls`, and `git status` before changing repository configuration.

### Acting before checking state

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **Acting before checking state** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **acting before checking state**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Stop and inspect status. Git usually gives you enough information to decide the next step.

### Copying a command without understanding it

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **Copying a command without understanding it** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **copying a command without understanding it**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Use the documentation habit from Lesson 02. Understand what the command changes and how to verify it.

### Assuming success means correctness

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **Assuming success means correctness** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **assuming success means correctness**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


A command can succeed while the project remains logically wrong. Test and inspect the result.

### Using a destructive operation casually

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **Using a destructive operation casually** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **using a destructive operation casually**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Preserve important work and understand what will be discarded or rewritten before running it.

### Forgetting the current branch

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **Forgetting the current branch** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **forgetting the current branch**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Run `git branch` or `git status` before branch-sensitive operations.

### Ignoring Git output

#### Why this matters

The staging area is a deliberate selection point. The goal is not to stage quickly; it is to create an accurate historical record.

In this section, treat **Ignoring Git output** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **ignoring git output**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

A useful written plan is:

```text
Goal:
Current state:
Evidence I have:
Operation I am considering:
What I expect:
How I will verify:
```

#### What beginners often get wrong

- Starting with a command instead of a goal.
- Assuming the current branch or repository location.
- Treating an error message as a reason to panic instead of information.
- Running several commands before checking the result of the first one.
- Using a destructive option because a random tutorial recommended it.
- Declaring success because a command returned without an error.

#### Verification checklist

- [ ] I know what state I started in.
- [ ] I know what I intended to change.
- [ ] I can explain what the operation changed.
- [ ] I checked the resulting Git state.
- [ ] I checked the actual project result when relevant.
- [ ] I can explain what I would do if the result were unexpected.


Git often tells you exactly what happened or what it expects next. Read the complete message.

## What you should be able to explain

- [ ] I can explain **working tree versus staging area** in my own words.
- [ ] I can explain **git add** in my own words.
- [ ] I can explain **selective staging** in my own words.
- [ ] I can explain **git add .** in my own words.
- [ ] I can explain **commits** in my own words.
- [ ] I can explain **commit messages** in my own words.
- [ ] I can explain **verification** in my own words.
- [ ] I can explain **meaningful history** in my own words.

## Mastery checkpoint

You should be able to complete the staging & committing: choosing what to record practice drills without being given a command-by-command recipe. If you forget a command, use documentation and your understanding of repository state to find it.

## Learning a command instead of memorising a command

For every new command, answer these questions:

1. **What problem does it solve?**
2. **What repository state should I be in before using it?**
3. **What does it change?**
4. **What does it not change?**
5. **What could go wrong?**
6. **How can I undo or recover if necessary?**
7. **How do I verify the result?**

If you cannot answer these questions, you are not ready to use an advanced option blindly. Look it up.

## Documentation habit

The course intentionally does not require you to remember every option. When you forget syntax:

```text
Remember the goal
      ↓
Inspect the state
      ↓
Search official documentation
      ↓
Read the relevant example/options
      ↓
Understand before executing
      ↓
Run the smallest safe operation
      ↓
Verify
```

## Prediction drill

Choose one operation from this lesson. Before running it, write:

```text
I am currently: __________________________
I want: __________________________________
I think Git will: ________________________
If I am wrong, I will first: ______________
I will verify by: _________________________
```

Then perform the operation and compare the actual result with the prediction. A wrong prediction is not a failure; it is evidence that your mental model needs improvement.

## Break-it principle

Practice difficult Git operations in a disposable repository. A safe practice environment lets you experience errors, conflicts, recovery, and history changes without risking important work.

Never turn a practice exercise into an experiment on an important production repository.

## Mastery interview

Explain this lesson to someone who has never used Git. Do not begin with commands. Begin with the problem Git is solving. Then explain the mental model, the normal workflow, the common mistake, and the verification step.

If you can explain the concept clearly without relying on command names, you understand it better than if you can merely type the command.
