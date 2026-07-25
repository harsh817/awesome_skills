---
name: feature-breakdown-router
description: Automatically invoke the Group 1 feature-breakdown skills one by one, compare against the project when available, and create or update FEATURE_MAP.md with a clear feature map and ordered small features to build. Use when the user wants one skill to route the full outcome-to-feature workflow.
---

# Feature Breakdown Router

## Definition

Act as the single entry point for Group 1: Break the app outcome into features. When invoked, call each named skill below in order and synthesize the results into `FEATURE_MAP.md`.

## Required Output

- Create or update `FEATURE_MAP.md` at the repository or workspace root.
- Write it as a durable planning document for coding agents.
- Include a clear feature map and an ordered list of small features to build.
- Compare against the existing project when files are available.
- Use `TBD` plus a precise question when a project fact is unknown.

## Exact Skill Invocation Flow

1. Invoke `$outcome-definition`.
2. Invoke `$user-identification`.
3. Invoke `$user-journey-mapping`.
4. Invoke `$journey-to-action-breakdown`.
5. Invoke `$action-to-feature-breakdown`.
6. Invoke `$business-rule-discovery`.
7. Invoke `$failure-case-discovery`.
8. Invoke `$feature-grouping`.
9. Invoke `$feature-prioritization`.
10. Invoke `$vertical-slice-creation`.
11. Invoke `$feature-map-document`.

## Document Structure

`FEATURE_MAP.md` must include:

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
- Open questions and TBDs

## Operating Rules

- Do not jump directly from outcome to feature list.
- Do not create large horizontal tasks such as "build database" or "build UI" unless they are supporting notes under a vertical slice.
- Prefer small features that validate abstractions and reduce unknowns.
- Keep feature names user-visible and domain-specific.
- Flag feature requests that increase complexity without improving the outcome.

## Expected Outcome

Produce `FEATURE_MAP.md` with a complete outcome-to-feature breakdown and an ordered, small-feature build plan ready for implementation.
