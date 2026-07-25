---
name: feature-ship-router
description: Automatically invoke the Phase 3 Ship skills one by one by exact skill name, compare the implementation against the project and feature plan, create or continuously update FEATURE_DELIVERY.md, then commit and push one working tested understandable feature when requested.
---

# Feature Ship Router

## Definition

Act as the single entry point for Phase 3 Ship: build, review, test, and push one feature. Invoke each named skill below in order. Use their outputs to create and maintain `FEATURE_DELIVERY.md`.

`FEATURE_DELIVERY.md` is the delivery document for the feature. It records what was inspected, what was planned, what changed, how behavior was verified, how the code compares to the plan, what tests and docs were updated, what diff was reviewed, and what was committed and pushed.

## Questions To Ask

- What feature is being built, and which acceptance criteria define done?
- Which existing project documents should guide the work?
- Should the feature be pushed after commit, or only prepared locally?
- What branch, remote, issue, or pull request context matters?
- Are there user changes that must be preserved outside this feature?

## Required Output Document

- Create or update exactly this file at the repository or workspace root: `FEATURE_DELIVERY.md`.
- Read `AGENT_GUARDRAILS.md`, `FEATURE_MAP.md`, and `FEATURE_DESIGN.md` when available.
- Preserve correct prior decisions, update stale parts, and add update notes whenever the implementation changes the plan.
- Use `TBD` plus a precise question when a project fact is unknown.
- Keep the document comprehensive enough that another coding agent can understand what was built and why.

## Existing Project Comparison

- Compare the feature against `AGENT_GUARDRAILS.md`, `FEATURE_MAP.md`, `FEATURE_DESIGN.md`, and current repository files when available.
- Reconcile implementation facts with the plan before committing.
- Check for tactical complexity, stale docs, missing tests, unrelated changes, and broken project conventions.

## Suggestive Plan

1. Inspect the repository and current git state.
2. Plan the smallest strategic implementation slice.
3. Write precise coding-agent instructions and implement the slice.
4. Verify behavior, compare plan to code, review complexity, and fix issues.
5. Add tests, update docs, review the final diff, commit, and push when allowed.

## Exact Skill Invocation Flow

The user should only need to invoke `$feature-ship-router`. This router is responsible for invoking these skills explicitly, one by one, by exact skill name.

1. Invoke `$repository-inspection`.
   - Write or update `Repository Inspection`.
2. Invoke `$implementation-planning`.
   - Write or update `Implementation Plan`.
3. Invoke `$coding-agent-instructions`.
   - Write or update `Coding Agent Instructions`.
4. Invoke `$small-slice-implementation`.
   - Write or update `Implementation Notes`.
5. Invoke `$run-behavior-verification`.
   - Write or update `Behavior Verification`.
6. Invoke `$plan-to-code-comparison`.
   - Write or update `Plan To Code Comparison`.
7. Invoke `$design-complexity-review`.
   - Write or update `Design And Complexity Review`.
8. Invoke `$strategic-fixing-refactoring`.
   - Write or update `Fixes And Refactors`.
9. Invoke `$test-implementation`.
   - Write or update `Test Implementation`.
10. Invoke `$documentation-review`.
   - Write or update `Documentation Review`.
11. Invoke `$final-diff-review`.
   - Write or update `Final Diff Review`.
12. Invoke `$commit-and-push`.
   - Write or update `Commit And Push`.

## Document Structure

`FEATURE_DELIVERY.md` must include:

- Read This First
- Feature Target
- Repository Inspection
- Implementation Plan
- Coding Agent Instructions
- Implementation Notes
- Behavior Verification
- Plan To Code Comparison
- Design And Complexity Review
- Fixes And Refactors
- Test Implementation
- Documentation Review
- Final Diff Review
- Commit And Push
- Existing Project Comparison
- Change Log
- Open Questions And TBDs

Use `references/feature-delivery-template.md` when creating the document from scratch.

## Operating Rules

- Keep the feature small enough to finish, verify, and push as one coherent change.
- Compare against the existing project before planning and after coding.
- Prefer strategic programming: make small design investments while implementing rather than layering tactical patches.
- Keep complexity moving downward into owner modules behind stable interfaces.
- Update `FEATURE_DELIVERY.md` whenever implementation facts diverge from the plan.
- Do not commit unrelated user changes.
- Push only after verification, final diff review, and an explicit user request or project rule allowing push.

## Example

For "add invoice resend", inspect billing ownership, plan one admin-to-service slice, implement the route and service change, verify email behavior, compare against the feature design, review complexity, add tests and docs, then commit and push the focused diff.

## Vocabulary

- Ship: complete the full loop from inspected plan to pushed feature.
- Delivery document: durable record of implementation decisions and verification.
- Strategic slice: small feature change that works while improving or preserving design.
- Commit-ready: final state after verification, tests, docs, and diff review.

## Expected Outcome

Produce one working, tested, understandable feature pushed to GitHub, with `FEATURE_DELIVERY.md` documenting the inspection, plan, implementation, review, tests, docs, final diff, commit, and push result.
