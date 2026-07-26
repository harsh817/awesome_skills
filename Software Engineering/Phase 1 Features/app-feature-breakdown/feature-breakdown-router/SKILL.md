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

## Visible Routing Protocol

When this router is invoked, the agent must make the routing visible to the user. Do not silently blend phases together.

Before doing feature breakdown work:

1. Create a visible checklist with all 11 subskills in order.
2. Mark only the current subskill as `in_progress`.
3. Announce the current subskill by exact name, for example: `Invoking $outcome-definition`.
4. Read that subskill's `SKILL.md` completely before acting on that phase.
5. Perform only the work that belongs to that phase.
6. Update the matching section in `FEATURE_MAP.md`.
7. Mark the subskill complete before moving to the next one.

Each phase must produce an observable artifact:

- A `FEATURE_MAP.md` section update, or
- A user, journey, action, feature, rule, failure case, priority, vertical slice, or build-plan decision, or
- A short explicit note that no change was needed and why.

If breakdown work has already happened before this router is invoked, still run the full visible sequence. In that case, use early phases to inspect and reconcile existing feature-map decisions instead of pretending they already happened.

Do not jump from outcome directly to feature list, from feature list directly to build order, or from planning directly to implementation without visibly completing the intervening subskills.

## Phase Work And Handoff Protocol

Router phases must do real work. Naming or reading a subskill is not enough to complete a phase.

For every subskill phase:

1. Read the latest `Routing Log` entry in `FEATURE_MAP.md`, if one exists.
2. Treat that entry as the incoming handoff from the previous skill.
3. Inspect the project, requirements, or existing document sections needed for this phase.
4. Produce phase output: observations, decisions, questions, changed feature-map content, or an explicit "no change needed" note backed by evidence.
5. Update the matching `FEATURE_MAP.md` section before moving on.
6. Add a new `Routing Log` handoff entry for the next skill.
7. Mark the phase with exactly one status: `done`, `needs_user_answer`, `needs_fix`, `deferred`, or `blocked`.

Use this handoff format:

```md
### $current-skill -> $next-skill
Status: done | needs_user_answer | needs_fix | deferred | blocked
Work completed:
- ...
Evidence or files checked:
- ...
Questions or TBDs:
- ...
Next skill focus:
- ...
```

The next skill must consume the previous handoff before doing its own work. If a phase has questions that block safe progress, ask the user or write a precise `TBD` in `FEATURE_MAP.md`. If a phase has only nonblocking questions, record them and continue with the safest stated assumption.

No phase may complete with only "invoked skill" or "read skill". It must leave an artifact in `FEATURE_MAP.md`, the routing log, or both.

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
- Routing Log
- Open questions and TBDs

## Operating Rules

- Do not jump directly from outcome to feature list.
- Do not create large horizontal tasks such as "build database" or "build UI" unless they are supporting notes under a vertical slice.
- Prefer small features that validate abstractions and reduce unknowns.
- Keep feature names user-visible and domain-specific.
- Flag feature requests that increase complexity without improving the outcome.
- Keep `FEATURE_MAP.md` synchronized with project changes. When new requirements, users, journeys, rules, failures, priorities, or slices are discovered, update the document in the same change.
- Treat `FEATURE_MAP.md` as the source of truth for feature planning unless the user gives a newer explicit instruction.
- Do not finish the router until all subskills are visibly complete in the checklist and represented in `FEATURE_MAP.md`.
- Do not mark a subskill complete until it has written its phase output and handoff entry.
- If a later phase changes an earlier decision, route back to the affected earlier subskill, update its section, then continue forward again.
- If a phase uncovers implementation work, record it as a feature, vertical slice, or follow-up rather than doing unplanned implementation inside this router.
- In the final response, list each invoked subskill and the concrete result it produced.

## Expected Outcome

Produce and maintain `FEATURE_MAP.md` with a complete outcome-to-feature breakdown, existing-project comparison, comprehensive feature map, ordered small-feature build plan, vertical slices, and update notes for changes made along the way.
