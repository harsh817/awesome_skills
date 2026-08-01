---
name: find-blindspots
description: Ask question-first prompts to uncover unknown unknowns before or during software work. Use for any domain when hidden assumptions, missing failure modes, unseen dependencies, security risks, data risks, edge cases, or expert concerns could change the plan.
---

# Find Blindspots

## Definition

Search for what has not been considered yet. Ask expert-style questions and inspect project evidence when possible, but do not implement the fix unless the user moves into another workflow phase.

## Questions To Ask

- What might we be missing?
- What hidden dependency, permission, data state, failure mode, edge case, or operational constraint might matter?
- What would break if our main assumption is false?
- What would an expert ask before proceeding?
- What should we verify before committing to this path?
- What could become expensive to change later?

## Question Rules

- Ask blindspot questions near phase boundaries and before irreversible work.
- Prefer concrete risk categories over vague worry.
- Use project inspection to discover hidden dependencies and failure modes.
- Mark credible blindspots as blockers, investigations, assumptions, or deferred risks.

## Existing Project Comparison

- Inspect code paths, tests, schemas, permissions, logs, docs, deployment files, and prior delivery notes when available.
- Compare likely blindspots against existing workflow documents.
- Flag missing evidence, unknown dependencies, and unsafe interactions.

## Suggestive Plan

1. Identify the current plan or intended next step.
2. Generate domain-specific blindspot questions.
3. Inspect the project for evidence when possible.
4. Classify blindspots by risk and action.
5. Update `UNKNOWNS.md` and recommend whether to continue or pause.

## Example

Before building an auth provider, ask about account linking, session migration, tenant permissions, token refresh, rollback, existing auth modules, and test coverage.

## Vocabulary

- Unknown unknown: risk or fact not yet considered.
- Blindspot: important missing perspective or evidence.
- Hidden dependency: behavior relying on another system or module in a nonobvious way.
- Unsafe interaction: two individually acceptable choices that create risk together.

## Expected Outcome

Produce an `Unknown Unknowns` section in `UNKNOWNS.md` with blindspot questions, investigations, risk classifications, evidence gaps, and recommended next action.
