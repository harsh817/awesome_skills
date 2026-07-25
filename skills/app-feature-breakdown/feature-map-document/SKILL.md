---
name: feature-map-document
description: Create or update a canonical FEATURE_MAP.md from outcome, users, journeys, actions, rules, failures, groups, priorities, and vertical slices. Use when the feature discovery flow needs a durable document for implementation planning.
---

# Feature Map Document

## Definition

Synthesize the feature breakdown into a durable Markdown document named `FEATURE_MAP.md`. This document tells coding agents what small features to build, in what order, and why.

## Questions To Ask

- What outcome and users does this map serve?
- Which journeys and actions are included?
- Which features are grouped and prioritized?
- Which rules and failure cases must be handled?
- Which vertical slices should be built first?

## Existing Project Comparison

- If `FEATURE_MAP.md` exists, preserve valid decisions and update stale ones.
- Compare the feature map with README, issues, tests, routes, UI, and existing docs.
- Flag implementation already present, missing, duplicated, or out of order.
- Add `TBD` for unknowns instead of inventing project facts.

## Suggestive Plan

1. Create `FEATURE_MAP.md` at the repository or workspace root.
2. Add sections for outcome, users, journeys, actions, features, rules, failures, groups, priorities, and vertical slices.
3. Include a build order table.
4. Include open questions.
5. Keep it concise enough for agents to read before implementation.

## Example

Build order table columns: order, feature, user value, owner, dependencies, rules, failure cases, vertical slice, verification.

## Vocabulary

- Feature map: structured view of outcome-to-feature decisions.
- Build order: recommended sequence of implementation.
- Open question: decision needed before safe implementation.
- Durable document: project reference meant to survive beyond one chat.
- Source of truth: document future agents should consult first.

## Expected Outcome

Produce or update `FEATURE_MAP.md` with a clear feature map, ordered build list, vertical slices, and unresolved questions.
