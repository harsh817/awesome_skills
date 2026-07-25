---
name: feature-outcome-definition
description: Define or audit the specific outcome of one feature before designing frontend, API, backend, data, and tests. Use when a feature idea is vague, too broad, disconnected from the product outcome, or needs a precise success target.
---

# Feature Outcome Definition

## Definition

Define the user-visible result this one feature must produce. Keep the outcome smaller than the whole app outcome and concrete enough to guide design decisions across every layer.

## Questions To Ask

- What changes for the user when this feature works?
- Which app outcome or feature map item does this support?
- What must the user be able to do after this feature ships?
- What visible or testable signal proves success?
- What is not part of this feature outcome?

## Existing Project Comparison

- Compare the requested feature with `FEATURE_MAP.md`, `AGENT_GUARDRAILS.md`, README, issues, routes, tests, and current UI.
- Identify whether the feature already exists, partially exists, or conflicts with current behavior.
- Flag any outcome that would force unrelated modules to change.

## Suggestive Plan

1. Write a one-sentence feature outcome.
2. Link it to the app outcome or feature map.
3. Define success signals and non-goals.
4. Record assumptions and open questions.
5. Use the outcome to reject scope creep.

## Example

- Weak: "Add appointment editing."
- Strong: "Receptionists can change a pending appointment request's preferred time window and see the updated request reflected in scheduling review."

## Vocabulary

- Feature outcome: the useful result this feature creates.
- Success signal: observable evidence that the feature works.
- Non-goal: behavior intentionally excluded.
- Scope creep: extra work not required for the feature outcome.

## Expected Outcome

Produce a feature outcome statement with success signals, non-goals, assumptions, and project links.
