---
name: folder-and-file-structure
description: Define or audit where features, shared code, tests, migrations, configuration, and documentation belong. Use when creating a repository layout, adding files, reorganizing folders, or reducing navigation complexity and misplaced ownership.
---

# Folder And File Structure

## Definition

Define a file layout that makes ownership obvious and keeps related knowledge close. Folder structure should reduce cognitive load; it should not create shallow buckets that scatter one concept across many places.

## Process

1. Choose top-level folders by durable responsibility: app, modules, shared infrastructure, tests, migrations, docs.
2. Keep feature/domain code near the rules it owns.
3. Put tests next to the interface or behavior they verify, following the project's test convention.
4. Put migrations in one ordered location with ownership notes.
5. Keep documentation near the code it can become stale against.
6. Review new folders for pass-through naming such as `helpers`, `misc`, `common`, and `utils`.

## Rules

- Prefer consistency over clever categorization.
- Do not split one feature into controller/model/service folders if that hides the feature's real ownership.
- Shared code must be genuinely general-purpose and deeper than the code it replaces.
- A folder name should predict what belongs inside and what does not.
- Avoid parallel folder trees that require edits in many places for one feature.

## Examples

- Good: `modules/billing/commands`, `modules/billing/domain`, `modules/billing/tests`.
- Bad: `services/billing`, `validators/billing`, `types/billing`, `helpers/billing`.
- Good: `docs/adr/` for architecture decisions and `migrations/` for ordered schema changes.
- Bad: `common/date.ts` containing appointment scheduling policy.

## Vocabulary

- Locality: keeping related design decisions close enough to change together.
- Parallel hierarchy: multiple folder trees that mirror the same concepts and amplify changes.
- Shared module: code used by multiple owners without owning their domain rules.
- Misc folder: a vague bucket that hides ownership.
- Consistency: using the same structure for the same kind of concept.

## Expected Outcome

Produce a repository map with allowed locations, placement rules, naming patterns, test and migration locations, and examples of files that do not belong.
