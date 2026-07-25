---
name: commit-and-push
description: Commit and push one completed feature after verification and final diff review. Use when preparing a focused git commit, preserving unrelated user changes, writing a clear message, pushing to GitHub, and recording the result.
---

# Commit And Push

## Definition

Publish one coherent feature change after it has been implemented, verified, reviewed, tested, and documented. Keep the commit focused and do not include unrelated work.

## Questions To Ask

- Has the user requested push, or do project rules allow it?
- Which changed files belong in this feature commit?
- What verification has passed, and what gaps remain?
- What commit message explains the feature or design reason?
- Which remote branch should receive the push?

## Existing Project Comparison

- Follow existing branch, commit message, and push conventions when discoverable.
- Compare staged files against final diff review and exclude unrelated user changes.
- Check remote configuration before pushing.

## Suggestive Plan

1. Confirm verification and final diff review are complete.
2. Stage only files belonging to the feature.
3. Write a clear commit message focused on outcome.
4. Push to the intended GitHub remote and branch.
5. Record commit hash, branch, remote, push result, and remaining gaps in `FEATURE_DELIVERY.md`.

## Example

Commit message: `Add invoice resend workflow`. The commit includes service, route, tests, docs, and `FEATURE_DELIVERY.md`, but excludes an unrelated local settings file.

## Vocabulary

- Commit scope: conceptual boundary of one commit.
- Staged files: files selected for the next commit.
- Remote branch: hosted branch receiving the push.
- Push result: confirmation, rejection, or required follow-up from the remote.

## Expected Outcome

Produce a focused commit pushed to GitHub, with commit details and push result recorded in `FEATURE_DELIVERY.md`.
