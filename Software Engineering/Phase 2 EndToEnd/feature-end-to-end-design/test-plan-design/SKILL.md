---
name: test-plan-design
description: Design the test plan for one feature across unit, integration, API, UI, end-to-end, migration, and regression tests. Use before implementation to align tests with acceptance criteria and module interfaces.
---

# Test Plan Design

## Definition

Design tests that prove the feature works through stable interfaces. Tests should protect behavior and design boundaries without coupling to private implementation details.

## Questions To Ask

- Which acceptance criteria need tests?
- Which business rules need focused unit or integration tests?
- Which API contracts need request/response tests?
- Which frontend flows need UI or end-to-end tests?
- Which migrations or data constraints need verification?

## Existing Project Comparison

- Inspect current test tools, file locations, naming, fixtures, and helper patterns.
- Reuse existing test seams.
- Flag missing regression coverage for known failures.
- Avoid tests that assert private call order.

## Suggestive Plan

1. Map acceptance criteria to tests.
2. Choose the narrowest stable test seam for each behavior.
3. Add integration or end-to-end tests for cross-layer behavior.
4. Add failure and permission tests.
5. List verification commands.

## Example

Test backend rule that only pending requests can change windows; API test for conflict response; UI test for inline validation and success state.

## Vocabulary

- Test seam: stable interface where behavior can be observed.
- Regression test: test preventing a known bug from returning.
- Integration test: test across modules or infrastructure.
- End-to-end test: test through real user or API entry point.

## Expected Outcome

Produce a test plan with test cases, levels, locations, fixtures, acceptance mapping, and verification commands.
