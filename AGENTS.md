# AGENTS.md — Codex SDD practice rules

You are assisting with a **practice repository**, not a live or graded student project. The human owns the decisions. Follow **Specify → Plan → Tasks → Implement (test first) → Review**.

## Source of truth
- Read `specs/001-appointment-cancellation/spec.md` before proposing anything.
- `spec.md` describes *what* should happen, `plan.md` describes *how*, and `tasks.md` describes incremental work.
- If a requirement is ambiguous, **ask** or record an Open Question. Never silently decide an authorization rule.
- Do not implement anything solely because it sounds reasonable.

## Operating rules
1. On a specification-review request, **do not write code** or rewrite the human's specification. Identify weaknesses and ask focused questions.
2. On a plan request, propose a minimal solution appropriate for a short workshop: Python standard library only, in-memory state, no web server, external API, or deployment unless the human explicitly approves otherwise.
3. On a task request, map every acceptance criterion (`AC-#`) to at least one test; include negative paths.
4. On an implementation request, do only the **next approved unchecked task**. Write the test first; run it and show the result; add minimal implementation; run the full suite; stop. If the new test initially passes, say so—do not fake a red step.
5. After each increment, report changed files, test results, remaining gaps, and a concept worth understanding.
6. Never weaken/delete an existing test solely to achieve a green test run. If a test is inappropriate, flag it to the human.
7. Do not automatically commit, push, merge, rewrite history, or edit files outside this repository.
8. Do not access or print secrets. This project needs no API calls beyond the Codex session itself.

## Test and evaluation habits
- Prefer `python -m unittest discover -s tests -v`; use built-in `trace` only if the human wants rough execution tracing, and explain its limitations.
- Keep requirements, test assertions, and implementation independently reviewable.
- Coverage, test counts, and green checks do **not** demonstrate that all necessary behavior was specified.
- The final reviewer should ideally be a fresh session and should not alter code.

## Classroom stop conditions
If a plan would install dependencies, edit a team repository, require a paid service, or invoke live external systems, **stop and ask**. This is a safe place to try and revise decisions.
