# 03 — What Is Git? Practice Drills

## Welcome to the Investigation Lab

Lesson 03 was mostly about understanding.

Now it is time to test whether you actually understand the ideas.

This is not a command-memorization test.

You will be asked to:

- predict
- reason
- compare
- investigate
- explain
- make decisions
- spot misunderstandings

The rule from Lesson 01 still applies:

> **Predict → Run → Verify**

But there is another rule for this lesson:

> **Explain it in your own words.**

If you cannot explain an idea simply, you probably need to investigate it again.

---

# Mission 1 — Explain Git Without Using the Word "Git"

This sounds strange.

Imagine someone asks:

> "What is Git?"

You are not allowed to answer:

> "Git is Git."

You also cannot simply copy a textbook definition.

Explain it to someone who has never used it.

Write your answer:

```text
________________________________________________
________________________________________________
________________________________________________
________________________________________________
```

### Challenge

Try to explain Git using **one sentence**.

```text
________________________________________________
```

---

# Mission 2 — The Version Chaos Problem

Imagine you find this on someone's computer:

```text
website/
website-final/
website-final2/
website-final-new/
website-final-new2/
website-final-use-this/
website-final-use-this-2/
website-final-real/
website-final-real-latest/
```

### Question

What problem are they trying to solve?

```text
________________________________________________
________________________________________________
```

### Question

Why might this become difficult?

```text
________________________________________________
________________________________________________
```

### Question

What kind of tool could help them manage versions more systematically?

```text
________________________________________________
```

---

# Mission 3 — The Timeline

Imagine a project has these recorded points:

```text
A → B → C → D
```

Where:

```text
A = project created
B = login added
C = password validation added
D = password reset added
```

Answer:

### What happened between A and B?

```text
________________________________________________
```

### What happened between B and C?

```text
________________________________________________
```

### Which point represents the project after password reset was added?

```text
________________________________________________
```

### What do we call these recorded points in Git?

```text
________________________________________________
```

---

# Mission 4 — What Is a Commit?

Complete the sentence:

> A Git commit is __________________________________

Now explain it without using the word "save."

```text
________________________________________________
________________________________________________
```

### Challenge

Why is this distinction useful?

```text
________________________________________________
________________________________________________
```

---

# Mission 5 — Save vs Commit

Imagine you open:

```text
app.js
```

You change:

```javascript
console.log("Hello");
```

to:

```javascript
console.log("Hello World");
```

Then you press Save in your editor.

### Has the file been saved?

```text
Yes / No
```

### Has Git necessarily recorded a new commit?

```text
Yes / No
```

### Why?

```text
________________________________________________
________________________________________________
```

This is one of the most important ideas in this lesson.

---

# Mission 6 — The Broken Login

Imagine:

Monday:

```text
Login works.
```

Tuesday:

```text
Password reset added.
```

Wednesday:

```text
Email verification added.
```

Thursday:

```text
Login is broken.
```

Someone says:

> "Let's just start changing random files until we find the problem."

Would Git's history potentially give you useful information?

```text
Yes / No
```

Explain:

```text
________________________________________________
________________________________________________
```

---

# Mission 7 — Detective Mode

You are investigating a bug.

Someone tells you:

> "The application worked yesterday."

What questions could Git history eventually help you investigate?

Select all that apply:

```text
[ ] What changes were recorded recently?

[ ] Which files changed?

[ ] When were changes recorded?

[ ] What did the project look like at an earlier point?

[ ] What does the developer's lunch taste like?

[ ] What commits exist in the history?
```

Write two additional questions Git history could help you investigate:

```text
1. _____________________________________________

2. _____________________________________________
```

---

# Mission 8 — Repository or Ordinary Folder?

You see:

```text
project/
├── index.html
├── app.js
└── styles.css
```

Nothing else is shown.

### Question

Can you automatically conclude that this is a Git repository?

```text
Yes / No
```

### Why?

```text
________________________________________________
________________________________________________
```

---

# Mission 9 — Spot the Git Repository

Consider these two structures.

### Folder A

```text
project-a/
├── index.html
├── app.js
└── styles.css
```

### Folder B

```text
project-b/
├── index.html
├── app.js
├── styles.css
└── .git/
```

### Which one shows evidence that Git has been initialized there?

```text
A / B
```

### What is `.git`?

```text
________________________________________________
```

### Should you normally edit files inside `.git` manually?

```text
Yes / No
```

---

# Mission 10 — Git or GitHub?

Classify each statement.

Write **Git** or **GitHub**.

### 1.

> Software that manages version history on your computer.

```text
________________
```

### 2.

> An online service that can host Git repositories.

```text
________________
```

### 3.

> Can be used without an internet connection for local version control.

```text
________________
```

### 4.

> Can provide online collaboration features such as pull requests.

```text
________________
```

### 5.

> The thing you installed in Lesson 02.

```text
________________
```

---

# Mission 11 — Can You Use Git Without GitHub?

Imagine you have no internet connection.

You create a project on your computer.

