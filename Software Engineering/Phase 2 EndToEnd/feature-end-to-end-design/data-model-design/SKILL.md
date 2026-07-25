---
name: data-model-design
description: Design or audit the data model for one feature, including entities, fields, constraints, indexes, ownership, migrations, and persistence boundaries. Use before implementing database or schema changes.
---

# Data Model Design

## Definition

Design the minimum persistent data shape needed for the feature while keeping schema details behind the owning module. Treat schemas as interfaces that create dependencies.

## Questions To Ask

- What state must persist for this feature outcome?
- Which existing entity owns the data?
- What new fields, tables, constraints, indexes, or migrations are needed?
- Which invariants belong in the database, domain, or transaction?
- What data must not leak to callers or clients?

## Existing Project Comparison

- Inspect existing schema, migrations, models, repositories, fixtures, and tests.
- Prefer extending existing owner concepts over duplicating data.
- Flag risky migrations, nullable ambiguity, and hidden backfills.

## Suggestive Plan

1. List data needed for the feature.
2. Map to existing entities first.
3. Propose schema changes only when necessary.
4. Define constraints and transaction needs.
5. Write migration and rollback notes.

## Example

For changing a preferred window, an existing `appointment_requests` record may need `preferred_start` and `preferred_end`, not a new scheduling table.

## Vocabulary

- Data model: persistent structure supporting feature behavior.
- Schema interface: database shape other code depends on.
- Constraint: rule enforced by data or domain layer.
- Migration: ordered schema or data change.

## Expected Outcome

Produce a data design with entities, fields, constraints, migration plan, ownership, and test needs.
