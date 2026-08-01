---
name: unknowns-router
description: Orchestrate the Unknowns Toolkit question-first skills for any software work, including frontend, backend, debugging, database design, agent frameworks, docs, deployments, and audits. Use to create or update UNKNOWNS.md, ask focused user questions, classify unknowns, and recommend the next workflow phase without implementing the work.
---

# Unknowns Router

## Definition

Act as the entry point for the Unknowns Toolkit. Use the four unknown categories to help the user and agent discover what must be clarified before work becomes expensive.

This router is question-first. Do not implement, refactor, design the full solution, or audit the whole system unless the user explicitly moves into a build, design, ship, or audit phase. Ask the smallest set of questions that would change direction, scope, architecture, UX, data, debugging strategy, or risk.

## Questions To Ask

- What kind of work are we about to do: plan, design, build, debug, review, audit, explain, or decide?
- What outcome are we trying to make easier or safer?
- What phase or document should this support: `AGENT_GUARDRAILS.md`, `FEATURE_MAP.md`, `FEATURE_DESIGN.md`, `FEATURE_DELIVERY.md`, or `PRODUCTION_READINESS.md`?
- Should questions be asked one at a time, grouped by theme, or only when they could change direction?
- What project files, references, examples, or prior attempts should be considered before asking?

## Required Output Document

- Create or update exactly this file at the repository or workspace root: `UNKNOWNS.md`.
- Use `references/unknowns-template.md` when creating it from scratch.
- Keep the document short enough to remain usable during the next phase.
- Update it whenever the user answers questions, project inspection reveals facts, or a later phase exposes new unknowns.
- Record each item as one of: `Ask now`, `Investigate`, `Assume for now`, or `Defer`.

## Exact Skill Invocation Flow

Invoke these skills in order by exact skill name:

1. Invoke `$clarify-knowns`.
   - Write or update `Known Knowns`.
2. Invoke `$surface-questions`.
   - Write or update `Known Unknowns`.
3. Invoke `$make-tacit-visible`.
   - Write or update `Unknown Knowns`.
4. Invoke `$find-blindspots`.
   - Write or update `Unknown Unknowns`.

After the four passes, recommend the next workflow step:

- Phase 0 Foundation when project rules or scope are still missing.
- Phase 1 Features when outcome-to-feature mapping is next.
- Phase 2 EndToEnd when one feature needs design.
- Phase 3 Ship when implementation can begin or resume.
- Phase 4 Audit when production readiness needs evidence.

## Existing Project Comparison

- Inspect existing project documents and files only when they help produce better questions or classify unknowns.
- Compare user answers against project reality and flag contradictions.
- Prefer asking the user when their answer could change architecture, product direction, or risk acceptance.
- Prefer investigation when the project can answer the question better than the user.

## Suggestive Plan

1. Identify the current work type and target phase.
2. Run the four unknown passes.
3. Classify questions into `Ask now`, `Investigate`, `Assume for now`, and `Defer`.
4. Ask only the highest-leverage user questions first.
5. Update `UNKNOWNS.md` and recommend the next phase.

## Operating Rules

- Ask questions before doing work when answers could change direction.
- Prefer one question at a time for high-impact ambiguity.
- Explain why each important question matters.
- Do not overwhelm the user with every possible question.
- Work for any domain: frontend, backend, data, debugging, architecture, agent workflows, product design, documentation, deployment, or operations.

## Example

Before Phase 2, ask what is already decided about the feature, surface data model and UX uncertainties, request references for hard-to-describe quality bars, then search for blindspots such as permissions, retries, migrations, or rollback risks.

## Vocabulary

- Known known: fact already stated, decided, or discoverable.
- Known unknown: question the user or project already knows is open.
- Unknown known: tacit preference or quality bar the user recognizes when shown.
- Unknown unknown: risk, constraint, dependency, or standard not yet considered.
- Ask now: question whose answer could change the next move.

## Expected Outcome

Produce or update `UNKNOWNS.md` with categorized unknowns, focused questions for the user, investigation items for Codex, safe assumptions, deferred items, and a recommendation for the next workflow phase.
