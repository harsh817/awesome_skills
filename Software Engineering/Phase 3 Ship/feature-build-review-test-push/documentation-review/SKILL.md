---
name: documentation-review
description: Review and update documentation for an implemented feature. Use when checking README files, API docs, comments, design documents, changelogs, examples, and delivery notes after code changes.
---

# Documentation Review

## Definition

Keep documentation aligned with the code and useful for future developers. Document design intent and nonobvious behavior, not code that already explains itself.

## Questions To Ask

- Did the feature change public behavior, APIs, setup, configuration, or workflows?
- Which docs or comments will become stale if not updated?
- Are interface comments clear without exposing implementation details?
- Are nonobvious decisions recorded near the code or in the right design document?
- Does `FEATURE_DELIVERY.md` reflect the final implementation?

## Existing Project Comparison

- Follow existing documentation locations, tone, and naming.
- Compare current docs against changed routes, commands, config, environment variables, and user workflows.
- Check comments for repetition, missing intent, and stale design claims.

## Suggestive Plan

1. Identify docs touched by public or developer-facing behavior.
2. Update durable docs and examples.
3. Add or adjust comments only for nonobvious intent, invariants, or interface contracts.
4. Remove or revise stale documentation.
5. Record doc decisions and gaps in `FEATURE_DELIVERY.md`.

## Example

If invoice resend adds an admin API route, update API docs and mention the permission rule; skip a comment that merely repeats the route name.

## Vocabulary

- Interface documentation: contract needed by callers.
- Implementation comment: note explaining nonobvious internal intent.
- Stale documentation: docs that contradict current behavior.
- Design intent: reason a structure or tradeoff exists.

## Expected Outcome

Produce updated documentation and comments where needed, with stale docs fixed and documentation gaps recorded.
