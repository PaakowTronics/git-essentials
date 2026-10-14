# 12 — GitHub: Accounts, Repositories, Identity & Authentication — Practice Drills

## Drill philosophy

Use the course loop:

```text
PREDICT → RUN → VERIFY → EXPLAIN
```

Do not turn these exercises into command-copying exercises.

For every mission, write down:

```text
Goal:
Current state:
Evidence:
Prediction:
Action:
Result:
Verification:
What I learned:
```

Use a throwaway/test repository whenever an exercise could affect a real project.

Never place real credentials, private keys, or tokens in the exercise repository.

---

## Mission 1 — Build the Git/GitHub map

### Goal

Prove that you understand the boundary between Git and GitHub.

### Predict

Without opening a terminal, classify these as primarily Git concepts or GitHub platform concepts:

- commit
- branch
- remote
- pull request
- issue
- tag
- release
- Actions workflow
- repository visibility
- merge conflict
- SSH authentication

### Do the work

Create a two-column table in a temporary notes file.

Then explain the cases that cross the boundary, such as a Git commit appearing on GitHub.

### Verify

Explain this flow in your own words:

```text
local commit → push → GitHub repository → pull request → review → merge
```

### Mastery question

Why can Git work without GitHub?

---

## Mission 2 — Explore a GitHub repository as a platform

### Goal

Learn the important repository areas before using them.

### Do the work

Open a public GitHub repository you are allowed to inspect.

Find:

- Code
- Issues
- Pull requests
- Actions
- Projects, if enabled
- Releases
- Settings, if you have access

### Record

For each area, answer:

1. What is it for?
2. What kind of object does it contain?
3. Is it part of Git itself or a GitHub feature?
4. What could go wrong if a developer misunderstood its purpose?

### Mastery question

Explain the difference between a commit, an issue, a pull request, and a release.

---

## Mission 3 — Create a safe practice repository

Create a small repository specifically for this lesson.

Choose deliberately:

- name;
- visibility;
- README;
- `.gitignore` template, if useful;
- license.

### Prediction

Before clicking Create repository, predict what files GitHub will create for you.

### Verify

After creation, inspect the repository and explain what GitHub created and what it did not create.

Then clone the repository locally and inspect:

```bash
git status
git remote -v
git log --oneline --decorate -n 5
```

---

## Mission 4 — Discover your Git commit identity

### Goal

Understand what email your local Git commits will use.

Run:

```bash
git config --global user.name
git config --global user.email
git config --local user.name
git config --local user.email
```

Then:

```bash
git config --list --show-origin
```

### Investigate

Answer:

- Which values come from global configuration?
- Which values come from local configuration?
- Which scope wins if both define the same key?
- What email will the next commit use?

### Verify

Create a harmless test commit and inspect its author information with:

```bash
git log -1 --format=fuller
```

Do not push a personal email to a public repository if you do not want it exposed.

---

## Mission 5 — Configure GitHub-safe commit email

### Goal

Learn to protect personal email while preserving attribution.

### Research

Open GitHub account email settings and identify your GitHub-provided `noreply` address.

Do not paste it into this exercise response if you consider it private.

### Predict

What should happen if Git's commit email is changed to the GitHub-associated `noreply` address?

### Do the work

Configure the test repository deliberately.

Then create a test commit.

### Verify

Check both:

```bash
git log -1 --format=fuller
```

and the commit on GitHub.

Confirm that the commit is attributed to the expected GitHub account.

### Explain

Why is an arbitrary fake email a poor solution to the privacy problem?

---

## Mission 6 — Existing SSH key investigation

### Goal

Learn the correct first step before generating SSH credentials.

Run:

```bash
ls -la ~/.ssh
```

### Predict

Which files would indicate an Ed25519 key pair?

### Investigate

Identify:

- private key;
- public key;
- known hosts file;
- SSH configuration, if present.

Do not print or upload your private key.

### Verify

