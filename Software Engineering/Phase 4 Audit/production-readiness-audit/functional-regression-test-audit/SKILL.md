---
name: functional-regression-test-audit
description: Audit functional and regression test readiness before production. Use when confirming unit, integration, system, edge-case, smoke, and regression tests pass and adequately support safe refactoring.
---

# Functional And Regression Test Audit

## Definition

Confirm that tests provide enough evidence to change and operate the system safely. Tests are production readiness evidence and support future refactoring.

## Questions To Ask

- Which unit tests cover core rules and edge cases?
- Which integration or system tests prove parts work together?
- Which regression tests protect recently fixed failures?
- Which smoke tests prove production-critical paths?
- What test gaps remain and what risk do they create?

## Existing Project Comparison

- Inspect test scripts, CI configuration, fixtures, coverage reports, and recent failures.
- Compare tests against requirements, failure cases, migrations, security rules, and high-risk paths.
- Prefer behavior coverage over brittle private implementation assertions.

## Suggestive Plan

1. Map must-have behavior to test evidence.
2. Run relevant targeted and full test commands when available.
3. Inspect skipped, flaky, failing, or missing tests.
4. Classify test gaps as blocker, accepted risk, or follow-up.
5. Update `PRODUCTION_READINESS.md`.

## Example

For invoice payments, confirm unit tests for amount rules, integration tests for payment callbacks, system tests for paid invoice state, and regression tests for duplicate webhook handling.

## Vocabulary

- Unit test: isolated proof of a rule or small behavior.
- Integration test: proof that components work together.
- System test: proof of a full user or service workflow.
- Regression test: proof that a fixed bug stays fixed.

## Expected Outcome

Produce a test audit with pass/fail evidence, coverage by requirement, skipped or flaky tests, gaps, blockers, and accepted risk.
