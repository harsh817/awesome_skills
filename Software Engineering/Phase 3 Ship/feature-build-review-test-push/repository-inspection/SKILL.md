---
name: repository-inspection
description: Inspect an existing repository before implementing a feature. Use when a coding agent needs to understand project structure, current behavior, owner modules, tests, documentation, git state, and risk before planning code changes.
---

# Repository Inspection

## Definition

Build a clean map of the current project before changing it. Treat existing code as the primary source for architecture, vocabulary, dependency direction, tests, and conventions.

## Questions To Ask

- What feature or bug is being delivered?
- Which documents describe the intended outcome?
- What entry points, modules, routes, commands, jobs, or screens already own related behavior?
- What tests or manual checks currently cover the area?
- Are there uncommitted changes, and which appear unrelated to this task?

## Existing Project Comparison

- Inspect the file tree, package scripts, framework conventions, and domain folders.
- Compare `AGENT_GUARDRAILS.md`, `FEATURE_MAP.md`, and `FEATURE_DESIGN.md` against current files when they exist.
- Identify deep modules, shallow modules, information leakage, pass-through layers, repeated logic, vague names, and hidden dependencies.
- Record the smallest owner area where the feature should land.

## Suggestive Plan

1. Read the request and any durable planning documents.
2. Inspect project layout and likely entry points.
3. Inspect related tests, fixtures, documentation, and config.
4. Check current git state and mark unrelated changes.
5. Write repository findings into `FEATURE_DELIVERY.md`.

## Example

For "add invoice resend", inspect billing routes, invoice service, notification jobs, email tests, API docs, and pending local changes before proposing edits.

## Vocabulary

- Owner module: module responsible for a rule or behavior.
- Entry point: UI, API, command, job, or event handler that begins the feature.
- Information leakage: one design decision reflected across multiple modules.
- Unknown unknown: risk hidden because no inspected artifact reveals it yet.

## Expected Outcome

Produce a repository map with relevant files, owner modules, current behavior, test coverage, documentation, git state, risks, and open questions.
