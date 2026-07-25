---
name: full-system-adversarial-review
description: Run a full-system adversarial production review. Use when actively searching for hidden assumptions, unknown dependencies, missing errors, unsafe interactions, cross-area failures, and readiness blind spots after focused audits.
---

# Full-System Adversarial Review

## Definition

Actively look for what the focused audits missed. Search for interactions between requirements, architecture, data, security, reliability, deployment, and operations that create hidden production risk.

## Questions To Ask

- What assumption would make the release unsafe if false?
- What dependency or state transition is not obvious from the code?
- What happens when two individually safe features interact?
- Which errors are missing, masked incorrectly, or handled by the wrong layer?
- What would an independent reviewer challenge?

## Existing Project Comparison

- Re-read audit findings, delivery docs, high-risk code paths, configs, migrations, and operational docs.
- Look for unknown unknowns, cross-module information leakage, edge cases, privilege paths, partial failures, and rollout interactions.
- Use independent review passes when feasible, keeping each pass focused on fresh evidence.

## Suggestive Plan

1. List assumptions discovered across prior audits.
2. Challenge each assumption with code, tests, docs, or operational evidence.
3. Search for cross-area interactions and hidden dependencies.
4. Convert credible risks into blockers, accepted risks, or follow-ups.
5. Update `PRODUCTION_READINESS.md`.

## Example

Challenge whether invoice retry, payment webhook idempotency, tenant permissions, and rollback migration order still work when events arrive during deployment.

## Vocabulary

- Hidden assumption: belief not backed by evidence.
- Unknown unknown: risk that is hard to notice from current context.
- Unsafe interaction: combination of safe parts that creates risk together.
- Adversarial review: review designed to falsify readiness, not confirm it.

## Expected Outcome

Produce an adversarial review with challenged assumptions, hidden dependencies, unsafe interactions, evidence gaps, blockers, accepted risks, and follow-ups.
