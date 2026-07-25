---
name: plan-to-code-comparison
description: Compare implemented code against the feature plan, delivery document, and project constraints. Use after implementation to find missing acceptance criteria, plan drift, stale documents, and unintended behavior.
---

# Plan To Code Comparison

## Definition

Check whether the code faithfully implements the plan. Treat divergence as useful information: either fix the code, update the plan, or ask for a decision.

## Questions To Ask

- Which acceptance criteria are fully implemented?
- Which planned files, modules, or tests changed differently than expected?
- Did the implementation add behavior outside the feature scope?
- Did code reveal a better design than the original plan?
- Which documents must be updated to match reality?

## Existing Project Comparison

- Compare code to `FEATURE_DESIGN.md`, `FEATURE_MAP.md`, `AGENT_GUARDRAILS.md`, and `FEATURE_DELIVERY.md`.
- Compare changed files to existing module ownership and interface conventions.
- Check whether any new dependency, data field, route, or public behavior is undocumented.

## Suggestive Plan

1. List planned acceptance criteria and mark implemented, missing, changed, or rejected.
2. Compare planned file changes with actual diff.
3. Identify scope creep and unplanned behavior.
4. Update the plan when implementation discovered valid facts.
5. Send missing behavior or accidental divergence back for fixing.

## Example

If the plan called for an audit entry but the diff only sends email, mark that criterion missing and either implement it or update the plan with the reason it no longer applies.

## Vocabulary

- Plan drift: mismatch between written plan and implemented code.
- Scope creep: behavior added beyond the feature target.
- Traceability: visible link from requirement to implementation and test.
- Stale document: document that contradicts current code or decisions.

## Expected Outcome

Produce a plan-to-code comparison with matched criteria, missing work, justified changes, stale documents, and required fixes.
