---
name: user-journey-mapping
description: Map the steps a user takes to reach the desired app outcome. Use when turning users and outcomes into workflows, auditing existing screens, or finding missing transitions before feature breakdown.
---

# User Journey Mapping

## Definition

Describe the user's path from trigger to completed outcome. A journey should reveal decisions, handoffs, dependencies, and moments where complexity appears for the user or system.

## Questions To Ask

- What starts the journey?
- What does the user know before starting?
- What steps must happen in order?
- Where does the user wait, decide, correct, or abandon?
- What confirms completion?

## Existing Project Comparison

- Compare existing navigation, routes, pages, and tests to the intended journey.
- Identify screens without a journey step and journey steps without a screen.
- Find pass-through screens that add work without changing the user's state.
- Check whether the journey exposes internal implementation details.

## Suggestive Plan

1. Write the happy path as 5 to 9 steps.
2. Add key decisions and handoffs.
3. Mark user-visible state changes.
4. Mark system-visible state changes.
5. Note missing, redundant, or unclear steps.

## Example

Patient scheduling journey: request appointment, choose time window, enter contact details, confirm preferences, receive slot proposal, accept slot, get confirmation.

## Vocabulary

- Journey: ordered path from trigger to outcome.
- Trigger: event that starts the journey.
- State change: meaningful change in user or system status.
- Handoff: transfer of responsibility between users, modules, or systems.
- Happy path: expected successful journey.

## Expected Outcome

Produce a journey map with ordered steps, triggers, decisions, states, handoffs, and gaps to feed action breakdown.
