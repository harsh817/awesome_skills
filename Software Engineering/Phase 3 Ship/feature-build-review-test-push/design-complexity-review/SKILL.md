---
name: design-complexity-review
description: Review feature code for design quality and complexity using Ousterhout-style principles. Use after implementation to find tactical patches, shallow modules, information leakage, vague names, pass-through methods, duplicated rules, avoidable special cases, and nonobvious code.
---

# Design Complexity Review

## Definition

Review the implementation for unnecessary complexity. Working code is not enough; the change should make future work easier or at least avoid making it harder.

## Questions To Ask

- Does the code hide complexity behind simple interfaces?
- Did the change create or deepen the right module?
- Are design decisions duplicated across files?
- Are names precise and consistent with the domain?
- Can any error or special case be designed out of existence?

## Existing Project Comparison

- Compare changed code against neighboring patterns and domain vocabulary.
- Look for shallow modules, information leakage, temporal decomposition, pass-through methods, repeated logic, special-general mixtures, vague names, and nonobvious code.
- Check whether added complexity is justified by a larger simplification elsewhere.

## Suggestive Plan

1. Read the diff and nearby owner modules.
2. Identify complexity added, removed, or moved.
3. Flag high-value design issues first.
4. Recommend strategic fixes tied to the feature.
5. Record accepted and deferred review items in `FEATURE_DELIVERY.md`.

## Example

If a new route validates invoice permissions, status, and email eligibility inline, recommend moving those rules into the billing service so the route stays a simple entry point.

## Vocabulary

- Complexity: anything that makes software hard to understand or modify.
- Change amplification: one small behavior change requiring edits in many places.
- Cognitive load: how much a developer must know to make a change safely.
- Obscurity: important information that is hard to discover.

## Expected Outcome

Produce a prioritized design review with complexity risks, recommended fixes, accepted tradeoffs, and deferred items.