Explain why `id_ed25519.pub` can be uploaded to GitHub while `id_ed25519` must remain private.

---

## Mission 7 — Generate an SSH key safely

Use a test machine/account if you already have production SSH keys.

### Goal

Understand every part of key generation rather than memorizing one command.

Use the official GitHub documentation and determine the appropriate command for your operating system.

A typical Linux example is:

```bash
ssh-keygen -t ed25519 -C "your-github-email@example.com"
```

### Predict

Before running it, explain:

- what is being generated;
- what the private key is for;
- what the public key is for;
- why a passphrase is useful;
- why overwriting an existing key can be dangerous.

### Verify

Confirm that the pair exists and has appropriate permissions.

Never commit either key to a repository.

---

## Mission 8 — Configure `ssh-agent`

### Goal

Understand the agent as a helper for using private keys, not as a replacement for the key itself.

On a typical Linux shell:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

Then inspect loaded identities:

```bash
ssh-add -l
```

### Investigate

Answer:

- Where is the private key stored?
- What does the agent store?
- What happens if the agent has no identities?
- Does starting an agent automatically give GitHub permission?

---

## Mission 9 — Add the public key to GitHub

### Goal

Connect the local key pair to your GitHub account.

Display only the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Add it under GitHub account settings → SSH and GPG keys as an **authentication** key.

### Verify

Confirm that the key appears in the correct GitHub account.

Then test:

```bash
ssh -T git@github.com
```

### Evidence

Record only:

```text
SSH authentication: SUCCESS / FAILURE
GitHub account recognized: YES / NO
```

Do not record the private key or token.

---

## Mission 10 — Break and diagnose SSH authentication

### Scenario

You have a repository whose remote uses SSH, but push returns:

```text
Permission denied (publickey).
```

You are not allowed to solve it by generating a random second key.

### Investigation order

Determine which layer failed:

```text
1. Does a key exist?
2. Is the expected key available to SSH?
3. Is the public key registered with GitHub?
4. Is SSH authenticating to GitHub?
5. Is the remote URL correct?
6. Does the account have repository access?
7. Is a branch/ruleset preventing the operation?
```

Useful evidence:

```bash
ls -la ~/.ssh
ssh-add -l
ssh -T git@github.com
git remote -v
```

For deeper diagnosis:

```bash
ssh -vT git@github.com
```

### Mastery requirement

Explain which layer failed before changing anything.

---

## Mission 11 — HTTPS and personal access tokens

### Goal

Understand the alternative authentication model.

Research GitHub's current documentation on personal access tokens.

Answer:

1. Why is a GitHub account password not used as an ordinary Git HTTPS password?
2. What is a fine-grained token?
3. Why should permissions be minimal?
4. Why should tokens expire when practical?
5. Where should a token be stored?
6. What should you do if a token is committed?

### Break-It question

What is wrong with this idea?

```bash
git remote set-url origin https://USERNAME:TOKEN@github.com/OWNER/REPOSITORY.git
```

Do not execute it with a real token.

---

## Mission 12 — Remote identity investigation

Run:

```bash
git remote -v
git remote show origin
```

### Scenario

A teammate says:

> “GitHub is broken. My push is going to the wrong repository.”

Investigate without changing anything.

Determine:

- repository location;
- remote name;
- fetch URL;
- push URL;
- authentication method;
- whether the URL matches the intended repository.

Only after identifying the problem should you decide whether `git remote set-url` is appropriate.

---

## Mission 13 — Authentication versus authorization

### Scenario A

```text
ssh -T git@github.com
→ authentication succeeds

push
→ repository access denied
```

### Scenario B

```text
ssh -T git@github.com
→ Permission denied (publickey)
```

### Task

For each scenario, identify the first investigation layer.

Then explain why the same fix should not be applied to both.

---

## Mission 14 — Repository visibility investigation

Compare three situations:

1. public repository you do not own;
2. private repository you have been invited to;
3. private repository you have not been granted access to.

For each, explain:

