---
name: error-and-edge-case-design
description: Design error handling and edge cases for one feature across frontend, API, backend, database, and tests. Use when deciding which failures to prevent, define away, recover from, or expose to users.
---

# Error And Edge-Case Design

## Definition

Identify exceptional and uncommon situations, then choose simple semantics for each. Prefer defining errors and special cases out of existence when it reduces complexity without hiding important truth.

## Questions To Ask

- What invalid input, stale state, permission failure, conflict, or external failure can happen?
- Which cases can the user correct?
- Which cases should be prevented by design?
- Which errors can be merged under one response?
- What should be logged, retried, or surfaced?

## Existing Project Comparison

- Inspect existing error types, handlers, UI messages, database constraints, retries, logs, and tests.
- Flag inconsistent error shapes or duplicate edge-case logic.
- Avoid adding rare error branches that every caller must understand.

## Suggestive Plan

1. List errors by layer.
2. Classify user-correctable, conflict, permission, external, and internal bug cases.
3. Define response semantics and owner.
4. Simplify or define away unnecessary cases.
5. Add tests for important failures.

## Example

If the request was confirmed while the editor was open, return a conflict response and show "This request is already confirmed; refresh to view the current appointment."

## Vocabulary

- Edge case: uncommon but possible situation.
- Conflict: state changed so the requested action no longer applies.
- Define away: choose semantics that eliminate unnecessary failure handling.
- Error owner: module responsible for response and recovery.

## Expected Outcome

Produce an error matrix covering cases, layer, user message, system response, owner, simplification option, and tests.
