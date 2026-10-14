# 12 — GitHub: Accounts, Repositories, Identity & Authentication

## Mission

Move from **local Git** to **professional GitHub use**.

This lesson is not just about connecting a remote. You will learn what GitHub is, how a GitHub account is configured, how GitHub identifies you, how Git authenticates to GitHub, how repository visibility and permissions work, and how to diagnose authentication problems without guessing.

By the end of this lesson, GitHub should feel like a system you understand rather than a website you happen to push code to.

---

## Learning outcomes

You should be able to:

- explain Git, GitHub, a Git repository, and a GitHub repository without mixing them up;
- navigate the important parts of a GitHub repository;
- create and configure a repository intentionally;
- distinguish public, private, and organizational access at a practical level;
- understand your GitHub account identity, verified email, commit email, and `noreply` email;
- configure Git commit identity deliberately;
- explain why email privacy matters for public repositories;
- explain authentication versus authorization;
- explain HTTPS and SSH as Git transport/authentication approaches;
- inspect existing SSH keys before creating new ones;
- create an Ed25519 SSH key when needed;
- understand private-key versus public-key responsibilities;
- add an SSH authentication key to GitHub;
- use `ssh-agent` appropriately;
- test an SSH connection to GitHub;
- diagnose common `Permission denied (publickey)` problems;
- understand the role of personal access tokens when using HTTPS;
- understand why GitHub passwords are not used as ordinary Git HTTPS passwords;
- understand the difference between repository access and authentication;
- inspect and change a repository's remote URL safely;
- understand the purpose of README files, `.gitignore`, and licenses;
- identify the important GitHub repository areas: Code, Issues, Pull requests, Actions, Projects, Releases, and Settings;
- understand the difference between a GitHub repository and a local clone;
- explain why an SSH private key, PAT, password, or secret must never be committed;
- use official GitHub documentation when authentication or account behavior differs from the lesson;
- prove that Git and GitHub are correctly connected instead of assuming that they are.

---

# Part 1 — Git and GitHub are different systems

## Git

Git is the distributed version-control system running on your computer.

Git can:

- create commits;
- record file history;
- create branches;
- compare versions;
- merge histories;
- recover work;
- rewrite local history;
- communicate with remote Git repositories.

Git does not require GitHub.

You can use Git entirely offline.

## GitHub

GitHub is a hosted development and collaboration platform built around Git repositories.

A GitHub repository can provide:

- hosted Git history;
- access control;
- pull requests;
- code review;
- issues;
- project management;
- Actions and automation;
- releases;
- repository settings;
- security controls;
- collaboration between people and teams.

### The important boundary

```text
Git
│
├── local repository
├── commits
├── branches
├── tags
├── merges
└── history

GitHub
│
├── hosted repository
├── identity
├── permissions
├── pull requests
├── issues
├── Actions
├── Projects
├── Releases
└── collaboration/security features
```

Git is the version-control engine.

GitHub is one platform that hosts Git repositories and adds collaboration and management capabilities.

---

# Part 2 — A GitHub repository is more than a place to store files

When you open a GitHub repository, learn to recognize the major areas instead of treating the page as one large screen.

Depending on repository configuration and your permissions, you may encounter:

### Code

The repository files, branches, commits, tags, and other source-control views.

### Issues

A place to record and discuss work, bugs, questions, and tasks.

An issue is not a Git commit.

### Pull requests

A proposed change from one branch into another, accompanied by discussion, review, checks, and a merge decision.

Pull requests are taught deeply in Lesson 16.

### Actions

GitHub's automation system. Workflows can run tests, checks, builds, releases, and other automation in response to repository events.

You do not need to become an Actions expert in this lesson. You need to understand what it is and how to recognize a failed workflow.

### Projects

GitHub's project-management capability for organizing work across issues and pull requests.

### Releases

A GitHub presentation/distribution layer around important versions. Releases commonly point at Git tags and can include release notes and downloadable assets.

Tags and releases are explored further in Lesson 23.

### Settings

Repository configuration such as access, branches/rules, Actions, security, webhooks/integrations, and other administrative controls. What you can see or change depends on your permissions.

### Do not confuse these objects

```text
Commit       = a Git history object
Branch       = a movable Git reference
Tag          = a Git reference commonly used to mark a version
Issue        = a GitHub work/discussion record
Pull request = a GitHub collaboration/review proposal
Release      = a GitHub version/distribution presentation
```

That distinction becomes extremely important later.

---

# Part 3 — Creating a GitHub repository intentionally

When creating a repository, make deliberate choices.

Typical decisions include:

- repository name;
- description;
- public or private visibility;
- whether GitHub should create a README;
- whether GitHub should add a `.gitignore` template;
- whether to add a license;
- organization versus personal ownership.

