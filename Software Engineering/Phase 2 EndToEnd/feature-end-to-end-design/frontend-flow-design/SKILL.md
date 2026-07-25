---
name: frontend-flow-design
description: Design the frontend flow for one feature, including screens, states, user actions, loading, validation, errors, accessibility, and connection to API behavior.
---

# Frontend Flow Design

## Definition

Design the user-facing path for the feature. The frontend should express the feature outcome clearly while hiding system complexity and matching existing product conventions.

## Questions To Ask

- Where does the user start the feature?
- What fields, controls, and states are needed?
- What feedback appears for loading, success, validation, and errors?
- What existing screens or components should be reused?
- What should be accessible by keyboard and assistive tech?

## Existing Project Comparison

- Inspect current routes, components, design system, forms, state management, and tests.
- Reuse existing patterns before inventing new UI structures.
- Flag UI that exposes internal IDs, implementation states, or backend sequencing.

## Suggestive Plan

1. Define entry point and user actions.
2. Map UI states: empty, editing, loading, success, error, disabled.
3. Define client validation and server error display.
4. Map API calls and optimistic or pessimistic update behavior.
5. Define accessibility and responsive requirements.

## Example

Receptionist opens request details, edits preferred window in a controlled form, saves, sees inline validation or a success confirmation, and remains on the updated request.

## Vocabulary

- UI state: visible condition of the interface.
- User feedback: confirmation, error, or progress signal.
- Client validation: immediate local check before API submission.
- Accessibility: usability for keyboard and assistive technology.

## Expected Outcome

Produce frontend flow with screens, actions, states, validation, API connection, accessibility, and UI test needs.
