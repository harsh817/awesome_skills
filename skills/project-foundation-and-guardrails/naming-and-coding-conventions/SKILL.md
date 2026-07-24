---
name: naming-and-coding-conventions
description: Define or audit naming, formatting, comments, file patterns, and coding consistency rules. Use when creating conventions, reviewing unclear names, writing comments, choosing formats, or reducing obscurity in code.
---

# Naming And Coding Conventions

## Definition

Define conventions that make code obvious. Names and comments are part of design because they expose or hide complexity for future readers.

## Process

1. Adopt the formatter and lint rules already chosen by the stack.
2. Define file, type, function, variable, and test naming patterns.
3. Prefer precise names that match the domain vocabulary.
4. Write comments for abstractions, constraints, and why-decisions; avoid comments that repeat code.
5. Write interface comments before implementation when designing nontrivial modules.
6. Check diffs for stale comments and inconsistent naming.

## Rules

- Use one word for one concept across the codebase.
- Avoid vague names such as `data`, `info`, `manager`, `processor`, and `helper` unless the domain gives them precise meaning.
- Implementation comments explain what is not obvious from the code and why it is done.
- Interface comments describe behavior, requirements, side effects, errors, and guarantees without leaking implementation.
- Prefer consistency even when a local alternative is slightly nicer.

## Examples

- Good: `cancelAppointment`, `AppointmentCancellationPolicy`, `slotStartsAt`.
- Bad: `handleThing`, `processData`, `doStuff`.
- Good comment: "Uses clinic-local time because appointment availability is defined by the clinic, not the patient."
- Bad comment: "Increment i by 1."

## Vocabulary

- Obscurity: important information that is not obvious.
- Interface comment: documentation that defines how to use a module or function.
- Implementation comment: documentation that helps maintainers understand internal logic.
- Precision: extra detail that removes ambiguity.
- Intuition: higher-level explanation that helps a reader understand the shape of the code.
- Consistency: repeated choices that reduce cognitive load.

## Expected Outcome

Produce convention rules for names, file patterns, formatting, comments, domain vocabulary, and review checks that keep code easy to read and change.