## README

A README should help another person understand the project.

At minimum, a useful project README often answers:

1. What is this?
2. Why does it exist?
3. How do I install or run it?
4. How do I use it?
5. How do I contribute?
6. Where can I find additional documentation?

## `.gitignore`

`.gitignore` tells Git which untracked files should normally be ignored.

It is not a security boundary.

If a secret has already been committed, adding it to `.gitignore` does **not** remove it from history or make the secret safe.

## License

A license communicates what others are legally permitted to do with the project.

Do not invent a license choice casually. Read the project requirements and the license text.

---

# Part 4 — GitHub identity: account email and Git commit email

This section is essential because GitHub associates command-line commits with accounts using commit email addresses.

## Your GitHub account email

GitHub can have one or more email addresses associated with your account. Verification matters for account capabilities and notifications.

## Your Git commit email

Git itself records author and committer identity in commits.

Inspect your current configuration:

```bash
git config --global user.name
git config --global user.email
git config --local user.name
git config --local user.email
```

The local repository configuration can override the global configuration.

That means you must understand which configuration scope is active before changing anything.

## GitHub `noreply` email

GitHub provides a `noreply` address that can be used as the commit email when you want to keep your personal email private.

The important relationship is:

```text
Git commit
   │
   └── author email
           │
           ▼
       GitHub
           │
           ├── matches a verified account email
           │
           └── or uses the appropriate GitHub noreply address
```

Use the email shown in your GitHub account's email settings rather than copying a random example from the internet.

## Why this matters

If you publish commits containing a personal email address, that address may become visible in public repository history.

Before pushing to a public repository, ask:

> What email address will my next commit expose?

## Privacy and attribution are related but different

You want both:

- privacy where appropriate;
- correct attribution to your GitHub account.

Do not replace your commit email with an arbitrary fake address merely to hide your email. Use an address GitHub associates with your account, including its provided `noreply` address where appropriate.

## Exercise

Configure a test repository so that you can explain:

- which `user.name` is active;
- which `user.email` is active;
- whether that email is intended for public commits;
- how the repository's local configuration differs from your global configuration, if it does.

Do not change a work repository's identity without understanding the effect first.

---

# Part 5 — Authentication versus authorization

These words are easy to confuse.

## Authentication

Authentication answers:

> Who are you?

Examples:

- proving possession of an SSH private key corresponding to a public key registered with GitHub;
- authenticating a GitHub CLI session;
- presenting an appropriate token over HTTPS.

## Authorization

Authorization answers:

> What are you allowed to do?

A successful authentication does not automatically mean you can push to every repository.

For example:

```text
SSH key recognized
       ↓
Authentication succeeds
       ↓
But repository is private and you lack access
       ↓
Authorization fails
```

This distinction is one of the most useful debugging tools in GitHub work.

---

# Part 6 — HTTPS versus SSH

Git can communicate with GitHub using different URL schemes.

Common examples:

```text
HTTPS
https://github.com/OWNER/REPOSITORY.git

SSH
git@github.com:OWNER/REPOSITORY.git
```

These are not merely cosmetic differences. They use different authentication workflows.

## HTTPS

HTTPS is a web-based transport.

For Git operations requiring authentication, GitHub does not accept your ordinary GitHub account password as the Git credential. A personal access token or another supported credential mechanism is used instead.

For modern GitHub usage, understand the concept of:

- fine-grained personal access tokens;
- permissions/scopes;
- expiration;
- storage by a credential manager;
- token revocation.

Never paste a token into a repository file or commit it.

## SSH

SSH authenticates using cryptographic keys.

The typical relationship is:

```text
Your computer
│
├── private key  ← keep secret
│
└── public key   → register with GitHub

GitHub
│
└── knows your public key
```

The private key stays on your computer.

The public key can be uploaded to GitHub.

### Never do this

```text
git add ~/.ssh/id_ed25519
```

Never put a private SSH key into a repository.

Never send the private key to another person.

---

# Part 7 — SSH keys: the complete practical workflow

GitHub's SSH documentation recommends checking for existing keys before generating another one. Do that first.

## Step 1 — Check for existing keys

Linux/macOS:

```bash
ls -la ~/.ssh
```

Look for keys such as:

```text
id_ed25519
id_ed25519.pub
```

The `.pub` file is the public key.

The file without `.pub` is the private key.

Do not open or paste your private key into chat, an issue, a pull request, or a repository.

## Step 2 — Generate a key only if necessary

A common modern choice is Ed25519:

```bash
ssh-keygen -t ed25519 -C "your-github-email@example.com"
```

Choose a secure passphrase.

