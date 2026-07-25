---
name: run-behavior-verification
description: Verify implemented feature behavior by running relevant commands, manual checks, screenshots, smoke tests, logs, or API checks. Use after coding and before review to prove the user-visible behavior works.
---

# Run Behavior Verification

## Definition

Prove the implemented behavior works in the running project, not just in static code. Choose checks that match the feature surface and record results in `FEATURE_DELIVERY.md`.

## Questions To Ask

- What user-visible behavior must be proven?
- Which command, page, API call, job, or workflow exercises it?
- What expected state change, response, screen, or side effect confirms success?
- What negative or edge behavior should be checked?
- What verification gap remains if a check cannot run?

## Existing Project Comparison

- Use existing scripts, test commands, dev-server patterns, seed data, and smoke checks.
- Compare observed behavior against acceptance criteria and `FEATURE_DESIGN.md`.
- Check logs or UI state when the feature depends on side effects.

## Suggestive Plan

1. Identify the smallest behavior check that exercises the feature.
2. Run relevant automated commands first when available.
3. Run manual, browser, API, or job checks when automated tests are insufficient.
4. Record exact results, failures, and gaps.
5. Send failures back to `$strategic-fixing-refactoring`.

## Example

After adding invoice resend, run billing tests, start the app if needed, call the resend route with a known invoice, and confirm the audit entry and email adapter call.

## Vocabulary

- Smoke check: fast check that proves the main path is wired.
- Behavior check: verification of observable feature behavior.
- Side effect: effect outside the main state write, such as email or a job.
- Verification gap: risk left because a relevant check could not be run.

## Expected Outcome

Produce recorded verification evidence showing the feature works, what commands or checks ran, what passed or failed, and what gaps remain.
