---
name: data-and-migration-rules
description: Define or audit schema ownership, constraints, transactions, data access boundaries, and safe migration practices. Use when adding tables, changing fields, writing migrations, or preventing persistence details from leaking through the system.
---

# Data And Migration Rules

## Definition

Define how persistent data changes safely while preserving information hiding. Schemas are interfaces: they create dependencies for code, reports, migrations, and operations.

## Process

1. Assign each table, collection, or model to an owner module.
2. Put invariants in the strongest practical place: domain rule, database constraint, or transaction.
3. Keep raw persistence shapes behind repositories or data access modules.
4. Write migrations as ordered, reviewable, reversible where practical, and safe for existing data.
5. Separate expand and contract steps for risky production changes.
6. Verify migrations with tests, local migration runs, and rollback notes when relevant.

## Rules

- Do not let UI or route code depend directly on database schema details.
- Do not duplicate validation that belongs in a schema constraint or owner module.
- Treat nullability, defaults, indexes, uniqueness, and foreign keys as design decisions.
- Avoid data migrations that require hidden manual steps.
- Keep transactions inside the module that understands the invariant.

## Examples

- Good: add nullable column, backfill, deploy reads, deploy writes, then make non-null.
- Bad: rename a column and update all callers in one risky deploy.
- Good: `appointments` owns `appointment_slots` and exposes repository methods.
- Bad: analytics code mutates production domain tables directly.

## Vocabulary

- Schema interface: database structure other code depends on.
- Constraint: a rule enforced by the database or domain.
- Migration: an ordered change to persistent structure or data.
- Expand-contract: safe multi-step migration from old shape to new shape.
- Transaction boundary: the smallest unit that must succeed or fail together.
- Data leakage: persistence detail exposed where it does not belong.

## Expected Outcome

Produce data rules covering schema ownership, access boundaries, constraints, migration order, transaction policy, backfill safety, and verification steps.
