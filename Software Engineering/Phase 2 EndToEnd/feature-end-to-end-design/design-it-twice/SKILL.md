---
name: design-it-twice
description: Generate and compare at least two viable designs for one feature before choosing an implementation plan. Use when a feature affects multiple layers, module boundaries, interfaces, data, or error handling.
---

# Design It Twice

## Definition

Explore multiple designs before committing. Ousterhout's design-it-twice principle reduces tactical choices by forcing comparison of tradeoffs, complexity, information hiding, and future change cost.

## Questions To Ask

- What are two or more reasonable ways to design this feature?
- Which design has the simpler interface?
- Which design hides more complexity behind the right module?
- Which design creates fewer dependencies and fewer special cases?
- Which design is easiest to test and evolve?

## Existing Project Comparison

- Compare each option with current architecture, ownership, naming, data access, and test patterns.
- Reject options that require broad unrelated changes.
- Flag any option that only seems easy because it pushes complexity onto callers.

## Suggestive Plan

1. Sketch Design A.
2. Sketch Design B.
3. Compare complexity, dependencies, interfaces, data impact, tests, and failure handling.
4. Choose a design with rationale.
5. Record rejected alternatives in the feature design document.

## Example

Option A exposes separate `validate`, `save`, and `notify` calls. Option B exposes `updateRequestWindow` and hides validation, persistence, and notification. Prefer B if it keeps callers simpler.

## Vocabulary

- Design alternative: a plausible implementation approach.
- Tradeoff: benefit and cost of one design choice.
- Deep design: simple public surface with useful hidden behavior.
- Tactical choice: quickest local option that may increase future complexity.

## Expected Outcome

Produce at least two design options, a comparison table, selected design, and rationale.
