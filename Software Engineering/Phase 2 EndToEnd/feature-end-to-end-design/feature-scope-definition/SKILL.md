---
name: feature-scope-definition
description: Define or audit the exact scope of one feature, including included behavior, excluded behavior, dependencies, and layer impact. Use before designing or implementing a feature to keep the slice small and strategic.
---

# Feature Scope Definition

## Definition

Set the boundaries for one feature. Scope protects design quality by naming what will be built now, what is deferred, and what would create unnecessary complexity.

## Questions To Ask

- What user behavior is included in this feature?
- What frontend, API, backend, data, and test work is required?
- What is explicitly excluded or deferred?
- What dependencies or prior slices are required?
- What would make this feature too large?

## Existing Project Comparison

- Compare scope against current modules, routes, schemas, components, tests, and feature docs.
- Identify hidden dependencies, unrelated refactors, and old behavior that must be preserved.
- Flag scope that duplicates another feature or crosses ownership boundaries without reason.

## Suggestive Plan

1. Define included behavior.
2. Define excluded behavior.
3. List affected layers.
4. List dependencies and assumptions.
5. Split the feature if it cannot be tested as one vertical slice.

## Example

Included: edit preferred time window for pending requests. Excluded: editing confirmed appointments, calendar sync, audit export, bulk editing.

## Vocabulary

- Feature scope: the boundary of work for one feature.
- Deferred work: known work intentionally left for later.
- Affected layer: frontend, API, backend, database, or test surface touched by the feature.
- Vertical slice: smallest end-to-end feature increment.

## Expected Outcome

Produce a scope contract with included behavior, excluded behavior, dependencies, affected layers, and split recommendations.
