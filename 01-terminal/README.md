# 01 — Your Terminal

## Outcomes

- Identify the current working directory.
- List files, including hidden files when appropriate.
- Move through absolute and relative paths.
- Create directories and files.
- Recognize that terminal commands operate relative to the current location.

## Mental model

The shell always has a current working directory. Relative paths are interpreted from that location. `pwd` answers where you are; `ls` answers what is here; `cd` changes where you are.

## Guided lab

Create a disposable directory called `git-essentials-terminal-lab`. Inside it create `projects/website`, `projects/api`, `notes`, and `exercises`. Use only the terminal.

Useful commands to investigate:
```bash
pwd
ls
ls -la
cd
mkdir
touch
cd ..
cd ~
```

Do not blindly copy the sequence. Decide what each command needs to accomplish.

## Practice drills

### Drill A — Where am I?
Run `pwd`. Write the full path in your lab notes.

### Drill B — What's here?
Run `ls`, then `ls -la`. Explain one difference.

### Drill C — Navigation
Starting inside `projects/api`, return to the lab root, then enter `notes`.

### Drill D — Relative paths
From the lab root, create `notes/day-1.txt` without first entering `notes`.

## Break-It lab

Intentionally navigate into the wrong directory. Do not panic. Use `pwd` and `ls` to discover where you are, then return to the lab root.

The lesson is investigation, not speed.

## Challenge

You are told only: "The file `setup.txt` is somewhere under `git-essentials-terminal-lab`." Find it using terminal tools. Do not use a graphical file manager.

If you use a command you have not learned, look up its official/manual documentation first.

## Assignment

Create this structure entirely from the terminal:
```text
terminal-project/
├── src/
│   ├── app/
│   └── config/
├── docs/
└── tests/
```
Create `docs/setup.txt` and `src/app/main.txt`.

Then demonstrate that you can reach each directory using relative navigation.

## Check guidance

Expected evidence:
- `pwd` identifies the correct location.
- `ls -la` can reveal hidden entries.
- required directories/files exist.
- learner can move up/down without guessing.

There is no single required command sequence. Check the final state.