- what you can discover;
- what you can clone;
- what you can push;
- what authentication/authorization questions arise.

Do not assume “private” automatically means “nobody else can collaborate.”

---

## Mission 15 — GitHub security reconnaissance

In your practice repository, identify which of these are available and where they are configured:

- two-factor authentication at account level;
- SSH keys;
- branch protection/rules;
- Actions settings;
- security features;
- secret scanning, where available;
- dependency/security alerts, where available.

For each, write one sentence describing the risk it helps address.

---

## Mission 16 — GitHub feature map

Create this map from memory, then verify it on GitHub:

```text
Repository
├── Code
├── Issues
├── Pull requests
├── Actions
├── Projects
├── Releases
└── Settings
```

For every item, answer:

- What problem does it solve?
- Is it a Git object or a GitHub feature?
- When would a professional team use it?

---

## Mission 17 — First complete GitHub connection

Starting from a small local repository:

1. configure Git identity;
2. ensure your commit email is appropriate;
3. create a GitHub repository;
4. choose its visibility intentionally;
5. connect the local repository to GitHub;
6. use SSH or HTTPS deliberately;
7. authenticate;
8. push a branch;
9. verify the repository on GitHub;
10. inspect the resulting commit and author.

Do not treat “push succeeded” as the final verification.

Prove that:

```text
local repository
      ↓
correct remote
      ↓
correct GitHub account
      ↓
correct repository
      ↓
correct commit identity
      ↓
expected GitHub result
```

---

## Break-It Exercise — Credential incident

Create a harmless fake token such as:

```text
FAKE_TOKEN_DO_NOT_USE_123456
```

Place it in a temporary file, then accidentally stage it.

Your task is to stop before committing it.

Then explain:

- why `.gitignore` is useful;
- why `.gitignore` would not undo a commit;
- what you would do if a real token had already been committed;
- why rotating/revoking the real token is more important than merely deleting the file.

---

## Troubleshooting Drill — Five failures

For each failure, write the first three pieces of evidence you would collect.

### Failure 1

```text
Permission denied (publickey)
```

### Failure 2

```text
Repository not found
```

### Failure 3

```text
remote: Permission to OWNER/REPO.git denied to USER
```

### Failure 4

A public commit exposes your personal email.

### Failure 5

A token was accidentally committed and pushed.

Your answers must identify **the failure layer**, not merely name a command.

---

## Independent Challenge — GitHub setup without a recipe

You receive a new Linux laptop and are told:

> “Set up Git so you can contribute to our GitHub repository. Protect your personal email and use SSH. Do not create unnecessary credentials.”

You are given no command list.

Produce your own implementation plan, then execute it on a safe test repository.

Your plan must include:

- account verification;
- email privacy;
- Git identity;
- existing-key investigation;
- SSH key setup;
- public-key registration;
- SSH authentication test;
- repository access test;
- remote verification;
- final proof.

---

## Mastery Check

You should be able to answer all of these without notes:

1. What is the difference between Git and GitHub?
2. What is the difference between authentication and authorization?
3. What is the difference between an SSH public key and private key?
4. Why can you upload a public key to GitHub but not a private key?
5. Why should you check for existing SSH keys first?
6. What does `ssh -T git@github.com` actually test?
7. Why can SSH authentication succeed while a push still fails?
8. What is a GitHub `noreply` email address used for?
9. What does Git store in a commit about identity?
10. Why does `.gitignore` not fix an already-exposed secret?
11. Why is a PAT treated like a secret?
12. What is `origin`?
13. What is the difference between a GitHub repository and a local clone?
14. What is an issue?
15. What is a pull request?
16. What is a release?
17. What is GitHub Actions?
18. Where would you look for authoritative answers when GitHub changes its interface?

If you can answer the questions but cannot perform the workflow, you have memorized concepts without mastering the workflow.

If you can perform the workflow but cannot explain why each step exists, you have memorized commands without mastering the system.

The goal is both.
