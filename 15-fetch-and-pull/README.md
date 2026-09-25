# 15 — Fetch & Pull: Keeping Your Local Work Up to Date

## Mission

Understand the difference between receiving remote information and integrating it.

## Learning outcomes

- fetch
- remote-tracking information
- pull
- local changes
- divergence
- synchronisation
- conflict preparation

## The mental model

Before learning the commands for **Fetch & Pull: Keeping Your Local Work Up to Date**, understand the problem they solve. Git operations are safest when you can describe the current state and the desired state in ordinary language first.

### The core loop

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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


- Lessons 12–14: remotes, push, and clone.

## Detailed teaching guide

### 1. Why remote state changes

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **1. Why remote state changes** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **1. why remote state changes**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Other people can push commits while you are working. Your local repository therefore can become behind the remote.

### 2. Fetch

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **2. Fetch** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **2. fetch**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Fetch retrieves remote information without automatically integrating it into your current branch.

### 3. Remote-tracking information

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **3. Remote-tracking information** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **3. remote-tracking information**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Git keeps local references describing remote branches so you can investigate remote state without immediately changing your current branch.

### 4. Pull

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **4. Pull** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **4. pull**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Pull generally fetches and then integrates remote changes according to configured behavior. The integration part is why local state matters first.

### 5. Status before integration

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **5. Status before integration** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **5. status before integration**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Check `git status` before pulling so you know whether you have local changes that may be affected.

### 6. Divergence

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **6. Divergence** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **6. divergence**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


When local and remote branches both contain unique commits, integration becomes a history decision rather than a simple download.

### 7. Fetch as investigation

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **7. Fetch as investigation** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **7. fetch as investigation**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Fetch is useful when you want to learn what the remote has changed before deciding how to integrate it.

### 8. Pull is not magic

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **8. Pull is not magic** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **8. pull is not magic**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Pull may produce a merge, another configured integration strategy, or a conflict. Read the result and inspect the state.

### 9. Push versus pull

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **9. Push versus pull** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **9. push versus pull**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Push moves committed local history toward the remote; fetch retrieves remote information; pull retrieves and integrates remote work.

### 10. Safe synchronisation

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **10. Safe synchronisation** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **10. safe synchronisation**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Inspect local work → learn remote state → choose integration → integrate → verify.

## Command reference

### `git fetch`

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **`git fetch`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git fetch`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Retrieves remote information without automatically integrating it into the current branch.

### `git pull`

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

In this section, treat **`git pull`** as a real situation rather than a command to memorise. Ask what problem exists, what information Git already has, what you want to change, and how you will prove the result.

#### Step-by-step thinking

1. **Describe the goal in plain language.** Do not start with a command.
2. **Inspect the current state.** Use the information Git already provides.
3. **Predict the result.** Write down what you expect to happen.
4. **Perform the smallest appropriate operation.** Avoid unrelated changes.
5. **Read Git's output.** It often tells you what happened or what is required next.
6. **Verify the result.** Check the repository state, files, history, or project behavior as appropriate.

#### Example situation

Imagine a teammate asks you to deal with a problem involving **`git pull`**. You have not been given a command recipe. Your first response should be investigation: determine the current state, identify the desired state, and find the relevant documentation if you need syntax or options.

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


Fetches and integrates remote changes according to configuration.

### `git status`

#### Why this matters

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

Remote repositories change independently of your computer. Safe synchronisation begins with knowing your local state.

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

- [ ] I can explain **fetch** in my own words.
- [ ] I can explain **remote-tracking information** in my own words.
- [ ] I can explain **pull** in my own words.
- [ ] I can explain **local changes** in my own words.
- [ ] I can explain **divergence** in my own words.
- [ ] I can explain **synchronisation** in my own words.
- [ ] I can explain **conflict preparation** in my own words.

## Mastery checkpoint

You should be able to complete the fetch & pull: keeping your local work up to date practice drills without being given a command-by-command recipe. If you forget a command, use documentation and your understanding of repository state to find it.

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
