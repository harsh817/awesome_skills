---
name: production-readiness-router
description: Automatically invoke the Phase 4 Audit production-readiness skills one by one by exact skill name, compare evidence against the project, create or continuously update PRODUCTION_READINESS.md, and produce a final READY, READY WITH ACCEPTED RISKS, or NOT READY decision.
---

# Production Readiness Router

## Definition

Act as the single entry point for Phase 4 Audit: decide whether a product, feature set, release, or system is ready for production. Invoke each named audit skill below in order and synthesize the evidence into `PRODUCTION_READINESS.md`.

`PRODUCTION_READINESS.md` is the durable audit record. It must cover requirements, architecture, code quality, tests, security, data, performance, reliability, deployment, observability, adversarial review, and the final production decision.

## Questions To Ask

- What release, feature set, branch, environment, or service is being audited?
- What user journeys and acceptance conditions are must-have?
- What production environment, traffic level, data sensitivity, and compliance constraints matter?
- What evidence already exists in tests, dashboards, runbooks, deploy logs, or docs?
- Who can accept risks, and what risk level is unacceptable?

## Required Output Document

- Create or update exactly this file at the repository or workspace root: `PRODUCTION_READINESS.md`.
- Read `AGENT_GUARDRAILS.md`, `FEATURE_MAP.md`, `FEATURE_DESIGN.md`, and `FEATURE_DELIVERY.md` when available.
- Compare each audit area against current project files and operational evidence.
- Preserve correct prior decisions, update stale evidence, and add update notes whenever findings change.
- Use `TBD` plus a precise question when a required fact is unknown.

## Existing Project Comparison

- Inspect code, tests, docs, config, migrations, deployment files, monitoring, security boundaries, and git state.
- Use the book's design lens: reduce complexity, prefer deep modules, hide information, avoid pass-through layers, keep names precise, write useful comments, measure performance, and use tests to enable safe changes.
- Treat missing evidence as a readiness risk, not as proof of readiness.

## Suggestive Plan

1. Define the release scope and evidence sources.
2. Run each audit skill in order and update `PRODUCTION_READINESS.md`.
3. Mark each audit area pass, pass with risk, fail, or unknown.
4. Send blocking gaps back to the relevant implementation or fixing skill when appropriate.
5. Produce one final readiness decision with accepted risks and required follow-up.

## Exact Skill Invocation Flow

The user should only need to invoke `$production-readiness-router`. This router is responsible for invoking these skills explicitly, one by one, by exact skill name.

## Visible Routing Protocol

When this router is invoked, the agent must make the routing visible to the user. Do not silently blend audit phases together.

Before doing readiness audit work:

1. Create a visible checklist with all 12 audit subskills in order.
2. Mark only the current subskill as `in_progress`.
3. Announce the current subskill by exact name, for example: `Invoking $requirements-completeness-audit`.
4. Read that subskill's `SKILL.md` completely before acting on that phase.
5. Perform only the work that belongs to that audit phase.
6. Update the matching section in `PRODUCTION_READINESS.md`.
7. Mark the subskill complete before moving to the next one.

Each phase must produce an observable artifact:

- A `PRODUCTION_READINESS.md` section update, or
- An evidence-backed pass, pass-with-risk, fail, or unknown finding, or
- A blocker, accepted risk, measurement, command result, file reference, or operational-evidence note, or
- A short explicit note that no evidence was available and what remains unknown.

If audit work has already happened before this router is invoked, still run the full visible sequence. In that case, use early phases to inspect and reconcile existing readiness evidence instead of pretending they already happened.

Do not jump from requirements directly to final decision, from tests directly to security/deployment conclusions, or from audit findings directly to readiness without visibly completing the intervening subskills.

## Phase Work And Handoff Protocol

Router phases must do real work. Naming or reading a subskill is not enough to complete a phase.

For every audit phase:

1. Read the latest `Routing Log` entry in `PRODUCTION_READINESS.md`, if one exists.
2. Treat that entry as the incoming handoff from the previous skill.
3. Inspect the project, evidence sources, existing findings, or current audit section needed for this phase.
4. Produce phase output: observations, evidence-backed findings, blockers, accepted-risk candidates, questions, measurements, command results, or an explicit "no evidence available" note.
5. Update the matching `PRODUCTION_READINESS.md` section before moving on.
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

