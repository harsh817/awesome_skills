---
name: performance-capacity-audit
description: Audit performance and capacity before production. Use when measuring latency, throughput, resource use, database queries, critical paths, expected load, and capacity risks with evidence rather than guesses.
---

# Performance And Capacity Audit

## Definition

Decide whether the system can handle expected production load using measurements. Performance conclusions should be based on observed evidence, not intuition.

## Questions To Ask

- What are the expected and peak production loads?
- Which user journeys or jobs are performance-critical?
- What latency, throughput, memory, CPU, queue, and database query evidence exists?
- What performance budget or SLO applies?
- Which measurements are missing?

## Existing Project Comparison

- Inspect benchmarks, load tests, query plans, logs, metrics, caching, batching, queues, and resource limits.
- Compare measurements against expected traffic and critical paths.
- Check whether optimizations add complexity and whether that complexity is justified by measured benefit.

## Suggestive Plan

1. Define critical paths and expected load.
2. Gather current measurements from tests, logs, dashboards, or benchmarks.
3. Inspect database and external dependency behavior.
4. Identify bottlenecks, capacity limits, and missing evidence.
5. Update `PRODUCTION_READINESS.md`.

## Example

For invoice export, measure export time for realistic account sizes, database query count, memory use, queue duration, and timeout behavior.

## Vocabulary

- Critical path: execution path most important to user-visible performance.
- Throughput: work completed per unit of time.
- Latency: time for one request or workflow to complete.
- Performance budget: maximum acceptable resource or time cost.

## Expected Outcome

Produce a performance audit with measured evidence, expected load, bottlenecks, capacity limits, missing measurements, blockers, and accepted risks.
