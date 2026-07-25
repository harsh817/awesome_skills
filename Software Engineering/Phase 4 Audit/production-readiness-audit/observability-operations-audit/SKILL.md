---
name: observability-operations-audit
description: Audit observability and operations readiness before production. Use when checking logs, metrics, traces, dashboards, alerts, health checks, runbooks, ownership, on-call readiness, and operational evidence.
---

# Observability And Operations Audit

## Definition

Confirm the team can see, diagnose, and operate the system in production. A release is not ready if failures will be invisible or ownerless.

## Questions To Ask

- What logs, metrics, traces, and health checks prove the system is healthy?
- Which dashboards and alerts cover production-critical paths?
- Who owns each service, job, queue, and dependency?
- What runbooks explain common incidents and recovery steps?
- What operational gaps would slow response?

## Existing Project Comparison

- Inspect logging calls, metric names, tracing, health endpoints, dashboards, alert config, runbooks, ownership docs, and error reporting.
- Compare observability coverage against must-have journeys, dependencies, and failure modes.
- Check that sensitive data is not exposed in logs or telemetry.

## Suggestive Plan

1. Map critical journeys and operational signals.
2. Inspect logs, metrics, traces, health checks, dashboards, and alerts.
3. Verify runbooks and ownership are discoverable.
4. Identify invisible failures and noisy or missing alerts.
5. Update `PRODUCTION_READINESS.md`.

## Example

For invoice sending, confirm metrics for send success and failure, logs with invoice IDs but no private data, alert on queue failure, and a resend runbook.

## Vocabulary

- Observability: ability to understand system state from outputs.
- Health check: endpoint or probe indicating service readiness or liveness.
- Runbook: operational guide for diagnosing and fixing incidents.
- Ownership: accountable person or team for a production area.

## Expected Outcome

Produce an operations audit with observability evidence, alert and dashboard coverage, runbook status, ownership, blockers, and accepted risks.
