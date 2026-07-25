---
name: vertical-slice-creation
description: Create small vertical slices that cut through UI, application logic, domain rules, data, and tests. Use when converting prioritized features into buildable increments or avoiding broad horizontal implementation plans.
---

# Vertical Slice Creation

## Definition

Turn a feature into the smallest end-to-end increment that demonstrates real user value. A vertical slice should include just enough interface, behavior, data, and verification to prove progress without building unused breadth.

## Questions To Ask

- What is the smallest end-to-end user behavior?
- What UI, command, domain rule, data, and test are required?
- What can be hardcoded, deferred, or replaced by a simpler first version?
- What abstraction will this slice validate?
- What would make this slice too horizontal?

## Existing Project Comparison

- Compare the slice to current layers and modules.
- Avoid slices that only create database tables, only create UI, or only create infrastructure.
- Check whether the slice can be verified from a user or API entry point.
- Confirm the slice does not scatter temporary special cases.

## Suggestive Plan

1. Pick one prioritized feature.
2. Define one user-visible success path.
3. Add only required rules and failures.
4. Identify touched layers.
5. Define verification and done criteria.

## Example

First scheduling slice: patient submits request with name, contact, and preferred window; system saves request and shows confirmation. Staff dashboard and calendar sync wait.

## Vocabulary

- Vertical slice: small end-to-end increment of value.
- Horizontal slice: work limited to one technical layer.
- Done criteria: evidence the slice is complete.
- End-to-end: behavior observable through a real entry point.
- Deferral: intentional postponement of nonessential breadth.

## Expected Outcome

Produce vertical slices with user behavior, touched layers, included rules, deferred work, tests, and build order.
