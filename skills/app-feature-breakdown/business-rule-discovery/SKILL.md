---
name: business-rule-discovery
description: Discover business rules, invariants, policies, limits, and decisions hidden inside outcomes, journeys, actions, or existing code. Use when feature maps need domain rules before implementation or when rules appear duplicated across a project.
---

# Business Rule Discovery

## Definition

Find the rules that decide what is allowed, required, calculated, blocked, or changed. Business rules should be owned explicitly so they do not leak across UI, routes, data access, and tests.

## Questions To Ask

- What must always be true?
- What is allowed, forbidden, required, optional, or calculated?
- Who can make this decision?
- What changes when user type, time, status, amount, or location changes?
- Which rules are legal, policy, workflow, or product choices?

## Existing Project Comparison

- Search validation, conditionals, database constraints, tests, comments, and UI copy.
- Compare duplicate rules across layers.
- Identify rule owners and places where rules are only implied.
- Flag rules that are spread across modules and increase change amplification.

## Suggestive Plan

1. Extract candidate rules from each feature.
2. Mark invariant, policy, calculation, permission, or lifecycle rule.
3. Assign an owner module.
4. Add examples and counterexamples.
5. Record unknown rules as questions.

## Example

"Appointment can be cancelled by a patient until 24 hours before clinic-local start time" is a business rule. The owner is scheduling, not the UI.

## Vocabulary

- Business rule: domain decision that controls behavior.
- Invariant: rule that must always remain true.
- Policy: organizational decision that may change.
- Rule owner: module responsible for enforcing and explaining a rule.
- Leakage: the same rule duplicated in multiple places.

## Expected Outcome

Produce a rule catalog with rule text, type, owner, examples, enforcement point, tests needed, and open questions.
