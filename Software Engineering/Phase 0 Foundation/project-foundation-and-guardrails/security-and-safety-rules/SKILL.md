---
name: security-and-safety-rules
description: Define or audit authentication, authorization, validation, secrets, sensitive data handling, and prohibited unsafe actions. Use when adding user access, handling private data, reviewing external inputs, or creating safety guardrails for agents and developers.
---

# Security And Safety Rules

## Definition

Define security and operational safety as explicit design knowledge owned by modules, not scattered checks. Security rules reduce unknown unknowns by making trust boundaries and prohibited actions obvious.

## Process

1. Identify actors, authentication method, authorization model, and sensitive data.
2. Place authorization checks at stable interfaces, close to the protected operation.
3. Validate all external input at boundaries and preserve domain invariants internally.
4. Keep secrets out of code, logs, tests, fixtures, and generated output.
5. Define destructive, irreversible, or privacy-sensitive actions that require confirmation.
6. Add tests for permission failures and unsafe input.

## Rules

- Never trust client-side checks as authorization.
- Do not duplicate security policy across UI, route, and domain code; give it an owner.
- Log enough for diagnosis without leaking secrets or private data.
- Fail closed when permission or validation state is unknown.
- Treat dependencies, environment variables, and migrations as safety surfaces.

## Examples

- Good: `documents.canEdit(user, document)` owns edit permission.
- Bad: every route checks a different role string.
- Good: API validates request shape before calling the domain command.
- Bad: raw request bodies flow into database queries or shell commands.

## Vocabulary

- Trust boundary: place where untrusted data enters the system.
- Authentication: proving who the actor is.
- Authorization: deciding what the actor may do.
- Sensitive data: secrets, personal data, credentials, tokens, and private business data.
- Fail closed: deny access when uncertain.
- Policy owner: the module responsible for a safety rule.

## Expected Outcome

Produce security rules covering identity, permissions, validation, secrets, logging, sensitive data, destructive actions, and required abuse-case tests.
