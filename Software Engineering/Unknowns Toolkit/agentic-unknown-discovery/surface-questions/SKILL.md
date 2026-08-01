---
name: surface-questions
description: Ask question-first prompts to expose known unknowns before software work. Use for any domain when open decisions, ambiguities, missing requirements, uncertain architecture, debugging hypotheses, data choices, UX flows, or risky assumptions could change the next step.
---

# Surface Questions

## Definition

Expose the questions everyone already knows are unresolved. This skill helps decide what must be answered now, investigated by the agent, safely assumed, or deferred.

## Questions To Ask

- What decisions are still open?
- Which answer would change architecture, scope, UX, data model, debugging strategy, deployment, or implementation?
- What are you unsure about?
- What should I investigate in the codebase, docs, logs, or external references?
- What should I not assume?
- What would make this plan wrong?

## Question Rules

- Prioritize questions where the answer changes the shape of the work.
- Ask user-facing questions when project inspection cannot reveal intent.
- Mark mechanical or discoverable questions as `Investigate`.
- Mark reversible, low-risk gaps as `Assume for now` with a revisit trigger.
- Mark nonblocking curiosity as `Defer`.

## Existing Project Comparison

- Compare open questions against existing project docs, tests, issues, logs, schemas, routes, and code patterns.
- Convert questions answered by the project into known knowns.
- Keep contradictory or ambiguous evidence in the `Ask now` or `Investigate` buckets.

## Suggestive Plan

1. Review knowns and current phase target.
2. List open questions.
3. Classify each question by impact and owner.
4. Ask the highest-leverage user question first.
5. Update `UNKNOWNS.md`.

## Example

For a debugging task, ask whether preserving current behavior matters more than a quick fix, which user flow is failing, and whether logs or reproduction steps exist.

## Vocabulary

- Known unknown: explicit unresolved question.
- High-leverage question: answer that changes direction or avoids wasted work.
- Investigation item: question Codex can answer by inspecting artifacts.
- Revisit trigger: event that makes an assumption worth checking again.

## Expected Outcome

Produce a `Known Unknowns` section in `UNKNOWNS.md` with prioritized questions classified as `Ask now`, `Investigate`, `Assume for now`, or `Defer`.
