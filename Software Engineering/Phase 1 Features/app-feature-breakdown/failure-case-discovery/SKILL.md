---
name: failure-case-discovery
description: Discover failure cases, edge cases, invalid states, and recoverable errors for planned features. Use when designing resilient workflows, reducing hidden unknowns, or deciding which errors can be defined out of existence.
---

# Failure Case Discovery

## Definition

Identify what can go wrong and decide how much complexity each case deserves. Prefer defining errors and special cases out of existence where simple semantics can remove the failure from callers.

## Questions To Ask

- What input can be missing, invalid, stale, duplicated, or unauthorized?
- What external systems can fail or be slow?
- What state can change between user action and system response?
- Which failures can the user correct?
- Which failures should be retried, ignored, reported, or blocked?

## Existing Project Comparison

- Inspect error handling, validation, logs, tests, and empty states.
- Find exceptions thrown from low-level code that callers cannot handle meaningfully.
- Identify over-defensive checks that add complexity without user value.
- Look for missing tests around known failure paths.

## Suggestive Plan

1. List failure cases per feature.
2. Classify each as user-correctable, system-recoverable, authorization, data conflict, external dependency, or internal bug.
3. Decide the response and owner.
4. Define errors out of existence where possible.
5. Add acceptance and regression tests.

## Example

If a user accepts a slot that has just been taken, the feature should re-check availability and offer next options, not expose a database conflict.

## Vocabulary

- Failure case: condition that prevents the happy path.
- Edge case: uncommon but valid situation.
- Recoverable error: failure the app can handle and continue from.
- Define errors out of existence: choose semantics that eliminate unnecessary error handling.
- Error owner: module that decides how a failure is handled.

## Expected Outcome

Produce a failure matrix with case, trigger, user message, system response, owner, test need, and simplification opportunity.
