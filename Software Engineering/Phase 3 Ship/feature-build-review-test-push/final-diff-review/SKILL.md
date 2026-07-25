---
name: final-diff-review
description: Review the final local diff before delivery, commit, or push. Use when checking changed files for accidental edits, unrelated changes, secrets, generated artifacts, missing tests, stale docs, design regressions, and user-work preservation.
---

# Final Diff Review

## Definition

Read the exact final diff before delivery. Confirm every changed line belongs to the feature, has been verified, and does not hide accidental or unrelated work.

## Questions To Ask

- Which files changed, and why?
- Are any changes unrelated to the feature?
- Are there secrets, local config, generated artifacts, or debug code?
- Do tests and docs match the final behavior?
- Are user changes preserved and excluded from the commit if unrelated?

## Existing Project Comparison

- Compare the final diff against `FEATURE_DELIVERY.md`, tests, docs, and known project rules.
- Check deleted files, migrations, public APIs, dependency changes, and lockfiles with extra care.
- Verify the diff keeps naming, formatting, and architecture consistent with nearby code.

## Suggestive Plan

1. Inspect changed-file summary.
2. Read the full diff for files in scope.
3. Classify each change as feature, test, doc, generated, unrelated, or risky.
4. Fix or exclude accidental changes.
5. Record the final diff review in `FEATURE_DELIVERY.md`.

## Example

Before committing invoice resend, confirm route, service, tests, and docs changed; exclude a local `.env` edit and an unrelated formatting pass.

## Vocabulary

- Diff: exact changed lines compared with the base version.
- Unrelated change: edit not needed for the feature outcome.
- Generated artifact: tool-produced file that may not belong in source control.
- Delivery risk: issue that could break users or make maintenance harder.

## Expected Outcome

Produce a reviewed final diff with only intended changes, no secrets or accidental artifacts, known risks documented, and commit-ready files identified.
