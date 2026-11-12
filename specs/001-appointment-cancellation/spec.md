# Feature 001 — Appointment cancellation (starter specification)

**Status:** Deliberately incomplete; human decisions required before planning.

## Initial stakeholder request

> Let users cancel their appointments. When an appointment is cancelled, free the time slot and show a confirmation.

This is *not* an implementation-ready specification.

## User stories (draft)

- **US-1:** As a user, I want to cancel an appointment so that I can change my plans.
- **US-2:** As a user, I want to know whether my cancellation succeeded.

## Acceptance criteria (DRAFT — incomplete)

- **AC-1 / US-1:** Given an existing appointment, when a cancellation is requested, then that appointment is marked cancelled.
- **AC-2 / US-2:** Given a successful cancellation, when the user checks the result, then the user sees a confirmation.

## Decisions the human must make

Write specific, testable answers here before planning. Consider:
- **Authorization:** Who is allowed to cancel which appointments?
- **State:** What happens when an appointment has already been cancelled?
- **Timing:** Is there a cancellation cutoff? How would its time zone be interpreted?
- **Missing data:** What happens when the appointment ID does not exist?
- **Slot availability:** What does “free the time slot” mean, and what if another operation is competing for it?
- **Failures:** Which failures deserve an error versus an idempotent success?

## Open questions

- OQ-1: Who owns an appointment and how is the requester identified?
- OQ-2: What response does a different authenticated user receive?
- OQ-3: Should cancellation be permitted after the appointment's start time?
- OQ-4: Does cancellation need to be reversible?
- OQ-5: Which pieces belong in this small workshop increment versus a future system?

## Out of scope (initial workshop)

- Production deployment and account creation
- External calendars, email, payment refunds, and live notifications
- Full Django UI or REST API

## Acceptance-criteria traceability

| Criterion | Story | Planned test | Status |
| --- | --- | --- | --- |
| AC-1 | US-1 | TODO | Unreviewed |
| AC-2 | US-2 | TODO | Unreviewed |

**Before continuing:** Revise the criteria, make uncertainty explicit, then ask Codex to review them. You, not Codex, decide the policy.