If you already have a key you use for another service, do not blindly overwrite it. Use a separate filename when appropriate.

## Step 3 — Understand the SSH agent

The SSH agent can hold keys in memory so that a passphrase-protected key does not need to be manually entered for every operation.

Typical Linux workflow:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

The exact agent setup can differ by operating system and desktop environment. Use the official GitHub/OpenSSH documentation when configuring persistent agent behavior.

## Step 4 — Add the public key to GitHub

Print the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copy the **entire public-key line**.

On GitHub:

```text
Profile picture
→ Settings
→ SSH and GPG keys
→ New SSH key
→ Authentication key
```

Give it a meaningful title such as:

```text
Inspiron-15-3520
```

Then paste the public key.

## Step 5 — Test SSH authentication

```bash
ssh -T git@github.com
```

A successful authentication should identify your GitHub account.

The exact wording of GitHub's response can change, so focus on whether authentication succeeded rather than memorising one sentence.

## Step 6 — Verify the repository remote

```bash
git remote -v
```

For SSH, you should see a remote resembling:

```text
git@github.com:OWNER/REPOSITORY.git
```

## Step 7 — Test the actual Git operation

Authentication to `github.com` and authorization to a particular repository are separate checks.

After SSH authentication succeeds, test the repository operation you actually need, such as fetching or pushing a branch for which you have permission.

---

# Part 8 — Diagnosing `Permission denied (publickey)`

Do not immediately generate another key.

Investigate in layers.

## Layer 1 — Does a key exist?

```bash
ls -la ~/.ssh
```

## Layer 2 — Is the key loaded when needed?

```bash
ssh-add -l
```

If the agent has no identities, decide whether the key needs to be added.

## Layer 3 — Is the public key registered with the correct GitHub account?

Check:

```text
GitHub → Settings → SSH and GPG keys
```

## Layer 4 — Does SSH authenticate to GitHub?

```bash
ssh -T git@github.com
```

## Layer 5 — Is the repository remote correct?

```bash
git remote -v
```

## Layer 6 — Do you have authorization to the repository?

Authentication may succeed while repository access still fails.

## Layer 7 — Is SSH selecting the expected key?

For deeper diagnosis:

```bash
ssh -vT git@github.com
```

Read the output carefully. Do not copy the entire diagnostic output into a public issue because it can reveal local details.

### The debugging model

```text
Git push fails
     ↓
Is this a local Git problem?
     ↓
Is the remote URL correct?
     ↓
Can SSH authenticate?
     ↓
Is the key registered to the right account?
     ↓
Does that account have repository access?
     ↓
Is the branch allowed to be pushed?
```

This is much stronger than repeatedly generating keys until something works.

---

# Part 9 — HTTPS authentication and personal access tokens

A personal access token is a credential, not a replacement for your GitHub username.

Understand these properties:

- a token should have only the permissions needed;
- fine-grained tokens can be limited to selected repositories and permissions;
- tokens may have expiration dates;
- tokens can be revoked;
- tokens must be protected like passwords;
- credential managers are preferable to storing tokens in shell history or files;
- a token accidentally committed to a repository should be treated as compromised.

### Never do this

```bash
git remote set-url origin https://USERNAME:TOKEN@github.com/OWNER/REPOSITORY.git
```

That can expose credentials through shell history, configuration, logs, process output, or other tooling.

If a credential is accidentally exposed:

1. stop using it;
2. revoke it;
3. determine where it was exposed;
4. remove it from future history/files as appropriate;
5. issue a replacement with the minimum required permissions.

---

# Part 10 — Remote names and URLs

A remote is a named reference to another repository.

Inspect remotes:

```bash
git remote -v
```

Inspect one remote in more detail:

```bash
git remote show origin
```

`origin` is a conventional name. It is not a special GitHub keyword.

You can have:

```text
origin
upstream
company
backup
```

The name matters because commands use it as a local label.

## Add a remote

```bash
git remote add origin git@github.com:OWNER/REPOSITORY.git
```

Then verify:

```bash
git remote -v
```

## Change a remote

```bash
git remote set-url origin git@github.com:OWNER/REPOSITORY.git
```

Do not change a remote merely because a command fails. First determine whether the URL is actually wrong.

---

# Part 11 — Public, private, and access control

A repository's visibility affects who can discover or access it, but visibility is only one part of the security model.

Think in layers:

```text
Account identity
      ↓
Repository visibility
      ↓
Repository/organization membership
      ↓
Role/permissions
      ↓
Branch/ruleset restrictions
      ↓
Specific operation
```

Examples of different problems:

- You cannot see a private repository → likely access/visibility.
- You can see a repository but cannot push → likely authorization or branch rules.
- You can authenticate by SSH but cannot access a private repository → authentication succeeded; authorization did not.

