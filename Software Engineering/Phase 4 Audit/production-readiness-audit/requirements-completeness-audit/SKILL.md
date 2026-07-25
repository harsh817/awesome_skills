---
name: requirements-completeness-audit
description: Audit production requirements completeness for a release, feature set, or system. Use when confirming every must-have user journey, acceptance condition, non-goal boundary, and documented requirement works before production readiness.
---

# Requirements Completeness Audit

## Definition

Confirm that the product does what it must do for production. Treat requirements as user journeys plus observable acceptance conditions, not just ticket text.

## Questions To Ask

- What journeys are must-have for this release?
- Which acceptance conditions define success for each journey?
- Which roles, permissions, states, and failure paths must be included?
- What requirements are explicitly out of scope?
- What proof shows each condition works?

## Existing Project Comparison

- Compare `FEATURE_MAP.md`, `FEATURE_DESIGN.md`, tickets, docs, tests, and current behavior.
- Trace each must-have journey to code, test evidence, and manual or automated verification.
- Mark unknown, ambiguous, or untested requirements as readiness risks.

## Suggestive Plan

1. List all must-have journeys and acceptance conditions.
2. Map each condition to evidence.
3. Run or inspect verification for missing evidence.
4. Classify gaps as blocker, accepted risk, or out of scope.
5. Update `PRODUCTION_READINESS.md`.

## Example

For invoicing, confirm create invoice, edit draft, approve, send, pay, void, and export journeys work for every required role.

## Vocabulary

- Must-have journey: user path required for production launch.
- Acceptance condition: observable proof that a journey works.
- Traceability: link from requirement to implementation and evidence.
- Scope boundary: explicit line between included and excluded behavior.

## Expected Outcome

Produce a requirements audit showing every must-have journey, its acceptance evidence, gaps, blockers, accepted risks, and open questions.
