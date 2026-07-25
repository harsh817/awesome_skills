---
name: implementation-planning
description: Plan a small strategic implementation slice for one feature after repository inspection. Use when deciding files, order of work, tests, verification, risks, and how to keep the change understandable before coding.
---

# Implementation Planning

## Definition

Turn the feature target and repository inspection into a build plan. Prefer a small vertical slice that proves behavior while making modest design investments that reduce future complexity.

## Questions To Ask

- What is the smallest slice that demonstrates the feature outcome?
- Which existing module should own each rule, state change, and interface?
- What code can be reused without copying behavior?
- What tests will prove the slice works?
- What complexity might this change add, and how can it be contained?

## Existing Project Comparison

- Compare the plan against existing architecture, naming, test style, and dependency direction.
- Check whether the plan pulls complexity downward or exposes it to callers.
- Avoid temporal decomposition such as separate "add database", "add backend", and "add UI" tasks unless they are notes inside one vertical slice.

## Suggestive Plan

1. Restate the feature target and acceptance criteria.
2. Choose one end-to-end implementation slice.
3. List files to change and the reason for each.
4. Define tests and behavior checks before editing.
5. Add fallback, migration, or rollback notes when risk requires them.

## Example

Plan "resend invoice email" as one slice: API action, invoice service method, email adapter call, status audit entry, unit tests for rules, and an integration check for the route.

## Vocabulary

- Vertical slice: a small end-to-end change that reaches the user-visible outcome.
- Strategic programming: investing a little extra time to improve design while coding.
- Tactical patch: quick change that works by adding avoidable complexity.
- Acceptance criterion: observable condition proving the feature is done.

## Expected Outcome

Produce a concrete implementation plan with scope, files, sequence, tests, verification, risks, and complexity-control choices.
