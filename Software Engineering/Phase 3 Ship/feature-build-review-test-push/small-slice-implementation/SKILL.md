---
name: small-slice-implementation
description: Implement one feature in small vertical slices. Use when editing code to deliver behavior while preserving project patterns, owner modules, information hiding, tests, user changes, and the delivery document.
---

# Small Slice Implementation

## Definition

Implement the planned feature as the smallest working vertical slice. Make code changes in the owner modules and update `FEATURE_DELIVERY.md` whenever implementation reality changes the plan.

## Questions To Ask

- What is the next smallest behavior that can be made to work?
- Which owner module should absorb the complexity?
- What interface should stay simple for callers?
- What existing tests or fixtures can guide the edit?
- What changed from the plan?

## Existing Project Comparison

- Follow existing naming, formatting, framework, error handling, transaction, and test patterns.
- Prefer changing a deep owner module over adding pass-through layers or duplicated logic.
- Preserve unrelated user changes and avoid broad formatting churn.

## Suggestive Plan

1. Make the smallest behavior-preserving setup change.
2. Add or adjust the owner module behavior.
3. Wire the entry point to the owner module.
4. Add the test or assertion closest to the behavior.
5. Update `FEATURE_DELIVERY.md` with actual files and design changes.

## Example

Add `resendInvoiceEmail` to the billing service, call it from the admin route, and test the service rule before polishing surrounding docs.

## Vocabulary

- Small slice: minimal coherent change that can be verified.
- Deep module: module with a simple interface hiding useful implementation.
- Pass-through layer: layer that adds interface surface without hiding complexity.
- Plan drift: difference between intended and actual implementation.

## Expected Outcome

Produce working feature code in a small coherent slice, aligned with existing project patterns and documented in `FEATURE_DELIVERY.md`.
