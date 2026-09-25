# 22 — Cherry-Pick: Bringing One Commit Across

## Mission

Select one commit and apply its change to another branch deliberately.

## Learning outcomes

- specific commit selection
- target branch
- cherry-pick
- new commit identity
- conflicts
- verification
- merge versus cherry-pick

## The mental model

Before learning the commands for **Cherry-Pick: Bringing One Commit Across**, understand the problem they solve. Git operations are safest when you can describe the current state and the desired state in ordinary language first.

### The core loop

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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


- Lessons 07, 11, and 17: history, integration, and conflicts.

## Detailed teaching guide

### 1. The one-commit problem

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **1. The one-commit problem** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **1. the one-commit problem**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Sometimes a complete branch contains one fix you need elsewhere. Cherry-pick lets you select that specific commit.

### 2. Identify the commit

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **2. Identify the commit** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **2. identify the commit**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Use history to identify the exact commit containing the desired change. Inspect it before applying it elsewhere.

### 3. Verify target branch

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **3. Verify target branch** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **3. verify target branch**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Cherry-pick applies to the branch you are currently on. Confirm the target before running it.

### 4. Cherry-pick

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **4. Cherry-pick** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **4. cherry-pick**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


`git cherry-pick <commit>` applies the selected commit's changes to the current branch, normally creating a new commit.

### 5. New history identity

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **5. New history identity** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **5. new history identity**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


The resulting commit normally has a new identifier because it is a new commit in the target history.

### 6. Selective transfer

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **6. Selective transfer** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **6. selective transfer**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Cherry-pick is useful when you want one isolated change rather than the entire source branch.

### 7. Conflicts

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **7. Conflicts** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **7. conflicts**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


A selected commit may conflict with the target branch. Use the conflict workflow from Lesson 17.

### 8. Verification

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **8. Verification** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **8. verification**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Inspect status, history, actual files, and tests after cherry-picking.

### 9. Merge versus cherry-pick

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **9. Merge versus cherry-pick** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **9. merge versus cherry-pick**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Ask whether you want the entire development line or one particular change. That often determines whether merge or cherry-pick is appropriate.

### 10. Duplicate logical changes

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **10. Duplicate logical changes** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **10. duplicate logical changes**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Applying the same logical change through multiple routes can make history confusing. Investigate before applying another copy.

## Command reference

### `git cherry-pick <commit>`

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

In this section, treat **`git cherry-pick <commit>`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git cherry-pick <commit>`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Applies a specific commit to the current branch.

### `git log --oneline`

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

### `git status`

#### Why this matters

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

Cherry-pick is precise because it selects one commit. Precision still requires verification and awareness of history.

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

- [ ] I can explain **specific commit selection** in my own words.
- [ ] I can explain **target branch** in my own words.
- [ ] I can explain **cherry-pick** in my own words.
- [ ] I can explain **new commit identity** in my own words.
- [ ] I can explain **conflicts** in my own words.
- [ ] I can explain **verification** in my own words.
- [ ] I can explain **merge versus cherry-pick** in my own words.

## Mastery checkpoint

You should be able to complete the cherry-pick: bringing one commit across practice drills without being given a command-by-command recipe. If you forget a command, use documentation and your understanding of repository state to find it.

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
