---
name: project-goal-and-scope
description: Define or audit a project's goal, users, success boundary, and explicit out-of-scope work. Use when starting a project, writing a PRD, clarifying scope, rejecting feature creep, or checking whether a proposed change increases complexity without serving the core purpose.
---

# Project Goal And Scope

## Definition

Define the narrow reason the app exists, the people it serves, the outcomes it must make easier, and the work it must refuse. Treat scope as a complexity boundary: every accepted goal creates dependencies; every rejected goal protects the design.

## Process

1. State the primary user and their painful job in one sentence.
2. State the core outcome in observable terms, not implementation terms.
3. List the minimum capabilities required for that outcome.
4. Write non-goals before optional goals. A non-goal is a decision, not a vague postponement.
5. For each requested feature, ask whether it reduces complexity for the user or merely adds surface area to the system.
6. Prefer a smaller goal that enables deep modules over a broad goal that forces shallow feature wrappers.

## Rules

- Keep the goal stable enough that modules can hide complexity behind it.
- Reject tactical additions that make the first version faster but increase future change amplification.
- If a feature serves a different user, workflow, or business rule, call it out as a new scope decision.
- Record unknowns explicitly; unknown unknowns are the most dangerous form of complexity.
- Do not let technology choices define the project goal.

## Examples

- Good: "A lightweight appointment intake app for solo clinics that converts patient requests into confirmed slots without phone follow-up."
- Too broad: "A complete healthcare platform."
- Good non-goal: "No billing, insurance claims, or clinical records in v1."
- Scope check: "Adding chat support is out of scope unless it directly reduces appointment back-and-forth."

## Vocabulary

- Complexity: anything that makes the system hard to understand or change.
- Change amplification: one small user-facing change requiring edits in many places.
- Cognitive load: how much a maintainer must hold in mind to make a safe change.
- Unknown unknown: a hidden requirement or dependency that surprises the implementer.
- Strategic programming: investing design effort now to keep future work cheaper.
- Tactical programming: optimizing only for getting the current change working.

## Expected Outcome

Produce a project statement with users, core outcome, in-scope capabilities, explicit non-goals, success signals, and the rationale for keeping the surface area small.
