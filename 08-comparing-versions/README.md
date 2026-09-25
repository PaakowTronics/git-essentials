# 08 — Comparing Versions: Finding Exactly What Changed

## Mission

Move from knowing that something changed to proving exactly what changed.

## Learning outcomes

- git diff
- unstaged changes
- staged changes
- git diff --staged
- commit comparisons
- reading + and -
- review before commit

## The mental model

Before learning the commands for **Comparing Versions: Finding Exactly What Changed**, understand the problem they solve. Git operations are safest when you can describe the current state and the desired state in ordinary language first.

### The core loop

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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


- Lessons 06–07: staging, commits, and history.

## Detailed teaching guide

### 1. Why status is not enough

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **1. Why status is not enough** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **1. why status is not enough**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Status tells you that something changed. A diff tells you what content changed. You need both for careful review.

### 2. First diff

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **2. First diff** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **2. first diff**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Modify a tracked file and run `git diff`. Read the context around each changed line instead of focusing only on the plus and minus symbols.

### 3. Read + and -

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **3. Read + and -** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **3. read + and -**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


A minus line represents content removed from one side of the comparison; a plus line represents content added on the other side. They are comparison markers, not good/bad labels.

### 4. Staged versus unstaged diff

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **4. Staged versus unstaged diff** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **4. staged versus unstaged diff**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


`git diff` and `git diff --staged` inspect different portions of your changes. This is why staging creates a useful review boundary.

### 5. Review staged content

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **5. Review staged content** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **5. review staged content**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Before committing, inspect `git diff --staged` and ask whether the exact content shown belongs in the next historical record.

### 6. Compare commits

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **6. Compare commits** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **6. compare commits**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Comparing two commits lets you investigate how the project changed between two recorded points. It is especially useful during debugging and review.

### 7. Diff as a safety check

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **7. Diff as a safety check** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **7. diff as a safety check**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Diff can catch accidental edits, unrelated changes, debug code, formatting noise, and other surprises before they become history.

### 8. Diff is not testing

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **8. Diff is not testing** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **8. diff is not testing**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


A diff proves what changed. It does not prove that the software behaves correctly. Use the project's tests and verification process as well.

### 9. Large diffs

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **9. Large diffs** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **9. large diffs**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


A large diff is not automatically bad. First identify which files changed, then understand why the changes exist and whether they match the task.

### 10. Review discipline

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **10. Review discipline** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **10. review discipline**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Make diff review a habit: inspect before staging, inspect staged content before committing, and inspect historical differences when investigating.

## Command reference

### `git diff`

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **`git diff`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git diff`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Shows unstaged differences in the working-tree comparison.

### `git diff --staged`

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **`git diff --staged`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git diff --staged`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Shows staged differences.

### `git diff <commit1> <commit2>`

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

In this section, treat **`git diff <commit1> <commit2>`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git diff <commit1> <commit2>`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Compares two recorded commits.

## Common mistakes and troubleshooting

### Running commands in the wrong folder

#### Why this matters

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

A diff is a precise comparison. Use it to replace memory and assumptions with evidence.

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

- [ ] I can explain **git diff** in my own words.
- [ ] I can explain **unstaged changes** in my own words.
- [ ] I can explain **staged changes** in my own words.
- [ ] I can explain **git diff --staged** in my own words.
- [ ] I can explain **commit comparisons** in my own words.
- [ ] I can explain **reading + and -** in my own words.
- [ ] I can explain **review before commit** in my own words.

## Mastery checkpoint

You should be able to complete the comparing versions: finding exactly what changed practice drills without being given a command-by-command recipe. If you forget a command, use documentation and your understanding of repository state to find it.

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
