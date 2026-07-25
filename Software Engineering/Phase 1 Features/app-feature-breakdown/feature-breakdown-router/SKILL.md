---
name: feature-breakdown-router
description: Automatically invoke the Phase 1 Features breakdown skills one by one by exact skill name, compare against the project when available, and create or continuously update FEATURE_MAP.md as the comprehensive outcome-to-build-plan document. Use when the user wants one router skill to cover everything needed to achieve the app outcome and keep the feature plan current as changes happen.
---

# Feature Breakdown Router

## Definition

Act as the single entry point for Phase 1 Features: break the app outcome into features. When invoked, do not summarize the workflow from memory and do not skip directly to a backlog. Invoke each named skill below, step by step, in the exact order shown. Use the output of each skill to create or update `FEATURE_MAP.md`.

`FEATURE_MAP.md` is the comprehensive project document for achieving the app outcome. It must explain the outcome, users, journeys, actions, rules, failures, feature groups, priorities, vertical slices, and ordered implementation plan. Coding agents should consult it before building features and update it whenever feature decisions change during the project.

## Required Output Document

- Create or update exactly this file at the repository or workspace root: `FEATURE_MAP.md`.
- Write it as a durable, comprehensive planning document for coding agents.
- Cover all things needed to achieve the outcome: who the app serves, what journeys matter, what actions exist, what features are needed, what rules and failure cases must be handled, how features group together, what order to build in, and what vertical slices prove progress.
- Include a clear feature map and an ordered list of small features to build.
- Compare against the existing project when files are available.
- Use `TBD` plus a precise question when a project fact is unknown.
- If `FEATURE_MAP.md` already exists, preserve correct decisions, update stale decisions, and append or revise sections affected by new project changes.
- If a project decision changes in the middle of the work, immediately update the affected part of `FEATURE_MAP.md` before continuing implementation planning.

## Exact Skill Invocation Flow

The user should only need to invoke `$feature-breakdown-router`. This router is responsible for invoking the following skills explicitly, one by one, by exact skill name.

1. Invoke `$outcome-definition`.
   - Write or update the `Outcome` section.
   - Define the app outcome, success signals, non-goals, assumptions, and open questions.
2. Invoke `$user-identification`.
   - Write or update the `Users` section.
   - Identify primary, secondary, supporting, and external users or systems.
3. Invoke `$user-journey-mapping`.
   - Write or update the `User Journeys` section.
   - Map trigger-to-outcome paths and important state changes.
4. Invoke `$journey-to-action-breakdown`.
   - Write or update the `Journey Actions` section.
   - Break journeys into user actions, system actions, preconditions, and postconditions.
5. Invoke `$action-to-feature-breakdown`.
   - Write or update the `Feature List` section.
   - Convert actions into small user-visible features with acceptance signals.
6. Invoke `$business-rule-discovery`.
   - Write or update the `Business Rules` section.
   - Discover invariants, policies, calculations, permissions, and lifecycle rules.
7. Invoke `$failure-case-discovery`.
   - Write or update the `Failure Cases` section.
   - Discover invalid states, recoverable failures, edge cases, and simplification opportunities.
8. Invoke `$feature-grouping`.
   - Write or update the `Feature Groups` section.
   - Group features by outcome, journey, domain knowledge, and likely owner module.
9. Invoke `$feature-prioritization`.
   - Write or update the `Priority Rationale` and `Ordered Build Plan` sections.
   - Prioritize by outcome value, learning value, dependency order, risk, and complexity.
10. Invoke `$vertical-slice-creation`.
   - Write or update the `Vertical Slices` section.
   - Create small end-to-end slices that include UI or API entry point, behavior, rules, data, and tests.
11. Invoke `$feature-map-document`.
   - Finalize `FEATURE_MAP.md`.
   - Confirm every section is present, comprehensive enough to guide implementation, and updated with any changes made during the flow.

## Document Structure

`FEATURE_MAP.md` must include:

- Read This First
- Outcome
- Users
- User journeys
- Journey actions
- Feature list
- Business rules
- Failure cases
- Feature groups
- Priority rationale
- Vertical slices
- Ordered build plan
- Existing project comparison
- Change log or update notes
- Open questions and TBDs

## Operating Rules

- Do not jump directly from outcome to feature list.
- Do not create large horizontal tasks such as "build database" or "build UI" unless they are supporting notes under a vertical slice.
- Prefer small features that validate abstractions and reduce unknowns.
- Keep feature names user-visible and domain-specific.
- Flag feature requests that increase complexity without improving the outcome.
- Keep `FEATURE_MAP.md` synchronized with project changes. When new requirements, users, journeys, rules, failures, priorities, or slices are discovered, update the document in the same change.
- Treat `FEATURE_MAP.md` as the source of truth for feature planning unless the user gives a newer explicit instruction.

## Expected Outcome

Produce and maintain `FEATURE_MAP.md` with a complete outcome-to-feature breakdown, existing-project comparison, comprehensive feature map, ordered small-feature build plan, vertical slices, and update notes for changes made along the way.