Can you still use Git to record the project's history locally?

```text
Yes / No
```

Explain:

```text
________________________________________________
________________________________________________
```

---

# Mission 12 — The Branch Problem

Imagine:

```text
main
  │
  A
  │
  B
  │
  C
```

The project is working.

You want to experiment with a new design without immediately changing the main line.

What Git concept could help?

```text
________________________________________________
```

### Why?

```text
________________________________________________
________________________________________________
```

---

# Mission 13 — Branches Are Not Copies

A beginner might say:

> "A branch is just another folder."

Is that a good description?

```text
Yes / No
```

Explain what a branch represents more accurately:

```text
________________________________________________
________________________________________________
```

---

# Mission 14 — Draw the Branch

Start with:

```text
A → B → C
```

Now imagine that after C, you create a separate line of development.

Draw a simple diagram showing:

- the original line
- the new line

Use letters for commits.

Example:

```text
       ?
      /
A → B → C
```

Complete your diagram:

```text
________________________________________________
________________________________________________
________________________________________________
```

---

# Mission 15 — The Project Historian

Imagine Git is a historian standing beside your project.

Your project changes:

```text
Version 1
     ↓
Version 2
     ↓
Version 3
```

### What does Git help preserve?

```text
________________________________________________
________________________________________________
```

### Who decides what a meaningful commit represents?

```text
________________________________________________
```

### Does Git automatically understand why you made a change?

```text
Yes / No
```

Explain:

```text
________________________________________________
```

---

# Mission 16 — Good Commit Message or Bad?

Classify these commit messages as:

- **Useful**
- **Unclear**

### 1.

```text
update
```

```text
________________
```

### 2.

```text
Fix password validation
```

```text
________________
```

### 3.

```text
stuff
```

```text
________________
```

### 4.

```text
Add staff registration form
```

```text
________________
```

### 5.

```text
final final final
```

```text
________________
```

### Challenge

Choose one unclear message and rewrite it.

```text
Original:
____________________________

Better:
____________________________
```

---

# Mission 17 — What Would You Want Git to Tell You?

Imagine this situation:

> "The application worked last week. Now it doesn't."

Write five questions you would want to investigate.

```text
1. _____________________________________________

2. _____________________________________________

3. _____________________________________________

4. _____________________________________________

5. _____________________________________________
```

Compare your answers with these examples:

- What changed?
- When did it change?
- Which files changed?
- Which commits were created?
- What did the project look like before the problem appeared?

Your answers do not need to be identical.

---

# Mission 18 — The Git Mental Model

Complete the diagram.

```text
YOUR PROJECT
     │
     │ changes
     ▼
   ______
     │
     │ meaningful recorded point
     ▼
   ______
     │
     ▼
 PROJECT HISTORY
```

Answers:

```text
________________
________________
```

---

# Mission 19 — What Git Does NOT Do

Which of these are things Git does **not automatically** do?

```text
[ ] Write your application for you.

[ ] Track project history.

[ ] Decide whether your code is good.

[ ] Automatically fix every bug.

[ ] Record commits.

[ ] Decide what your business requirements should be.

[ ] Help you investigate changes.
```

Write one thing you think a beginner might incorrectly expect Git to do:

```text
________________________________________________
```

---

# Mission 20 — The Five-Year-From-Now Test

Imagine you make a project today.

Five years later, you return to it.

You see this history:

```text
update
fix
changes
more changes
final
final2
```

Would this history help you understand how the project developed?

```text
Yes / No
```

Why?

```text
________________________________________________
________________________________________________
```

Now imagine:

```text
Create staff registration workflow
Add HOD approval process
Fix duplicate staff registration
Add email verification
Improve password recovery security
```

Which history would be easier to investigate?

```text
________________________________________________
```

Why?

```text
________________________________________________
```

---

# Mission 21 — Predict Before Git

You have an ordinary project folder:

```text
my-project/
├── index.html
└── app.js
```

Git is not currently managing it.

You are told:

> "Turn this folder into a Git repository."

You haven't learned the command yet.

### What do you expect to happen?

Write your prediction.

```text
________________________________________________
________________________________________________
________________________________________________
```

### What should NOT happen?

```text
________________________________________________
________________________________________________
```

Do not run the command yet.

This is a prediction exercise.

Lesson 04 will test your prediction.

---

# Mission 22 — The `.git` Mystery

Imagine you run a command and suddenly notice:

```text
.git
```

appearing inside your project.

### What do you think it means?

```text
________________________________________________
________________________________________________
```

### Does it mean your project files were moved somewhere else?

```text
Yes / No
```

### Does it mean Git is now managing the repository?

```text
Yes / No
```

Explain:

```text
________________________________________________
```

---

# Mission 23 — Git Is a Tool, Not a Decision Maker

Imagine Git shows you that five files changed.

Can Git automatically know whether all five changes should be included in your next commit?

```text
Yes / No
```

Who makes that decision?

```text
________________________________________________
```

Why does this matter?

```text
________________________________________________
________________________________________________
```

---

