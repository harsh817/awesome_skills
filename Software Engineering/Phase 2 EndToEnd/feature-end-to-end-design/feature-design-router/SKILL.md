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
- Open Questions And TBDs

## Operating Rules

- Keep the design feature-sized; split if it becomes a multi-feature project.
- Prefer deep modules, information hiding, simple interfaces, and obvious dependencies.
- Keep every layer aligned with the same acceptance criteria.
- Update `FEATURE_DESIGN.md` in the same change when design decisions change during implementation.
- Treat `FEATURE_DESIGN.md` as the feature design source of truth unless the user gives a newer explicit instruction.

## Expected Outcome

Produce and maintain `FEATURE_DESIGN.md` with a complete end-to-end feature plan across frontend, API, backend, database, errors, and tests.
