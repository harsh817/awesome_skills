---
name: test-implementation
description: Add or update tests for one implemented feature. Use when deciding unit, integration, system, regression, or smoke tests that prove behavior while respecting existing project test style and avoiding brittle implementation coupling.
---

# Test Implementation

## Definition

Create tests that give developers confidence to improve the design. Prefer behavior-focused tests close to the rule owner, with broader checks only where integration risk matters.

## Questions To Ask

- What behavior, rule, or bug would fail without this feature?
- Which existing test layer best owns that proof?
- What unit tests cover domain rules or edge cases?
- What integration or system tests prove wiring between parts?
- What risk remains untested and why?

## Existing Project Comparison

- Follow existing test framework, naming, fixture, mocking, and assertion style.
- Avoid coupling tests to private implementation unless that is the existing project norm and no better seam exists.
- Add regression tests for fixed defects and edge cases discovered during implementation.

## Suggestive Plan

1. Map acceptance criteria to tests.
2. Add the closest test for owner-module behavior.
3. Add integration or route/UI coverage for wiring risk.
4. Run targeted tests, then broader checks as risk requires.
5. Record coverage rationale and gaps in `FEATURE_DELIVERY.md`.

## Example

For invoice resend, test service rules for status and permission, then test the route calls the service and returns the expected response.

## Vocabulary

- Unit test: isolated test of a small behavior or rule.
- Integration test: test proving parts work together.
- Regression test: test that fails for a bug before the fix.
- Test seam: stable boundary where behavior can be observed.

## Expected Outcome

Produce feature tests that cover acceptance criteria, important failures, integration risk, and documented remaining gaps.
