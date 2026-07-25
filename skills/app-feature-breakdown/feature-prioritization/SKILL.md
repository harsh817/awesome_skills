---
name: feature-prioritization
description: Prioritize features by outcome value, learning value, dependency order, risk, and complexity. Use when turning a feature map into a build order or reviewing whether a backlog is tactical and too feature-first.
---

# Feature Prioritization

## Definition

Order features so each increment teaches something useful, protects design quality, and moves toward the outcome. Prioritization is not only value ranking; it also considers dependencies, abstraction discovery, risk, and validation.

## Questions To Ask

- Which feature proves the core outcome fastest?
- Which feature removes the largest unknown?
- Which dependency must exist before others?
- Which feature is risky enough to test early?
- Which feature can wait without blocking learning?

## Existing Project Comparison

- Compare planned order with current technical dependencies and tests.
- Identify features blocked by missing abstractions or rules.
- Flag high-priority features that would force tactical shortcuts.
- Move risk-reducing spikes or slices earlier when they protect architecture.

## Suggestive Plan

1. Score each feature for outcome value, learning value, risk reduction, dependency need, and complexity cost.
2. Identify mandatory first slices.
3. Put abstraction-revealing work before broad surface area.
4. Defer nice-to-have features.
5. Produce an ordered build list with rationale.

## Example

Build "submit appointment request" before "staff dashboard filters" because it proves the core journey and reveals scheduling rules.

## Vocabulary

- Outcome value: contribution to the desired result.
- Learning value: how much uncertainty a feature removes.
- Risk reduction: early work that prevents expensive later discovery.
- Dependency: feature or rule another feature requires.
- Tactical priority: ordering chosen only because it is quick.

## Expected Outcome

Produce a prioritized feature list with reason, dependencies, risk, estimated complexity, and suggested build order.
