---
name: coding-agent-instructions
description: Write precise coding-agent instructions for implementing one feature. Use when converting a plan into actionable agent guidance with scope boundaries, project comparisons, tests, stop conditions, documentation updates, and expected outcomes.
---

# Coding Agent Instructions

## Definition

Write implementation instructions that another coding agent can follow without guessing. The instructions should steer behavior, not merely describe the feature.

## Questions To Ask

- What exact outcome should the agent deliver?
- What files or modules are in scope and out of scope?
- Which project rules, documents, and conventions must be followed?
- What tests and manual checks must pass?
- When should the agent stop and ask instead of proceeding?

## Existing Project Comparison

- Reference existing modules, patterns, tests, and docs by path when available.
- Include current constraints from `AGENT_GUARDRAILS.md`, `FEATURE_DESIGN.md`, and repository inspection.
- Flag user changes that must be preserved.

## Suggestive Plan

1. State the feature task in one sentence.
2. List implementation boundaries and owner modules.
3. List required tests and verification commands.
4. Define documentation and delivery document updates.
5. Add stop conditions for ambiguity, destructive actions, secrets, or unrelated changes.

## Example

"Implement invoice resend in the billing service and admin route only; preserve existing invoice creation behavior; add service tests and one route test; update API docs if the public route changes."

## Vocabulary

- Scope boundary: line between intended and unrelated changes.
- Stop condition: condition requiring user input or a safer plan before continuing.
- Source of truth: document or code location that owns a decision.
- Instruction drift: implementation behavior that no longer matches written guidance.

## Expected Outcome

Produce a concise instruction block that names the task, boundaries, files, project rules, tests, docs, verification, stop conditions, and expected delivery.
