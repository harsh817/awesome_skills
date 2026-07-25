---
name: reliability-failure-audit
description: Audit reliability and failure readiness before production. Use when testing dependency failures, retries, timeouts, duplicate requests, concurrency, partial failures, idempotency, recovery behavior, and error handling.
---

# Reliability And Failure Audit

## Definition

Confirm the system behaves predictably when things go wrong. Production readiness requires recovery paths, not only happy paths.

## Questions To Ask

- What dependencies can fail, slow down, or return partial results?
- Which operations must be idempotent?
- What retries, timeouts, and cancellation rules exist?
- What concurrent or duplicate requests can happen?
- How does the system recover after partial failure?

## Existing Project Comparison

- Inspect queues, jobs, webhooks, network calls, transactions, locks, idempotency keys, retry policies, and error handling.
- Compare failure behavior against requirements and operational runbooks.
- Look for avoidable special cases and errors that can be designed out of existence.

## Suggestive Plan

1. Map production dependencies and failure modes.
2. Inspect retry, timeout, idempotency, and concurrency handling.
3. Run or review failure-injection, edge-case, and recovery tests.
4. Classify missing recovery behavior as blocker or accepted risk.
5. Update `PRODUCTION_READINESS.md`.

## Example

For payment webhooks, verify duplicate events do not double-charge, provider timeouts retry safely, and partial database writes recover or roll back.

## Vocabulary

- Idempotency: repeated request has the same effect as one request.
- Partial failure: some steps succeed while others fail.
- Recovery path: behavior that restores a safe state after failure.
- Timeout: maximum wait before abandoning or retrying work.

## Expected Outcome

Produce a reliability audit with dependency risks, failure-mode evidence, recovery gaps, blockers, accepted risks, and required fixes.
