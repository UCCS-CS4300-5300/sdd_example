# Codex SDD Practice — Friday, November 13

**CS4300/5300 · instructor demonstration and optional student practice**

This repository is an intentionally small, independent sandbox. It is **not** Tom Hastings's Homework 2 and **not** any team's Sprint 4 application. The task is to practice the **Specify → Plan → Tasks → Implement (test first) → Review** workflow.

## The deliberately vague request

> Build an appointment scheduling application. Users should be able to create, view, and cancel appointments. Include tests and make sure it works.

**Do not start by asking Codex to build the entire app.** This request leaves open essential decisions about users, permissions, time conflicts, time zones, cancellations, and persistence. Your job is to make the important decisions before implementation.

## Start here (in GitHub Codespaces)

**Assume Codex is NOT installed and nobody is logged in.** Students do not need to install VS Code locally. One working Codex session per group is enough for the workshop.

1. Open this repository in a new GitHub Codespace (Code → Codespaces → Create codespace on main), then open **Terminal → New Terminal**.
2. Check that Node.js and npm are available:
   ```bash
   node --version
   npm --version
   ```
   If either command is missing, stop and ask for help rather than changing the team's application.
3. **Install Codex CLI** in the Codespace:
   ```bash
   npm install -g @openai/codex
   codex --version
   ```
   Do not use `sudo` unless the instructor helps diagnose a permissions problem.
4. **Log in** with your own authorized ChatGPT account (not the instructor's):
   ```bash
   codex login --device-auth
   ```
   Follow the URL and one-time code displayed in the terminal. If device login is unavailable or your account is not eligible, tell the instructor. **Do not buy a subscription or paste API keys into this repository.** The Sprint 3 course gateway is not a Codex login.
5. Verify authentication:
   ```bash
   codex login status
   ```
6. Make sure your terminal is in the `sdd_example` repository root (the directory containing `AGENTS.md`). Then start:
   ```bash
   codex
   ```
7. Ask: **"Summarize AGENTS.md in three bullets. Do not modify files."** Then read `specs/001-appointment-cancellation/spec.md` and work through `prompts/01-specify.md` to `prompts/05-review.md` in order.

**Security and troubleshooting:** Never share login codes, access tokens, or secrets in chat or screenshots. A successful `codex --version` means installed, **not** authenticated; check `codex login status` separately. If npm installation or login fails, join your group in reviewing the specification manually; you can still participate in the engineering decisions.

## What is already implemented?

**Nothing.** This repository intentionally contains no runnable application, dependencies, or passing tests. `spec.md` is a starter, while `plan.md` and `tasks.md` are empty templates. Do not confuse a generated test plan with executed tests. The first implementation increment should be small and test-first.

## Suggested classroom challenge

Begin with the **cancellation** feature. An authenticated user wants to cancel an appointment. Does authentication alone authorize cancelling any appointment? What should happen if it belongs to another user? What if it is already cancelled? Your first job is to resolve these questions in the spec, not to write a clever prompt.

For a first implementation, a small Python standard-library domain module is enough. Do not spend class time installing Django, deploying to Render, or setting up a database. Codex can propose a more elaborate plan, but you must approve the scope.

## Success looks like

- You can explain what behavior your spec requires and what it leaves unresolved.
- Each acceptance criterion has at least one planned test, including an error or authorization case.
- Your plan and tasks trace to requirements; one increment follows test-first development.
- You inspect the diff and run tests yourself rather than believing a generated summary.
- You can distinguish *test coverage* from *whether the right behavior was specified*.

A failed experiment or a useful newly discovered ambiguity is legitimate progress. Don't change student code, share credentials, or use this repository for graded Sprint 4 work.

**Teaching context:** This exercise follows the process from Tom Hastings's [Codex SDD Template](https://github.com/tghastings/cs4300andcs5300/tree/main/Codex%20SDD%20Template), adapted to a separate classroom example.
