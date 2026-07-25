---
name: backend-and-business-logic-design
description: Design backend flow and business logic for one feature. Use when deciding commands, transactions, domain rules, permissions, side effects, jobs, and module ownership before coding backend behavior.
---

# Backend And Business Logic Design

## Definition

Design the server-side behavior that enforces the feature's rules and state changes. Keep business logic in owner modules, not scattered through routes, UI, or persistence adapters.

## Questions To Ask

- What command or use case performs the feature?
- What rules and permissions must it enforce?
- What data is read and written in one transaction?
- What side effects happen, such as notifications or jobs?
- What should be idempotent, retried, or blocked?

## Existing Project Comparison

- Inspect services, commands, route handlers, domain modules, permissions, jobs, and tests.
- Identify duplicated business logic and move it toward the owner.
- Check existing transaction and error-handling patterns.

## Suggestive Plan

1. Define the backend use case.
2. Order rule checks, permission checks, data reads, writes, and side effects.
3. Define transaction boundary.
4. Define domain events or notifications.
5. Map each behavior to tests.

## Example

`changePreferredWindow` verifies actor permission, checks request is pending, validates the window, writes the change, and emits `AppointmentRequestUpdated`.

## Vocabulary

- Use case: backend operation that completes a feature action.
- Business logic: rules and decisions that define correct behavior.
- Transaction boundary: work that succeeds or fails together.
- Side effect: behavior outside the core state change.

## Expected Outcome

Produce backend design with use case flow, owner module, rules, transaction boundary, side effects, and test mapping.
