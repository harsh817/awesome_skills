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

## Visible Routing Protocol

When this router is invoked, the agent must make the routing visible to the user. Do not silently blend phases together.

Before doing feature work:

1. Create a visible checklist with all 12 subskills in order.
2. Mark only the current subskill as `in_progress`.
3. Announce the current subskill by exact name, for example: `Invoking $repository-inspection`.
4. Read that subskill's `SKILL.md` completely before acting on that phase.
5. Perform only the work that belongs to that phase.
6. Update the matching section in `FEATURE_DELIVERY.md`.
7. Mark the subskill complete before moving to the next one.

Each phase must produce an observable artifact:

- A `FEATURE_DELIVERY.md` section update, or
- A code/test/doc change, or
- A verification command result, or
- A short explicit note that no change was needed and why.

If implementation work has already happened before this router is invoked, still run the full visible sequence. In that case, use early phases to inspect and reconcile existing work instead of pretending they already happened.

Do not jump from planning directly to coding, from coding directly to commit, or from verification directly to push without visibly completing the intervening subskills.

## Phase Work And Handoff Protocol

Router phases must do real work. Naming or reading a subskill is not enough to complete a phase.

For every subskill phase:

1. Read the latest `Routing Log` entry in `FEATURE_DELIVERY.md`, if one exists.
2. Treat that entry as the incoming handoff from the previous skill.
3. Inspect the project, current diff, verification evidence, or delivery document sections needed for this phase.
4. Produce phase output: observations, implementation edits, verification results, review findings, fixes, tests, documentation updates, commit decisions, or an explicit "no change needed" note backed by evidence.
5. Update the matching `FEATURE_DELIVERY.md` section before moving on.
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

The next skill must consume the previous handoff before doing its own work. If a phase has questions that block safe progress, ask the user or write a precise `TBD` in `FEATURE_DELIVERY.md`. If a phase has only nonblocking questions, record them and continue with the safest stated assumption.

No phase may complete with only "invoked skill" or "read skill". It must leave an artifact in `FEATURE_DELIVERY.md`, the routing log, code, tests, docs, verification output, or a reviewed commit decision.

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
- Routing Log
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
- Do not enter `$commit-and-push` until all previous subskills are visibly complete in the checklist and represented in `FEATURE_DELIVERY.md`.
- Do not mark a subskill complete until it has written its phase output and handoff entry.
- If a phase uncovers a defect, route back through `$strategic-fixing-refactoring`, then repeat `$run-behavior-verification`, `$plan-to-code-comparison`, `$design-complexity-review`, `$test-implementation`, `$documentation-review`, and `$final-diff-review` as needed before committing.
- If a phase uncovers unrelated work, record it as excluded from scope and do not stage or commit it.
- In the final response, list each invoked subskill and the concrete result it produced.

## Example

For "add invoice resend", inspect billing ownership, plan one admin-to-service slice, implement the route and service change, verify email behavior, compare against the feature design, review complexity, add tests and docs, then commit and push the focused diff.

## Vocabulary

- Ship: complete the full loop from inspected plan to pushed feature.
- Delivery document: durable record of implementation decisions and verification.
- Strategic slice: small feature change that works while improving or preserving design.
- Commit-ready: final state after verification, tests, docs, and diff review.

## Expected Outcome

Produce one working, tested, understandable feature pushed to GitHub, with `FEATURE_DELIVERY.md` documenting the inspection, plan, implementation, review, tests, docs, final diff, commit, and push result.
