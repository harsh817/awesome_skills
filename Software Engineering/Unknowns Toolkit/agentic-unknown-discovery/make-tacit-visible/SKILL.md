---
name: make-tacit-visible
description: Ask question-first prompts to turn tacit preferences and unknown knowns into examples, references, criteria, prototypes, or reaction loops. Use for frontend design, architecture taste, developer experience, agent frameworks, workflows, documentation quality, and any work where the user knows what good looks like when they see it.
---

# Make Tacit Visible

## Definition

Turn "I will know it when I see it" into usable criteria. Ask for references, reactions, prototypes, examples, and rejection signals before implementation gets expensive.

## Questions To Ask

- Do you have a reference, screenshot, repo, app, article, design, library, or prior version that feels close?
- What feels right or wrong about this direction?
- Which option is closer to what you want?
- What would make you reject this?
- Should we prototype before touching the real project?
- What quality bar is hard for you to describe but easy to recognize?

## Question Rules

- Use examples and prototypes when words are not enough.
- Ask for reactions rather than forcing the user to produce perfect specifications.
- Prefer cheap artifacts before real implementation when taste or architecture preference is uncertain.
- Translate reactions into criteria that later phases can use.

## Existing Project Comparison

- Compare references and reactions against current project patterns.
- Identify where a desired style or workflow conflicts with existing architecture, design system, naming, or conventions.
- Capture reusable criteria in `UNKNOWNS.md`.

## Suggestive Plan

1. Ask for references or examples.
2. Offer a small set of directions or prototype options when useful.
3. Ask the user to react to differences.
4. Convert reactions into criteria, constraints, and rejection signals.
5. Update `UNKNOWNS.md`.

## Example

For a frontend dashboard, create or request three layout references, ask what feels too dense or too empty, then record criteria such as "operations-first, compact, no marketing hero".

## Vocabulary

- Unknown known: tacit preference the user recognizes but has not verbalized.
- Reference: artifact that shows desired behavior, style, or structure.
- Rejection signal: reason an option is not acceptable.
- Prototype: cheap artifact used to learn before implementation.

## Expected Outcome

Produce an `Unknown Knowns` section in `UNKNOWNS.md` with references, reactions, translated criteria, rejection signals, and prototype needs.
