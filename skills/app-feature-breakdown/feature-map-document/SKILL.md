---
name: feature-map-document
description: Create, update, and maintain the canonical FEATURE_MAP.md from outcome, users, journeys, actions, rules, failures, groups, priorities, and vertical slices. Use when the feature discovery flow needs a comprehensive document that coding agents read before implementation and update whenever feature decisions change.
---

# Feature Map Document

## Definition

Synthesize the feature breakdown into a durable Markdown document named `FEATURE_MAP.md`. This document tells coding agents what outcome they are trying to achieve, what small features to build, in what order, what rules and failures matter, and why.

`FEATURE_MAP.md` must remain current. When requirements, journeys, rules, feature priority, vertical slices, or implementation discoveries change, update the document in the same project change.

## Questions To Ask

- What outcome and users does this map serve?
- Which journeys and actions are included?
- Which features are grouped and prioritized?
- Which rules and failure cases must be handled?
- Which vertical slices should be built first?
- What changed since the last version of `FEATURE_MAP.md`?
- Which sections must be updated because of that change?

## Existing Project Comparison

- If `FEATURE_MAP.md` exists, preserve valid decisions and update stale ones.
- Compare the feature map with README, issues, tests, routes, UI, and existing docs.
- Flag implementation already present, missing, duplicated, or out of order.
- Add `TBD` for unknowns instead of inventing project facts.
- When code or project docs contradict `FEATURE_MAP.md`, report the conflict and update the document only when the correct decision is clear.

## Suggestive Plan

1. Create or update `FEATURE_MAP.md` at the repository or workspace root.
2. Add a `Read This First` section that says coding agents must read the document before building features and update it when project decisions change.
3. Add sections for outcome, users, journeys, actions, features, rules, failures, groups, priorities, and vertical slices.
4. Add an existing-project comparison.
5. Add an ordered build plan.
6. Add update notes for decisions changed during the current pass.
7. Add open questions.

## Example

Build order table columns: order, feature, user value, owner, dependencies, rules, failure cases, vertical slice, verification.

Update note example: "Changed priority of staff confirmation after discovering appointment requests cannot complete without manual approval."

## Vocabulary

- Feature map: structured view of outcome-to-feature decisions.
- Build order: recommended sequence of implementation.
- Open question: decision needed before safe implementation.
- Durable document: project reference meant to survive beyond one chat.
- Source of truth: document future agents should consult first.
- Update note: short record of a planning decision changed during discovery or implementation.

## Expected Outcome

Produce or update `FEATURE_MAP.md` with a comprehensive feature map, ordered build list, vertical slices, existing-project comparison, update notes, and unresolved questions.
