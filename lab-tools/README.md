# Lab Tools

The expanded course is designed to grow a library of disposable labs.

## Lab design rule

Each lab should be:

- reproducible
- disposable
- resettable
- independent
- verifiable
- safe to break

## Verification philosophy

Bad checker:

> Did the learner type `git add .`?

Good checker:

> Are the required files staged?

Bad checker:

> Did the learner use `git reset HEAD~1`?

Good checker:

> Is the repository in the required final state, and can the learner explain why?

## Future tooling

Recommended future scripts:

- `create-lab.sh`
- `reset-lab.sh`
- `check-state.sh`
- `check-commits.sh`
- `check-branches.sh`
- `check-remotes.sh`
- `check-tags.sh`

The scripts should produce friendly output such as:

```text
PASS: feature/login exists
PASS: 2 feature commits found
PASS: main remains unchanged
FAIL: expected file is missing
       Hint: inspect the assignment requirements.
```