Never assume that because `ssh -T git@github.com` works, every GitHub repository operation will work.

---

# Part 12 — Security habits you must develop

## Never commit secrets

Examples:

- passwords;
- API tokens;
- private SSH keys;
- cloud credentials;
- database passwords;
- `.env` files containing real secrets;
- certificates/private keys where they are sensitive.

## `.gitignore` is not secret management

This is safe:

```gitignore
.env
.env.*
```

But if `.env` was already committed, adding it to `.gitignore` does not erase the previous commit.

You must treat exposed secrets as compromised and rotate them.

## Do not paste secrets into troubleshooting

When asking for help, redact:

```text
TOKEN=ghp_****************
PRIVATE_KEY=-----BEGIN...REDACTED-----
```

Never send the actual credential.

---

# Part 13 — GitHub security features you should recognize

You do not need to master every security control yet, but you should know why these exist:

### Two-factor authentication

Adds another authentication factor to protect the account.

### SSH/GPG keys

SSH keys can authenticate Git operations; signing keys can be used for commit/tag signature verification. Authentication and signing are related cryptographically but serve different purposes.

### Secret scanning

Helps detect exposed credentials/secrets in supported repositories and workflows.

### Dependabot

Helps identify and update vulnerable dependencies in supported ecosystems.

### Branch protection/rules

Can require pull requests, reviews, passing checks, or other conditions before changes reach protected branches.

These controls become especially important in Lesson 16 when collaboration is introduced.

---

# Part 14 — Official documentation as part of the skill

GitHub changes its interface and security systems over time.

Do not memorize a screenshot.

Use official documentation for current account and authentication details.

Recommended documentation:

- GitHub authentication documentation: https://docs.github.com/en/authentication
- Checking for existing SSH keys: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys
- Generating an SSH key: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
- Adding an SSH key: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
- GitHub email addresses: https://docs.github.com/en/account-and-profile/reference/email-addresses-reference
- Personal access tokens: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens

The goal is not to memorize these URLs. The goal is to know **where authoritative answers come from**.

---

# Part 15 — Command reference

## Inspect identity

```bash
git config --global user.name
git config --global user.email
git config --local user.name
git config --local user.email
git config --list --show-origin
```

## Inspect remotes

```bash
git remote -v
git remote show origin
```

## Add/change a remote

```bash
git remote add origin <URL>
git remote set-url origin <URL>
```

## Inspect SSH keys

```bash
ls -la ~/.ssh
ssh-add -l
```

## Generate Ed25519 key

```bash
ssh-keygen -t ed25519 -C "your-github-email@example.com"
```

## Start agent and add key on a typical Linux shell

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

## Display public key

```bash
cat ~/.ssh/id_ed25519.pub
```

## Test GitHub SSH authentication

```bash
ssh -T git@github.com
```

## Verbose SSH diagnosis

```bash
ssh -vT git@github.com
```

Use verbose output as a diagnostic tool, not as something to memorize.

---

# Part 16 — Troubleshooting table

| Symptom | First question | Useful evidence |
|---|---|---|
| `Permission denied (publickey)` | Can SSH authenticate? | `ssh -T git@github.com` |
| `Repository not found` | Is the remote correct and does the account have access? | `git remote -v`, GitHub repository URL |
| Push rejected | Is remote history ahead or is a rule blocking the push? | `git fetch`, `git status`, GitHub message |
| Commit appears under wrong identity | Which commit email was used? | `git log --format=fuller`, Git config |
| Personal email exposed | What email is configured for commits? | `git config`, GitHub email settings |
| Token exposed | Is the credential still valid? | Token settings/revocation |
| Key exists but SSH fails | Is the correct key loaded/registered? | `ssh-add -l`, GitHub SSH settings |
| SSH works but push fails | Is this authorization or branch policy? | Repository permissions/rules |

---

# Mastery standard

You are ready to move on when you can explain and perform the following without blindly copying a tutorial:

- create a GitHub repository;
- choose appropriate visibility;
- configure a safe commit email;
- explain why a GitHub `noreply` address can be useful;
- inspect Git identity configuration;
- explain authentication versus authorization;
- configure SSH from an existing key or generate one when necessary;
- add the public key to GitHub;
- test SSH authentication;
- diagnose `Permission denied (publickey)` methodically;
- explain HTTPS authentication and personal access tokens;
- inspect and correct a remote URL;
- explain what the major GitHub repository tabs/features are for;
- explain why `.gitignore` does not remove an already-committed secret;
- identify where to find authoritative GitHub documentation.

The next lesson focuses on **push itself**. This lesson should have already answered the question:

> “How does my local Git identity and authentication reach GitHub safely?”
