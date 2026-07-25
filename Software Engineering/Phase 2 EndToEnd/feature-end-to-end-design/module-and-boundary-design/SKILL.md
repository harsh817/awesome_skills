---
name: module-and-boundary-design
description: Design module ownership and boundaries for one feature. Use when deciding where feature behavior, rules, data access, API handling, and UI responsibilities belong.
---

# Module And Boundary Design

## Definition

Place feature knowledge in the modules best able to hide it. Boundaries should reduce cognitive load, avoid information leakage, and keep layers at distinct abstraction levels.

## Questions To Ask

- Which module owns this feature's domain rule?
- Which layer should know about UI state, API transport, persistence, and business policy?
- What must cross the boundary, and what must stay hidden?
- Are any new modules shallow wrappers?
- Does the feature require moving complexity downward?

## Existing Project Comparison

- Inspect existing modules, folders, imports, commands, services, and tests.
- Compare proposed boundaries with `AGENT_GUARDRAILS.md`.
- Identify duplicated rules, pass-through layers, and ownership conflicts.

## Suggestive Plan

1. Identify owner module.
2. List affected modules and responsibilities.
3. Define allowed dependency direction.
4. Mark hidden decisions per module.
5. Remove pass-through or shallow boundaries.

## Example

Scheduling owns appointment-window rules. API routes translate requests. UI manages form state. Data access persists scheduling state without owning scheduling policy.

## Vocabulary

- Boundary: line where modules or layers communicate.
- Owner module: module responsible for rules and decisions.
- Information hiding: keeping design knowledge inside the owner.
- Pass-through layer: layer that forwards without adding abstraction.

## Expected Outcome

Produce a boundary map with owner modules, responsibilities, hidden details, allowed dependencies, and boundary risks.
