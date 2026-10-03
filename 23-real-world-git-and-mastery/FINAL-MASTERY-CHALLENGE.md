# Git Essentials — Final Mastery Challenge

## PaakowTronics Service Desk — Incident & Policy Investigation

This is the final practical assessment for **Git Essentials**.

You are not being assessed on whether you can recite Git commands. You are being assessed on whether you can enter an unfamiliar repository, understand its state, investigate its history, make sound Git decisions, recover from mistakes, and prove that the final result is correct.

There is intentionally no command-by-command recipe.

---

# Rules

You may use:

- the repository README;
- documentation inside the repository;
- Git's built-in help;
- official Git documentation;
- normal terminal documentation;
- your course notes.

You may ask the instructor to clarify a **business requirement** or an ambiguous task.

You may not ask:

> “What exact command should I type?”

The assessment is designed so that the repository state and documentation provide the evidence you need to choose the operation yourself.

---

# Official Assessment Repository

The official assessment is the **PaakowTronics Service Desk Final Mastery** repository:

**https://github.com/PaakowTronics/paakowtronics-service-desk-final-mastery**

The repository is prepared specifically for this assessment. Do not modify the prepared source repository directly. Follow its setup instructions and work in the assessment repository created for you.

Treat the repository's own documentation as part of the assessment.

---

# The business situation

You have joined the PaakowTronics Service Desk team as a junior engineer responsible for maintaining the team's documentation and Git history.

Management has identified a documentation problem in the ticket-priority policy.

The policy must communicate two important rules:

1. A **P2** may include a major internal team being blocked from an important function **or** a significant customer-facing service degradation where the service remains available.
2. Priority is determined by **business impact**, not by the identity or job title of the person who submitted the request.

There is already work in the repository related to customer-facing service operations. Some of that work may be useful. Some may not be appropriate to adopt. You must determine the difference from the evidence in the repository.

A separate portal hotfix also contains an incident ticket that management wants brought into the final work, but the other work on that hotfix line is not automatically required.

The repository therefore contains several different Git problems disguised as one normal piece of Service Desk work.

---

# Your assessment objective

By the end of the assessment, the repository should reflect the documented business requirements, contain the appropriate existing work, preserve a sensible history, and contain no accidental or unrelated changes.

You are responsible for deciding **how** to get there.

There may be more than one technically valid Git strategy. Your decisions must be explainable and the final state must satisfy the documented requirements.

---

# Mission 1 — Establish the starting state

Before changing anything, investigate the repository.

Determine:

- where you are;
- whether you are inside a Git repository;
- your current branch;
- working-tree state;
- recent history;
- local branches;
- remote-tracking branches;
- configured remotes; and
- any repository instructions that affect the assessment.

### Evidence

Record a short starting-state report. Do not rely on memory later.

You should be able to explain what you knew **before** making your first change.

---

# Mission 2 — Understand the Service Desk

Read the repository documentation before deciding what to change.

Determine:

- what the Service Desk repository represents;
- how the documentation is organized;
- which document defines ticket priority;
- what the customer-facing work is about;
- whether there are setup or verification instructions; and
- what the final business requirement means in terms of repository content.

Do not assume that a branch name tells you whether its work is correct or relevant.

---

# Mission 3 — Create your own policy change

Create an isolated line of work for the policy correction.

Implement the documented priority requirement on your branch.

Before committing, inspect:

- the working-tree state;
- the staged state if applicable; and
- the actual diff.

Create a meaningful commit that describes the change.

### What matters

Your commit should represent the business requirement clearly enough that another engineer could understand its purpose from the history.

---

# Mission 4 — Investigate the existing branches

The repository contains multiple lines of work.

Investigate their history and content.

Determine:

- which branch contains customer-facing work;
- which branch is unrelated maintenance;
- which branch contains knowledge-base work;
- which branch contains the portal hotfix;
- which commits introduced the relevant changes; and
- whether every change on a relevant branch actually belongs in the final result.

Do not merge or copy work merely because a branch sounds relevant.

### Required evidence

For the customer-facing branch, be able to explain the purpose of each significant commit you discovered and whether you believe its content satisfies the documented business requirement.

---

# Mission 5 — Integrate the correct work

Now bring the appropriate existing customer-facing work together with your policy change.

The repository is intentionally prepared so that integration can require judgment and may produce a conflict in the policy documentation.

If a conflict occurs, do not treat the conflict markers as the decision.

You must:

1. understand what your change means;
2. understand what the other change means;
3. compare both against the business requirement;
4. make an intentional resolution;
5. inspect the resulting file;
6. verify the integration; and
7. inspect the resulting history.

### Important

A successful merge is not automatically a correct solution.

The final content must satisfy the Service Desk policy, and the history must not silently introduce a policy that contradicts it.

---

# Mission 6 — Investigate the questionable change

During your branch investigation you should encounter an existing change involving requester identity or role and ticket priority.

Do not assume that an existing commit is correct simply because another developer created it.

Determine:

- what the commit changed;
- why the change appears questionable under the documented policy;
- whether the change is already part of the work you integrated; and
- what repository state is required to satisfy management's requirement.

Choose an appropriate Git/history operation to leave the repository in the required state.

### Evidence

Your final explanation must identify this change and explain what you decided to do about it.

The assessment is testing whether you can distinguish **useful history from history that should not be blindly adopted**.

---

# Mission 7 — Recover from an introduced mistake

The instructor will introduce a controlled mistake into your working repository.

The mistake may involve:

- an accidental local edit;
- an unnecessary staged change;
- an incorrect recent commit; or
- a commit that appears to have disappeared after a history operation.

The exact mistake is intentionally not specified in advance.

### Your task

Investigate before acting.

Use the evidence available from the repository state and history to determine:

- what happened;
- what should be preserved;
- what should be removed or restored; and
- which recovery approach is appropriate.

Do not begin with a destructive operation merely because it is familiar.

After recovery, verify both the files and the Git history.

### Recovery evidence

Record:

```text
What I observed:
What I believed had happened:
Evidence that supported that conclusion:
Recovery approach chosen:
Why I chose it:
What I verified afterward:
```

---

# Mission 8 — Bring in one specific hotfix item

Management needs the **portal incident ticket** from the portal hotfix line.

The other commits on that hotfix line are not automatically required.

Determine from the history which commit introduced the required incident ticket and bring that work into your current line without unnecessarily importing unrelated hotfix work.

The assessment does not tell you which Git operation to use.

Your job is to identify the smallest appropriate operation from the history and verify the result afterward.

### Evidence

Be able to identify:

- the source branch;
- the specific commit containing the requested work;
- what that commit changes; and
- how you brought the required work into your current history.

---

# Mission 9 — Understand the remote

Inspect the configured remote and remote-tracking information.

Determine:

- what the remote represents in this assessment;
- which local branch, if any, tracks a remote branch;
- whether your local view is current enough for the task; and
- what a push would mean from the final state.

Do not push destructive changes merely to demonstrate that you can push.

The objective is to understand the relationship between local history and the remote, not to perform an unnecessary publication.

---

# Mission 10 — Final verification

Before declaring the assessment complete, prove that the repository is correct.

Verify at minimum:

- the intended branch is checked out;
- the working tree is clean or any remaining changes are intentional and documented;
- the policy requirement is correctly represented;
- the questionable requester-role policy has not been silently adopted as valid policy;
- the appropriate customer-facing work is present;
- the required portal incident ticket is present;
- unrelated hotfix work was not unnecessarily imported;
- the recovery was successful;
- expected commits are present;
- no accidental files were committed;
- the history makes sense; and
- the local/remote relationship is understood.

A command returning successfully is not sufficient evidence.

---

# Final explanation

Submit a short written explanation in plain language.

Answer:

1. What repository state did you start with?
2. What business requirement were you asked to implement?
3. What change did you make yourself, and why?
4. Which existing branches did you investigate?
5. Which existing work did you decide was relevant, and why?
6. Where did the policy conflict or overlap occur?
7. How did you resolve the integration, and why?
8. What questionable change did you discover?
9. What did you do about that questionable change, and why?
10. What mistake did the instructor introduce?
11. How did you determine what had happened?
12. How did you recover?
13. Which specific hotfix commit contained the requested portal incident ticket?
14. How did you bring that work into your current history without unnecessarily bringing unrelated work?
15. What evidence proves the final repository is correct?
16. What would you do differently if you repeated the assessment?

---

# Evidence standard

A strong submission contains evidence, not just claims.

Examples of useful evidence include:

- repository status;
- branch and remote-tracking information;
- relevant commit history;
- diffs;
- the final contents of affected documents;
- conflict-resolution results;
- recovery history;
- the specific hotfix commit and its changed files; and
- a final clean-state check.

You do not need to submit every command you ran. Submit enough evidence to make your reasoning and final state independently understandable.

---

# Mastery standard

You demonstrate mastery when you can complete the assessment without command-by-command instruction and can explain **why** your Git operations were appropriate.

The key question is not:

> “Did you remember every command?”

The key question is:

> **“Could you investigate the repository, solve the problem, recover when something went wrong, and prove that you solved it correctly?”**

---

# Instructor observation sheet

| Skill | Observed independently? | Notes |
|---|---|---|
| Repository orientation | | |
| Documentation use | | |
| State inspection | | |
| Business requirement → Git task | | |
| Branching | | |
| Committing | | |
| History investigation | | |
| Relevance judgment | | |
| Integration | | |
| Conflict resolution | | |
| Detecting questionable history | | |
| Recovery | | |
| Specific-commit selection | | |
| Remote awareness | | |
| Verification | | |
| Explanation | | |

---

# Final reflection

Complete these sentences:

> Before this course, I thought Git was...

> Now I understand Git as...

> When I get stuck, my first step is...

> The Git skill I am most confident using independently is...

> The Git situation I still need more practice with is...
