---
name: git-and-change-rules
description: Define or audit branch rules, commit scope, diff review, ignored files, push conditions, and change hygiene. Use before committing, opening a PR, reviewing local changes, or preventing unrelated tactical edits from accumulating.
---

# Git And Change Rules

## Definition

Define change hygiene so complexity does not accumulate unnoticed. Each branch, commit, and pull request should represent a coherent design move with reviewed consequences.

## Process

1. Start from a clean understanding of existing changes.
2. Keep each change focused on one goal or clearly related set of files.
3. Review the diff for accidental files, generated artifacts, secrets, debug code, and unrelated refactors.
4. Run the required verification before commit or push.
5. Write commit messages that explain the user-visible or architectural reason.
6. Push only when requested or when project rules explicitly allow it.

## Rules

- Never hide unrelated changes inside a feature commit.
- Do not commit secrets, local config, build output, caches, or personal files.
- Prefer small strategic improvements tied to the task over broad opportunistic cleanup.
- If a change introduces complexity, explain the benefit and why it is worth it.
- Treat deleted files and migrations as high-review changes.

## Examples

- Good commit: "Enforce appointment cutoff in scheduling module."
- Bad commit: "misc fixes."
- Good PR scope: feature code, tests, migration, and docs for the same behavior.
- Bad PR scope: feature plus formatting every file in the repo.

## Vocabulary

- Diff review: reading the exact changed lines before delivery.
- Commit scope: the conceptual boundary of a commit.
- Tactical cleanup: unrelated edits made because the file was nearby.
- Generated artifact: file produced by tools that may not belong in source control.
- Push condition: rule deciding when local work may be sent to a remote.

## Expected Outcome

Produce git rules covering branch naming, commit size, ignored files, diff checks, required tests, push policy, and what to report before handoff.
