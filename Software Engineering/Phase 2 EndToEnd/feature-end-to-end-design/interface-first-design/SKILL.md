---
name: interface-first-design
description: Design the module interface for one feature before implementation. Use when defining commands, services, hooks, repositories, or public methods so callers see intent rather than implementation details.
---

# Interface-First Design

## Definition

Design the feature's public interfaces before writing internals. Interface comments and signatures reveal whether the abstraction is simple, deep, and complete.

## Questions To Ask

- What does the caller want to accomplish?
- What inputs are required, and which are implementation details?
- What output, error, or state change should callers observe?
- What ordering must callers not need to know?
- Can the interface comment stay simple?

## Existing Project Comparison

- Compare proposed interfaces with current naming, service, command, hook, and repository patterns.
- Flag APIs that expose database shapes, HTTP details, vendor SDKs, or internal steps.
- Look for duplicated or pass-through methods.

## Suggestive Plan

1. Write the interface name and purpose.
2. Draft signature, input, output, errors, and side effects.
3. Write the interface comment before implementation.
4. Remove parameters that push complexity onto callers.
5. Confirm common cases are simple.

## Example

Prefer `changePreferredWindow(requestId, window, actor)` over separate calls for loading request, checking status, validating window, saving, and notifying.

## Vocabulary

- Interface: everything callers must know to use a module.
- Informal contract: behavior not expressed in the signature.
- Interface comment: documentation defining the abstraction.
- Common case: normal path the interface should make easy.

## Expected Outcome

Produce interface definitions with purpose, inputs, outputs, errors, side effects, comments, and rejected leaks.
