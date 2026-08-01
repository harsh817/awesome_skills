---
name: clarify-knowns
description: Ask question-first prompts to capture known knowns before software work. Use for any domain when establishing the outcome, existing facts, decisions, constraints, project state, references, and user context before planning, designing, debugging, building, or auditing.
---

# Clarify Knowns

## Definition

Capture what is already true so the agent does not rediscover obvious context or make wrong assumptions. This skill asks questions first, then records reliable facts in `UNKNOWNS.md`.

## Questions To Ask

- What are we trying to accomplish?
- What do you already know about the problem, codebase, domain, or tool?
- What has already been decided?
- What constraints should I respect?
- What existing files, examples, docs, designs, tickets, logs, or previous attempts matter?
- What should I treat as out of scope?

## Question Rules

- Ask only questions that establish facts needed for the next phase.
- Ask one at a time when an answer could change direction.
- Use project inspection for facts the repository can answer better than the user.
- Record confidence and source for each known.

## Existing Project Comparison

- Compare user-stated facts with existing project files and durable docs when available.
- Flag contradictions between user intent, code, tests, docs, and configuration.
- Convert stable project facts into `Known Knowns`.

## Suggestive Plan

1. Identify the current work type.
2. Ask for outcome, decisions, constraints, and relevant references.
3. Inspect obvious project documents when available.
4. Record facts, sources, confidence, and contradictions in `UNKNOWNS.md`.
5. Hand unresolved items to `$surface-questions`.

## Example

For a database redesign, ask what data must be preserved, which tables are in scope, what migrations already exist, and whether downtime is allowed.

## Vocabulary

- Known known: fact already established or discoverable.
- Constraint: boundary the solution must respect.
- Source: user statement, file, test, doc, log, or external reference.
- Confidence: how reliable a known appears to be.

## Expected Outcome

Produce a clear `Known Knowns` section in `UNKNOWNS.md` with outcome, decisions, constraints, relevant references, confidence, contradictions, and out-of-scope boundaries.
