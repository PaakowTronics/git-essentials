# 02 — Documentation & Software Setup

## Outcomes

- Identify Linux distribution and architecture.
- Find authoritative installation documentation.
- distinguish platform-specific instructions.
- follow documentation without blind copying.
- verify software installation.
- investigate installation errors.

## Mental model

Professional setup work is a loop: identify environment → find authoritative documentation → read prerequisites → execute carefully → verify → troubleshoot.

## Guided mission

First identify the system:
```bash
cat /etc/os-release
uname -m
```
For Debian-based systems, investigate:
```bash
dpkg --print-architecture
```

Then use official documentation to install Git:
https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

Do not use a third-party tutorial as your primary source.

## Practice drills

### Drill A — Documentation map
Find the installation section that applies to your OS.

### Drill B — Verification
After installation, determine how the official documentation recommends verifying Git.

### Drill C — Docker mission
Use Docker's official installation documentation:
https://docs.docker.com/engine/install/
Choose the correct platform page and record prerequisites, installation method, and verification.

### Drill D — Documentation safety
Find a command that uses elevated privileges. Explain what it changes before running it.

## Break-It lab

Use a disposable VM/container where possible. Introduce a controlled setup problem such as an incomplete prerequisite. Your job is to read the error, identify the relevant documentation section, fix the prerequisite, and verify.

## Challenge

Choose a legitimate developer tool with official Linux installation documentation. Install it without receiving a command list. Submit:
OS, architecture, documentation URL, prerequisites, installation approach, verification command, installed version.

## Assignment

Perform a fresh Git installation from official documentation. Then write a one-page installation report explaining how you selected the correct instructions and how you verified success.

## Check guidance

Full credit requires evidence that the learner:
- identified their actual platform;
- used authoritative documentation;
- understood prerequisites;
- verified the installation;
- can explain what they did.

Do not award full credit merely because the software happens to be installed.

