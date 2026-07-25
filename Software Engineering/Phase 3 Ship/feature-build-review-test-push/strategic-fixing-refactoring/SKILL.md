---
name: strategic-fixing-refactoring
description: Fix feature defects and refactor strategically after review or verification. Use when tests, behavior checks, plan comparison, or design review reveal issues that should be corrected without expanding scope or hiding unrelated cleanup.
---

# Strategic Fixing And Refactoring

## Definition

Apply focused fixes that make the feature correct and understandable. Invest in design where it reduces real complexity for this feature, and defer unrelated cleanup.

## Questions To Ask

- Which failing behavior or review finding must be fixed before delivery?
- What is the smallest change that fixes the cause, not just the symptom?
- Does a refactor reduce complexity enough to justify itself now?
- Could this fix accidentally change unrelated behavior?
- Which follow-up should be documented instead of bundled?

## Existing Project Comparison

- Reuse existing abstractions and test patterns.
- Fix duplicated rules by moving them toward the owner module.
- Avoid broad rewrites, opportunistic cleanup, and formatting churn outside touched areas.

## Suggestive Plan

1. Classify each issue as must-fix, document, or defer.
2. Fix the highest-risk behavioral issue first.
3. Refactor only where it clarifies ownership, hides information, or removes duplication.
4. Re-run the relevant verification.
5. Update `FEATURE_DELIVERY.md` with fixes and deferred work.

## Example

If resend permissions are duplicated in route and service, move the rule into the service, keep the route thin, and add a regression test for unauthorized resend.

## Vocabulary

- Root cause: underlying design or logic reason a failure happened.
- Refactor: behavior-preserving change that improves structure.
- Deferred work: useful but nonblocking change intentionally left out.
- Tactical fix: symptom patch that adds future maintenance cost.

## Expected Outcome

Produce focused fixes and refactors that resolve blocking issues, preserve scope, improve or maintain design quality, and update verification notes.
