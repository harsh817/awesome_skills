---
name: action-to-feature-breakdown
description: Convert actions into small buildable features with clear boundaries. Use when turning workflow actions into backlog items, reviewing feature size, or separating user-facing behavior from internal implementation tasks.
---

# Action To Feature Breakdown

## Definition

Bundle related actions into features that deliver user-visible progress. A feature should be small enough to build and test, but deep enough to hide meaningful system behavior behind a simple user interaction.

## Questions To Ask

- Which actions must ship together to create value?
- Which actions are internal implementation details?
- What is the smallest user-visible behavior that can be tested end to end?
- What business rules or failures belong to this feature?
- What can be deferred without breaking the outcome?

## Existing Project Comparison

- Compare actions to current components, endpoints, commands, and tests.
- Split features that require unrelated modules to change for unrelated reasons.
- Merge thin features that only expose implementation steps.
- Identify features that leak persistence, transport, or vendor details to users.

## Suggestive Plan

1. Group actions by user-visible value.
2. Write each feature as "user can...".
3. Add acceptance signals.
4. Add owner modules and dependencies.
5. Mark too-large features for vertical slicing.

## Example

Actions around entering, validating, and saving contact details become feature: "Patient can submit valid appointment contact details and see clear correction messages."

## Vocabulary

- Feature: a buildable unit of user-visible value.
- Acceptance signal: evidence a feature works.
- Internal task: implementation work that does not stand alone as user value.
- Deep feature: simple user surface with meaningful hidden behavior.
- Feature boundary: what belongs inside and outside a feature.

## Expected Outcome

Produce a feature list with user value, included actions, acceptance signals, dependencies, and notes about deferrable work.