# Mission 24 — The Real-World Scenario

You are working on a project.

You have made three unrelated changes:

```text
1. Fixed a login bug.
2. Changed the website logo.
3. Added a new report.
```

Should you automatically throw all three into one commit just because they happened at the same time?

```text
Yes / No / It depends
```

Explain your reasoning:

```text
________________________________________________
________________________________________________
```

The important idea is that commits should normally represent meaningful pieces of work.

---

# Mission 25 — Explain Git to Three People

Explain Git differently to each person.

## Person A — A child

Use very simple language.

```text
________________________________________________
________________________________________________
```

## Person B — Someone who uses computers but has never programmed

```text
________________________________________________
________________________________________________
```

## Person C — A beginner developer

```text
________________________________________________
________________________________________________
```

The goal is to see whether you actually understand the idea rather than memorizing one definition.

---

# Mission 26 — The Git Myth Buster

For each statement, write:

**True**, **False**, or **Needs qualification**.

### 1.

> Git and GitHub are the same thing.

```text
________________
```

### 2.

> Git is only useful for teams.

```text
________________
```

### 3.

> A Git commit is exactly the same as saving a file.

```text
________________
```

### 4.

> Git can help you investigate what changed in a project.

```text
________________
```

### 5.

> Every Git repository must be hosted on GitHub.

```text
________________
```

### 6.

> A branch is a separate line of development.

```text
________________
```

### 7.

> Git automatically knows why a developer changed a file.

```text
________________
```

---

# Mission 27 — The Five-Question Git Check

Before using a Git command, train yourself to ask:

### 1. What am I trying to accomplish?

```text
________________________________________________
```

### 2. What is the current state?

```text
________________________________________________
```

### 3. What do I expect the command to do?

```text
________________________________________________
```

### 4. What could go wrong?

```text
________________________________________________
```

### 5. How will I verify the result?

```text
________________________________________________
```

This method will become one of your most important Git habits.

---

# Mission 28 — The Mystery Project

You receive this project:

```text
company-portal/
├── frontend/
├── backend/
├── docs/
├── tests/
└── README.md
```

Someone tells you:

> "We accidentally broke something yesterday."

You are not allowed to start changing files randomly.

What would you want to investigate first?

Write a plan:

```text
1. _____________________________________________

2. _____________________________________________

3. _____________________________________________

4. _____________________________________________

5. _____________________________________________
```

Think about:

- project state
- history
- recent changes
- commits
- files
- branches

You don't need to know the exact commands yet.

---

# Boss Challenge — The Git Explanation Challenge

Imagine you are teaching Lesson 03 to a new learner.

They ask:

> "Why did I install Git?"

You have **two minutes** to explain.

Your explanation must include:

- the problem of tracking project changes
- version control
- repositories
- commits
- history
- branches
- Git vs GitHub

Write your explanation:

```text
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
________________________________________________
```

### Extra challenge

Explain it without using these words:

```text
repository
commit
branch
GitHub
```

If you can still explain the basic idea, you probably understand it.

---

# Final Challenge — Predict Lesson 04

Lesson 04 will be practical.

You will have an ordinary folder and Git installed.

You will turn that folder into your first Git repository.

Before beginning Lesson 04, answer:

### What do you expect Git to add to the project?

```text
________________________________________________
```

### What do you expect to happen to your existing project files?

```text
________________________________________________
```

### What evidence would prove that the folder is now a Git repository?

```text
________________________________________________
```

### What would you NOT expect Git to do?

```text
________________________________________________
```

---

# Reflection

Answer honestly.

### 1. Before this lesson, what did you think Git was?

```text
________________________________________________
________________________________________________
```

### 2. What do you understand now that you did not understand before?

```text
________________________________________________
________________________________________________
```

### 3. What is still confusing?

```text
________________________________________________
________________________________________________
```

### 4. Which idea was most interesting?

```text
________________________________________________
```

### 5. Which idea was hardest?

```text
________________________________________________
```

---

# Mastery Check

Do not move forward simply because you finished the pages.

Check yourself.

- [ ] I can explain Git in my own words.
- [ ] I understand what version control means.
- [ ] I understand why project history is useful.
- [ ] I understand what a repository is.
- [ ] I understand what a commit represents.
- [ ] I understand why a commit is not simply the same thing as saving a file.
- [ ] I understand what `.git` represents.
- [ ] I know the difference between Git and GitHub.
- [ ] I understand that Git can work without GitHub.
- [ ] I understand the basic purpose of branches.
- [ ] I understand that Git does not make decisions for me.
- [ ] I can think of questions Git history could help me investigate.
- [ ] I can predict what should happen before running a Git command.
- [ ] I know that I should verify the result after running it.

## The Real Mastery Question

Forget the definitions for a moment.

Ask yourself:

> **"If someone asked me why Git exists, could I explain the problem it solves without reading my notes?"**

If yes, you are ready for Lesson 04.

If not, go back to the parts that are unclear.

You are not supposed to memorize Git.

You are supposed to **understand it**.
