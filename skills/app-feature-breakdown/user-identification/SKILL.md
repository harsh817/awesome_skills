---
name: user-identification
description: Identify primary, secondary, and supporting users for an app outcome. Use when discovering whose journeys, permissions, pains, and decisions should shape the feature map or when an existing project has unclear user roles.
---

# User Identification

## Definition

Name the users whose goals determine the product shape. Do not treat all actors equally. The primary user is the one whose successful outcome justifies the app; secondary and supporting users matter only where they affect that outcome.

## Questions To Ask

- Who experiences the pain directly?
- Who performs the work?
- Who receives the result?
- Who approves, pays, administers, or audits?
- Which user should the first build serve if only one can be served?

## Existing Project Comparison

- Inspect routes, roles, database entities, tests, and UI screens for user types.
- Compare discovered actors with the stated outcome.
- Flag missing users, duplicate role names, and roles that mix business meaning with permissions.
- Identify users implied by failure cases, such as approvers or support staff.

## Suggestive Plan

1. List all actors.
2. Mark primary, secondary, supporting, and external systems.
3. Write each user's goal and risk.
4. Remove actors that do not affect the outcome.
5. Use the primary user to prioritize journeys.

## Example

For clinic scheduling: primary user may be the patient, secondary user the clinic receptionist, supporting user the clinician, and external system the calendar provider.

## Vocabulary

- Actor: a person or system that interacts with the app.
- Primary user: the user whose outcome drives the first build.
- Secondary user: a user who supports or benefits from the outcome.
- Supporting user: an admin, approver, operator, or auditor.
- Role: permission or responsibility assigned to an actor.

## Expected Outcome

Produce a user map with actor type, goal, pain, permissions, and priority for journey mapping.
