---
name: feature-design-router
description: Automatically invoke the Phase 2 EndToEnd feature-design skills one by one by exact skill name, compare against the project when available, and create or continuously update FEATURE_DESIGN.md as the comprehensive frontend/API/backend/database/test plan for one feature.
---

# Feature Design Router

## Definition

Act as the single entry point for Phase 2 EndToEnd: design one feature across frontend, API, backend, database, and tests. When invoked, do not jump directly to implementation. Invoke each named skill below in order and synthesize the result into `FEATURE_DESIGN.md`.

`FEATURE_DESIGN.md` is the comprehensive feature design document. Coding agents should read it before implementing the feature and update it whenever design decisions change during implementation.

## Required Output Document

- Create or update exactly this file at the repository or workspace root: `FEATURE_DESIGN.md`.
- Cover the feature outcome, scope, acceptance criteria, design alternatives, modules, interfaces, data model, backend logic, API contract, frontend flow, errors, and tests.
- Compare against existing project files, `FEATURE_MAP.md`, and `AGENT_GUARDRAILS.md` when available.
- If `FEATURE_DESIGN.md` already exists, preserve correct decisions, update stale decisions, and add update notes for changes made during the work.
- Use `TBD` plus a precise question when a project fact is unknown.

## Exact Skill Invocation Flow

The user should only need to invoke `$feature-design-router`. This router is responsible for invoking these skills explicitly, one by one, by exact skill name.

## Visible Routing Protocol

When this router is invoked, the agent must make the routing visible to the user. Do not silently blend phases together.

Before doing design work:

1. Create a visible checklist with all 12 subskills in order.
2. Mark only the current subskill as `in_progress`.
3. Announce the current subskill by exact name, for example: `Invoking $feature-outcome-definition`.
4. Read that subskill's `SKILL.md` completely before acting on that phase.
5. Perform only the work that belongs to that phase.
6. Update the matching section in `FEATURE_DESIGN.md`.
7. Mark the subskill complete before moving to the next one.

Each phase must produce an observable artifact:

- A `FEATURE_DESIGN.md` section update, or
- A design decision, acceptance criterion, interface, model, API, frontend flow, edge case, or test-plan change, or
- A short explicit note that no change was needed and why.

If design work has already happened before this router is invoked, still run the full visible sequence. In that case, use early phases to inspect and reconcile existing design decisions instead of pretending they already happened.

Do not jump from outcome directly to API/backend/frontend details, from design directly to implementation, or from one layer to another without visibly completing the intervening subskills.

## Phase Work And Handoff Protocol

Router phases must do real work. Naming or reading a subskill is not enough to complete a phase.

For every subskill phase:

1. Read the latest `Routing Log` entry in `FEATURE_DESIGN.md`, if one exists.
2. Treat that entry as the incoming handoff from the previous skill.
3. Inspect the project, requirements, or existing design sections needed for this phase.
4. Produce phase output: observations, design decisions, interfaces, model/API/frontend/test changes, questions, or an explicit "no change needed" note backed by evidence.
5. Update the matching `FEATURE_DESIGN.md` section before moving on.
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

The next skill must consume the previous handoff before doing its own work. If a phase has questions that block safe progress, ask the user or write a precise `TBD` in `FEATURE_DESIGN.md`. If a phase has only nonblocking questions, record them and continue with the safest stated assumption.

No phase may complete with only "invoked skill" or "read skill". It must leave an artifact in `FEATURE_DESIGN.md`, the routing log, or both.

1. Invoke `$feature-outcome-definition`.
   - Write or update `Feature Outcome`.
2. Invoke `$feature-scope-definition`.
   - Write or update `Feature Scope`.
3. Invoke `$acceptance-criteria-writing`.
   - Write or update `Acceptance Criteria`.
4. Invoke `$design-it-twice`.
   - Write or update `Design Alternatives`.
5. Invoke `$module-and-boundary-design`.
   - Write or update `Modules And Boundaries`.
6. Invoke `$interface-first-design`.
   - Write or update `Interfaces`.
7. Invoke `$data-model-design`.
   - Write or update `Data Model`.
8. Invoke `$backend-and-business-logic-design`.
   - Write or update `Backend And Business Logic`.
9. Invoke `$api-contract-design`.
   - Write or update `API Contract`.
10. Invoke `$frontend-flow-design`.
   - Write or update `Frontend Flow`.
11. Invoke `$error-and-edge-case-design`.
   - Write or update `Errors And Edge Cases`.
12. Invoke `$test-plan-design`.
   - Write or update `Test Plan`.

## Document Structure

`FEATURE_DESIGN.md` must include:

- Read This First
- Feature Outcome
- Feature Scope
- Acceptance Criteria
- Design Alternatives
- Selected Design
- Modules And Boundaries
- Interfaces
- Data Model
- Backend And Business Logic
- API Contract
- Frontend Flow
- Errors And Edge Cases
- Test Plan
- Existing Project Comparison
- Update Notes
- Routing Log
- Open Questions And TBDs

## Operating Rules

- Keep the design feature-sized; split if it becomes a multi-feature project.
- Prefer deep modules, information hiding, simple interfaces, and obvious dependencies.
- Keep every layer aligned with the same acceptance criteria.
- Update `FEATURE_DESIGN.md` in the same change when design decisions change during implementation.
- Treat `FEATURE_DESIGN.md` as the feature design source of truth unless the user gives a newer explicit instruction.
- Do not finish the router until all subskills are visibly complete in the checklist and represented in `FEATURE_DESIGN.md`.
- Do not mark a subskill complete until it has written its phase output and handoff entry.
- If a later phase changes an earlier decision, route back to the affected earlier subskill, update its section, then continue forward again.
- If a phase uncovers implementation work, record it as a design requirement or follow-up rather than doing unplanned implementation inside this router.
- In the final response, list each invoked subskill and the concrete result it produced.

## Expected Outcome

Produce and maintain `FEATURE_DESIGN.md` with a complete end-to-end feature plan across frontend, API, backend, database, errors, and tests.
