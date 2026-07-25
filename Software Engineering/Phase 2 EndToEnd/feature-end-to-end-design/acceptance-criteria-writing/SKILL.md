---
name: acceptance-criteria-writing
description: Write or audit acceptance criteria for one feature across success, validation, permissions, state changes, and visible results. Use when a feature needs clear done criteria before implementation or tests.
---

# Acceptance Criteria Writing

## Definition

Write criteria that prove the feature outcome has been achieved. Acceptance criteria describe observable behavior, not private implementation steps.

## Questions To Ask

- What must be true for the feature to count as done?
- What user actions and system responses must be observable?
- What rules, permissions, validations, and state changes matter?
- What should happen when inputs are invalid or state changes?
- Which criteria can become tests?

## Existing Project Comparison

- Compare criteria with existing tests, UI copy, route behavior, and business rules.
- Flag criteria that assert implementation order instead of user-visible behavior.
- Add missing criteria for failure states and permissions.

## Suggestive Plan

1. Write happy-path criteria.
2. Add validation and permission criteria.
3. Add persistence and state criteria.
4. Add user feedback criteria.
5. Mark each criterion as unit, integration, or end-to-end test candidate.

## Example

Given a pending request, when a receptionist saves a valid new preferred window, then the request shows the new window and remains pending.

## Vocabulary

- Acceptance criterion: condition that proves feature completion.
- Observable behavior: result visible through UI, API, data state, or testable output.
- Given-when-then: format for behavior criteria.
- Done criteria: checks required before the feature is complete.

## Expected Outcome

Produce acceptance criteria covering happy path, validations, permissions, persistence, errors, and test mapping.
