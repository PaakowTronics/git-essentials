# 11 — Bringing Work Together: Merging

## Mission

Bring separate lines of development together deliberately and verify the result.

## Learning outcomes

- source and destination
- git merge
- fast-forward
- merge commit
- history graph
- post-merge verification

## The mental model

Before learning the commands for **Bringing Work Together: Merging**, understand the problem they solve. Git operations are safest when you can describe the current state and the desired state in ordinary language first.

### The core loop

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

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

Merging combines lines of development. The destination branch and the final project state matter.

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


- Lesson 10: creating and switching branches.

## Detailed teaching guide

### 1. Merge direction

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **1. Merge direction** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **1. merge direction**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


To bring feature work into main, main is the destination. Switch to main first, then merge the feature branch into it.

### 2. Simple merge

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **2. Simple merge** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **2. simple merge**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


A merge combines histories. After merging, inspect status and history rather than assuming the result is correct.

### 3. Fast-forward

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **3. Fast-forward** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **3. fast-forward**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


If the destination has not diverged, Git may only move the destination pointer forward. No separate merge commit is required in that case.

### 4. Diverged histories

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **4. Diverged histories** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **4. diverged histories**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


When both branches contain unique commits, Git must combine the histories rather than simply moving one pointer forward.

### 5. Merge commit

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **5. Merge commit** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **5. merge commit**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


A merge commit can record the point where two lines were brought together. Its presence depends on the history and merge strategy.

### 6. History graph

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **6. History graph** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **6. history graph**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


`git log --oneline --graph --decorate --all` gives a visual view of branch relationships. Use it as evidence, not decoration.

### 7. Verify after merge

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **7. Verify after merge** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **7. verify after merge**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Check Git status, inspect history, and test the project. A successful merge is a version-control result, not an application-quality guarantee.

### 8. Merge versus copy

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **8. Merge versus copy** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **8. merge versus copy**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Git is combining changes and history relationships. It is not simply copying one folder over another.

### 9. Preparing for conflicts

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **9. Preparing for conflicts** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **9. preparing for conflicts**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Overlapping changes may stop a merge. Read the status and conflict instructions rather than trying random commands.

### 10. Safe merge workflow

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **10. Safe merge workflow** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **10. safe merge workflow**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Inspect → identify destination → switch → merge → read output → status → inspect history → test.

## Command reference

### `git merge <branch>`

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **`git merge <branch>`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git merge <branch>`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Merges the named branch into the branch you are currently on.

### `git log --oneline --graph --decorate --all`

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

In this section, treat **`git log --oneline --graph --decorate --all`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git log --oneline --graph --decorate --all`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Shows a compact visual branch/history graph.

### `git status`

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

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

## Common mistakes and troubleshooting

### Running commands in the wrong folder

#### Why this matters

Merging combines lines of development. The destination branch and the final project state matter.

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

Merging combines lines of development. The destination branch and the final project state matter.

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

Merging combines lines of development. The destination branch and the final project state matter.

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

Merging combines lines of development. The destination branch and the final project state matter.

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

Merging combines lines of development. The destination branch and the final project state matter.

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

Merging combines lines of development. The destination branch and the final project state matter.

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

Merging combines lines of development. The destination branch and the final project state matter.

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

- [ ] I can explain **source and destination** in my own words.
- [ ] I can explain **git merge** in my own words.
- [ ] I can explain **fast-forward** in my own words.
- [ ] I can explain **merge commit** in my own words.
- [ ] I can explain **history graph** in my own words.
- [ ] I can explain **post-merge verification** in my own words.

## Mastery checkpoint

You should be able to complete the bringing work together: merging practice drills without being given a command-by-command recipe. If you forget a command, use documentation and your understanding of repository state to find it.

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
