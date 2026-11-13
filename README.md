# Codex SDD Practice — Friday, November 13

**CS4300/5300 · instructor demonstration and optional student practice**

This repository is an intentionally small, independent sandbox. It is **not** Dr. Hastings's Homework 2 and **not** any team's Sprint 4 application. The task is to practice the **Specify → Plan → Tasks → Implement (test first) → Review** workflow.

## The deliberately vague request

> Build an appointment scheduling application. Users should be able to create, view, and cancel appointments. Include tests and make sure it works.

**Do not start by asking Codex to build the entire app.** This request leaves open essential decisions about users, permissions, time conflicts, time zones, cancellations, and persistence. Your job is to make the important decisions before implementation.

## Start here (in GitHub Codespaces)

**Assume your chosen coding agent is NOT installed and nobody is logged in.** Students do not need to install VS Code locally. One working coding-agent session per group is enough for the workshop. **Codex and Claude Code are both welcome; the SDD reasoning and prompts are the same.**

1. **Fork this repository into your own GitHub account** (or make a personal copy). Open a Codespace from **your fork/copy**, not the shared instructor repository (Code → Codespaces → Create codespace on main), then open **Terminal → New Terminal**.
2. Check that Node.js and npm are available:
   ```bash
   node --version
   npm --version
   ```
   If either command is missing, stop and ask for help rather than changing the team's application.
3. **If using Codex, install Codex CLI** in the Codespace:
   ```bash
   npm install -g @openai/codex
   codex --version
   ```
   Do not use `sudo` unless the instructor helps diagnose a permissions problem.
4. **Option A — Log in with a personal ChatGPT account** (not the instructor's):
   ```bash
   codex login --device-auth
   ```
   Follow the URL and one-time code displayed in the terminal. If device login is unavailable or your account is not eligible, see Option B below or tell the instructor. **Do not buy a subscription or paste API keys into this repository.** The Sprint 3 course gateway is not a Codex login.
5. Verify authentication for the ChatGPT-account route:
   ```bash
   codex login status
   ```
6. Make sure your terminal is in the `sdd_example` repository root (the directory containing `AGENTS.md`). Then start:
   ```bash
   codex
   ```
7. Ask: **"Summarize AGENTS.md in three bullets. Do not modify files."** Then read `specs/001-appointment-cancellation/spec.md`. For the in-class activity, use the prompts in the Canvas worksheet; the repository's `prompts/01-specify.md` through `prompts/05-review.md` are available for deeper optional practice.

## Option B — Using UCCS-provided ChatGPT access or an OpenAI API key

If your ChatGPT access is provided through **UCCS**, the institutional sign-in may not work with Codex's personal-account device-login flow. When you start Codex with `codex`, it can present **multiple sign-in methods**. Choose the method supported by your account:

- **Sign in with ChatGPT** if your account supports it. Follow the browser/device authorization flow.
- **Use an OpenAI API key** only if you already have an authorized OpenAI Platform account/project and permission to use its API budget. Open [OpenAI Platform — API keys](https://platform.openai.com/api-keys) and create a **secret API key** for the appropriate project. **This is not a public key.** Copy it once and keep it private. An institutional ChatGPT license does **not** automatically mean you have API access or API credits.

If you are authorized to use an API key, provide it through Codex's supported **API-key sign-in option** when prompted. Do **not** paste the key into Codex chat, `AGENTS.md`, `spec.md`, source files, a committed `.env` file, screenshots, or a shared terminal. Do not share the key with teammates. API usage may incur charges to the associated project; check with the instructor or UCCS administrator before using it.

If you have UCCS ChatGPT access but **no authorized API key**, do not create a billable project just for this workshop. Work with a teammate who has working access, use another approved assistant (such as Claude), or complete the worksheet manually. The engineering reasoning—not access to a particular paid tool—is assessed.

**Security and troubleshooting:** Never share login codes, access tokens, or secrets in chat or screenshots. A successful `codex --version` means installed, **not** authenticated; check `codex login status` separately. If npm installation or login fails, join your group in reviewing the specification manually; you can still participate in the engineering decisions.


## Prefer Claude? Use Claude Code in the same Codespace

If you already use **Claude Code**, you may use it instead of Codex. Start from **your own fork/copy** of this repository and open its Codespace. In the Codespaces terminal, install Claude Code using Anthropic's native installer:

```bash
curl -fsSL https://claude.ai/install.sh | bash
claude --version
claude
```

Follow Claude Code's sign-in instructions using **your own authorized account**. If needed, use `/login` inside Claude Code. Claude Code access may require an eligible paid Claude plan or billed API access; **do not purchase anything for this workshop**. If you already have access, use it. If you do not, work with a teammate or complete the worksheet's reasoning manually.

**Use the same SDD prompts** from the Canvas worksheet. Claude Code can read `AGENTS.md` when a prompt explicitly asks it to; you do not need to create a `CLAUDE.md` file for this exercise. The prompts about reviewing the specification, comparing options, and documenting a human decision work with either agent. A regular Claude chat session can also help with the reasoning if you paste the relevant specification text, though it cannot directly inspect the Codespace repository.

Never share credentials or authentication codes. Do not paste API keys into files or commit them to GitHub.

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

**Teaching context:** This exercise follows the process from Dr. Hastings's [Codex SDD Template](https://github.com/tghastings/cs4300andcs5300/tree/main/Codex%20SDD%20Template), adapted to a separate classroom example.
