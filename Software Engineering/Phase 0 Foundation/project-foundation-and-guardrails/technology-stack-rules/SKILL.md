---
name: technology-stack-rules
description: Define or audit the approved language, framework, database, test tools, and libraries for a project. Use when creating project standards, choosing dependencies, reviewing new packages, or preventing stack drift that increases cognitive load and hidden coupling.
---

# Technology Stack Rules

## Definition

Define the small approved set of technologies the project uses and the standard for adding anything new. A stack rule exists to reduce cognitive load and keep dependencies obvious.

## Process

1. List the approved runtime, language, framework, database, testing tools, package manager, formatter, and deployment target.
2. Identify which layer owns each technology.
3. Prefer boring tools that hide complexity behind stable interfaces.
4. For each new dependency, require a reason it makes a module deeper or reduces system complexity.
5. Reject libraries that leak implementation details across modules or force global conventions into unrelated code.
6. Document version constraints and upgrade ownership.

## Rules

- Use one primary language and framework unless there is a clear boundary that hides the extra complexity.
- Do not add a dependency for thin convenience wrappers.
- Prefer libraries with narrow, stable APIs and good failure behavior.
- Keep infrastructure choices out of domain modules.
- Treat configuration as part of the interface: defaults, environment variables, and flags must be documented.

## Examples

- Good: "Use PostgreSQL for relational data; only the data access module imports the database client."
- Good: "Use Playwright for browser tests; do not add Cypress without an architecture decision."
- Bad: "Import the payment SDK directly from UI components."
- Review question: "Does this package remove complexity from the codebase, or only move it into an unfamiliar API?"

## Vocabulary

- Dependency: knowledge in one place that requires corresponding knowledge elsewhere.
- Obvious dependency: a connection visible through an interface, import, schema, or documented contract.
- Hidden dependency: a coupling that maintainers must infer.
- Deep tool: a library with a simple interface that hides meaningful implementation complexity.
- Stack drift: gradual addition of overlapping tools that raises cognitive load.

## Expected Outcome

Produce a stack contract with approved tools, allowed import boundaries, dependency approval criteria, version policy, and prohibited substitutes.
