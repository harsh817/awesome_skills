---
name: journey-to-action-breakdown
description: Break each user journey step into concrete user and system actions. Use when converting journeys into implementable behavior, comparing workflows to existing code, or exposing hidden actions before feature design.
---

# Journey To Action Breakdown

## Definition

Translate journey steps into observable actions. An action is smaller than a feature: it is something a user does, the system does, or another actor does to move the journey forward.

## Questions To Ask

- What does the user click, enter, choose, confirm, or cancel?
- What does the system calculate, validate, persist, notify, or display?
- What must happen before this action is allowed?
- What changes after the action succeeds?
- What actions are implied but not visible?

## Existing Project Comparison

- Map actions to routes, handlers, commands, forms, jobs, tests, or events.
- Find actions with no implementation and implementation with no journey reason.
- Flag action sequences that force callers to know internal order.
- Prefer actions that hide complexity behind deeper module operations.

## Suggestive Plan

1. For each journey step, list user actions.
2. Add system actions behind each user action.
3. Add preconditions and postconditions.
4. Mark action owners when obvious.
5. Merge tiny pass-through actions where they do not create useful clarity.

## Example

Journey step: "accept slot." Actions: user clicks accept, system verifies slot still available, reserves slot, writes confirmation, sends notification, displays final state.

## Vocabulary

- Action: a concrete behavior that changes progress or state.
- Preconditions: facts required before an action can run.
- Postconditions: facts true after successful action.
- System action: hidden behavior performed by the app.
- Pass-through action: a step that forwards work without adding meaning.

## Expected Outcome

Produce an action table with journey step, user action, system action, preconditions, postconditions, and likely owner.
