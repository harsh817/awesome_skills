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
- Change Log
- Open Questions And TBDs

Use `references/production-readiness-template.md` when creating the document from scratch.

## Operating Rules

- Do not declare readiness without evidence.
- Separate must-fix blockers from accepted risks and informational findings.
- Prefer measured facts over guesses, especially for performance, capacity, reliability, and deployment.
- Update `PRODUCTION_READINESS.md` whenever fixes, evidence, risk acceptance, or project behavior changes.
- Keep the final decision to exactly one of: `READY`, `READY WITH ACCEPTED RISKS`, or `NOT READY`.

## Example

For a billing release, audit invoice creation, approval, payment, and reporting journeys; inspect module boundaries and tests; check auth, migrations, performance measurements, rollback, alerts, and runbooks; then decide whether production can proceed.

## Vocabulary

- Readiness: evidence-backed confidence that production use is acceptable.
- Accepted risk: known risk explicitly approved by the accountable owner.
- Blocker: issue that prevents production release.
- Evidence: test result, measurement, code inspection, deploy result, log, dashboard, or documented operational proof.

## Expected Outcome

Produce and maintain `PRODUCTION_READINESS.md` with complete audit evidence and one final decision: `READY`, `READY WITH ACCEPTED RISKS`, or `NOT READY`.
