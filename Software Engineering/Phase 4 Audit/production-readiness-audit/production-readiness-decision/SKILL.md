---
name: production-readiness-decision
description: Make the final production readiness decision from audit evidence. Use when combining requirements, architecture, code quality, tests, security, data, performance, reliability, deployment, observability, and adversarial findings into READY, READY WITH ACCEPTED RISKS, or NOT READY.
---

# Production Readiness Decision

## Definition

Convert audit evidence into one release decision. The decision must be evidence-backed, explicit about accepted risks, and clear about blockers.

## Questions To Ask

- Which findings are blockers?
- Which risks have explicit owner acceptance?
- Which unknowns remain and are they acceptable?
- What evidence proves the release can be operated safely?
- Who owns the final production decision?

## Existing Project Comparison

- Compare every audit section in `PRODUCTION_READINESS.md` against current code, tests, docs, and operational evidence.
- Check that accepted risks have owners and review dates.
- Do not downgrade blockers to accepted risks without explicit accountable approval.

## Suggestive Plan

1. Summarize each audit area as pass, pass with risk, fail, or unknown.
2. List blockers and determine whether any prevent release.
3. List accepted risks with owner, impact, mitigation, and review date.
4. Choose exactly one decision value.
5. Update `PRODUCTION_READINESS.md`.

## Example

Choose `READY WITH ACCEPTED RISKS` when all must-have journeys pass, security blockers are fixed, deployment rollback is proven, and the product owner accepts a measured performance risk with a review date.

## Vocabulary

- Ready: evidence shows production release is acceptable.
- Ready with accepted risks: release is acceptable only with explicit risk ownership.
- Not ready: one or more blockers or unacceptable unknowns prevent release.
- Decision owner: person or team accountable for release approval.

## Expected Outcome

Produce the final readiness decision as exactly `READY`, `READY WITH ACCEPTED RISKS`, or `NOT READY`, with rationale, blockers, accepted risks, owners, and follow-up.
