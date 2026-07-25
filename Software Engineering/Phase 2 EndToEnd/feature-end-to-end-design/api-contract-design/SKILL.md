---
name: api-contract-design
description: Design the API contract for one feature, including endpoint or procedure shape, request and response data, status/error semantics, validation, permissions, and versioning concerns.
---

# API Contract Design

## Definition

Design the transport-facing contract that lets clients perform the feature without learning backend internals. API contracts should expose intent and stable behavior, not persistence or implementation steps.

## Questions To Ask

- What API action does the frontend need?
- What request shape is required?
- What response shape supports the UI without leaking internals?
- What validation, permission, and conflict errors are possible?
- How does this contract fit existing API patterns?

## Existing Project Comparison

- Inspect existing routes, controllers, schemas, handlers, OpenAPI docs, clients, and tests.
- Reuse naming and response conventions.
- Flag contracts that expose database columns, service internals, or multi-step call order.

## Suggestive Plan

1. Define endpoint or procedure name.
2. Define request schema.
3. Define success response.
4. Define error response semantics.
5. Map contract to backend use case and frontend flow.

## Example

`PATCH /appointment-requests/{id}/preferred-window` accepts `{ start, end }` and returns the updated request summary plus user-facing status.

## Vocabulary

- API contract: transport-visible behavior and data shape.
- Request schema: accepted input shape.
- Response schema: returned output shape.
- Error semantics: stable meaning of failures.
- Transport: HTTP, RPC, GraphQL, events, or similar boundary.

## Expected Outcome

Produce API contract with endpoint/procedure, request, response, errors, permissions, validation, and tests.