The next skill must consume the previous handoff before doing its own work. If a phase has questions that block a readiness decision, ask the user or write a precise `TBD` in `PRODUCTION_READINESS.md`. If a phase has only nonblocking questions, record them and continue with the safest stated assumption.

No phase may complete with only "invoked skill" or "read skill". It must leave an artifact in `PRODUCTION_READINESS.md`, the routing log, evidence output, blockers, accepted risks, or a documented readiness decision.

1. Invoke `$requirements-completeness-audit`.
   - Write or update `Requirements Completeness Audit`.
2. Invoke `$architecture-complexity-audit`.
   - Write or update `Architecture And Complexity Audit`.
3. Invoke `$code-quality-documentation-audit`.
   - Write or update `Code Quality And Documentation Audit`.
4. Invoke `$functional-regression-test-audit`.
   - Write or update `Functional And Regression Test Audit`.
5. Invoke `$security-readiness-audit`.
   - Write or update `Security Audit`.
6. Invoke `$data-migration-audit`.
   - Write or update `Data And Migration Audit`.
7. Invoke `$performance-capacity-audit`.
   - Write or update `Performance And Capacity Audit`.
8. Invoke `$reliability-failure-audit`.
   - Write or update `Reliability And Failure Audit`.
9. Invoke `$deployment-rollback-audit`.
   - Write or update `Deployment And Rollback Audit`.
10. Invoke `$observability-operations-audit`.
   - Write or update `Observability And Operations Audit`.
11. Invoke `$full-system-adversarial-review`.
   - Write or update `Full-System Adversarial Review`.
12. Invoke `$production-readiness-decision`.
   - Write or update `Production Readiness Decision`.

## Document Structure

`PRODUCTION_READINESS.md` must include:

- Read This First
- Release Scope
- Evidence Summary
- Requirements Completeness Audit
- Architecture And Complexity Audit
- Code Quality And Documentation Audit
- Functional And Regression Test Audit
- Security Audit
- Data And Migration Audit
- Performance And Capacity Audit
- Reliability And Failure Audit
- Deployment And Rollback Audit
- Observability And Operations Audit
- Full-System Adversarial Review
- Production Readiness Decision
- Accepted Risks
- Blockers
- Routing Log
- Change Log
- Open Questions And TBDs

Use `references/production-readiness-template.md` when creating the document from scratch.

## Operating Rules

- Do not declare readiness without evidence.
- Separate must-fix blockers from accepted risks and informational findings.
- Prefer measured facts over guesses, especially for performance, capacity, reliability, and deployment.
- Update `PRODUCTION_READINESS.md` whenever fixes, evidence, risk acceptance, or project behavior changes.
- Keep the final decision to exactly one of: `READY`, `READY WITH ACCEPTED RISKS`, or `NOT READY`.
- Do not enter `$production-readiness-decision` until all previous audit subskills are visibly complete in the checklist and represented in `PRODUCTION_READINESS.md`.
- Do not mark a subskill complete until it has written its phase output and handoff entry.
- If a phase uncovers a blocker that must be fixed before readiness can be decided, record it in `Blockers`, route the work back to the appropriate implementation/fixing skill when requested, and repeat affected audit phases after fixes.
- If a phase uncovers implementation work, record it as a blocker, accepted-risk candidate, or follow-up rather than doing unplanned implementation inside this router.
- In the final response, list each invoked subskill and the concrete result it produced.

## Example

For a billing release, audit invoice creation, approval, payment, and reporting journeys; inspect module boundaries and tests; check auth, migrations, performance measurements, rollback, alerts, and runbooks; then decide whether production can proceed.

## Vocabulary

- Readiness: evidence-backed confidence that production use is acceptable.
- Accepted risk: known risk explicitly approved by the accountable owner.
- Blocker: issue that prevents production release.
- Evidence: test result, measurement, code inspection, deploy result, log, dashboard, or documented operational proof.

## Expected Outcome

Produce and maintain `PRODUCTION_READINESS.md` with complete audit evidence and one final decision: `READY`, `READY WITH ACCEPTED RISKS`, or `NOT READY`.
