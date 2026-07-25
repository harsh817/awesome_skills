---
name: testing-rules
description: Define or audit required tests, test locations, behavioral seams, fixtures, and verification expectations. Use when adding features, fixing bugs, planning coverage, or preventing tests from coupling to implementation details.
---

# Testing Rules

## Definition

Define tests as a way to protect behavior while preserving module depth. Tests should verify interfaces and invariants, not freeze private implementation details.

## Process

1. Identify the behavior or bug before writing the test.
2. Choose the narrowest stable seam that gives confidence.
3. Test domain rules through owner modules and public interfaces.
4. Add integration tests where module contracts, database behavior, or external boundaries matter.
5. Add regression tests for every fixed bug.
6. Keep fixtures small, named, and aligned with domain vocabulary.

## Rules

- Do not test private helpers just because they exist.
- Avoid tautological tests that recompute the same logic as the implementation.
- Prefer expected values from requirements, examples, or known facts.
- Tests should reduce fear of change, not make refactoring harder.
- Keep test names explicit about behavior and outcome.

## Examples

- Good: "cancels an appointment only when requested before the clinic cutoff."
- Bad: "calls validateCutoff before saveAppointment."
- Good: migration test proves existing rows get a valid default.
- Bad: snapshot test of a large object with no named behavior.

## Vocabulary

- Seam: the interface where a behavior can be observed.
- Regression test: a test that prevents a known bug from returning.
- Fixture: reusable test data.
- Implementation coupling: tests depending on private structure rather than behavior.
- Tautological test: a test whose expected value is produced by the same logic under test.
- Confidence: evidence that a future change can be made safely.

## Expected Outcome

Produce test rules covering required coverage by change type, test locations, seams, fixture style, regression expectations, and commands to run before delivery.
