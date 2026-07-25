---
name: data-migration-audit
description: Audit data and migration readiness before production. Use when checking schema constraints, transactions, migration safety, compatibility, backups, restore tests, data-loss risks, and rollback implications.
---

# Data And Migration Audit

## Definition

Confirm production data can survive the release. Schema, transaction, migration, backup, and rollback choices must protect correctness and recoverability.

## Questions To Ask

- What data changes are included in this release?
- Which constraints and invariants must the database enforce?
- Are migrations backward-compatible with currently deployed code?
- What backup and restore evidence exists?
- What data-loss or partial-write risks remain?

## Existing Project Comparison

- Inspect schema files, migrations, data access code, transactions, seed data, rollback notes, backups, and restore procedures.
- Compare data invariants against business rules and tests.
- Check migration ordering, locking, idempotency, and compatibility with rolling deploys.

## Suggestive Plan

1. List schema, migration, and data behavior changes.
2. Inspect constraints, indexes, transactions, and owner modules.
3. Verify migration apply, rollback, backup, and restore evidence.
4. Identify data-loss, compatibility, and concurrency risks.
5. Update `PRODUCTION_READINESS.md`.

## Example

For adding invoice numbers, verify uniqueness constraints, backfill safety, concurrent creation behavior, rollback effect, and restore procedure.

## Vocabulary

- Invariant: rule that must always remain true.
- Backfill: migration that populates existing data.
- Compatibility: ability of old and new code/data to coexist safely.
- Restore test: proof that backup data can be recovered.

## Expected Outcome

Produce a data audit with migration evidence, constraints, transaction risks, compatibility notes, backup and restore status, blockers, and accepted risks.
