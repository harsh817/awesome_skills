---
name: interface-and-api-rules
description: Define or audit how modules, layers, services, and external clients communicate. Use when designing APIs, reviewing public interfaces, preventing implementation leakage, or simplifying contracts between modules.
---

# Interface And API Rules

## Definition

Define the contracts modules use to communicate. An interface is everything callers must know: signatures, data shapes, behavior, ordering, errors, side effects, performance expectations, and informal rules.

## Process

1. Identify the caller's goal and design the smallest interface that satisfies common cases.
2. Keep rare features optional and out of the common path.
3. Hide implementation details, persistence shapes, transport types, and vendor SDKs.
4. Document informal behavior that code signatures cannot express.
5. Review whether the interface is simpler than the implementation it hides.
6. Remove pass-through variables and methods unless they create a distinct abstraction.

## Rules

- Design APIs around intent, not internal steps.
- Do not expose fields just because the implementation has them.
- Prefer fewer, more powerful operations over many shallow methods.
- Make defaults live behind the interface when callers should not care.
- Treat exceptions and errors as part of the interface.

## Examples

- Good: `reserveSlot(patientId, requestedWindow)` hides lock, conflict, and timezone details.
- Bad: `checkSlot`, `lockSlot`, `createVisit`, `sendCalendarInvite` required in exact caller order.
- Good API comment: describes what happens if no slot is available.
- Bad API comment: explains the table queries used internally.

## Vocabulary

- Formal interface: signature, public fields, schema, route, or type.
- Informal interface: behavior, constraints, side effects, timing, and errors.
- Abstraction: a simplified view that omits unneeded detail.
- Pass-through method: a method that mostly forwards to another method.
- Common path: the normal use case the interface should make simple.

## Expected Outcome

Produce API rules covering allowed exports, input and output shapes, error contracts, documentation requirements, forbidden leaks, and review questions for interface depth.
