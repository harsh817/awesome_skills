---
name: architecture-style
description: Define or audit the project's architecture style, module shape, dependency direction, and layer boundaries. Use when establishing a modular monolith, reviewing cross-layer imports, deciding service boundaries, or simplifying architecture that has become shallow or tangled.
---

# Architecture Style

## Definition

Define the system shape and dependency direction so complexity is contained inside deep modules. The preferred default is a modular monolith unless independent deployment is truly required.

## Process

1. Name the architecture style and the reason it fits the project goal.
2. Identify layers and modules by distinct abstractions, not by temporal workflow steps.
3. Draw allowed dependency direction from delivery layers toward application/domain capabilities and from modules toward stable interfaces.
4. Keep implementation details below the interface that hides them.
5. Challenge every pass-through layer, pass-through variable, and wrapper module.
6. Record exceptions as architecture decisions with an expiry or review trigger.

## Rules

- Prefer deep modules: simple interface, substantial hidden behavior.
- Avoid shallow modules that add an interface without hiding meaningful complexity.
- Keep each layer at a different abstraction level.
- Do not split modules only because code is long; split when the split hides knowledge.
- Pull complexity downward into the module best able to hide it.

## Examples

- Good: `orders` exposes `placeOrder` and hides inventory checks, pricing rules, and transaction boundaries.
- Bad: `OrderService` calls `OrderValidator`, `OrderCalculator`, and `OrderRepository` in a way every caller must understand.
- Good dependency direction: UI -> application command -> domain module -> repository interface.
- Bad dependency direction: domain objects importing web request types.

## Vocabulary

- Module: a unit with an interface and an implementation.
- Interface: everything another module must know to use a module.
- Implementation: hidden decisions behind the interface.
- Deep module: powerful behavior behind a simple interface.
- Shallow module: a complex interface with little hidden behavior.
- Pass-through layer: a layer that mostly forwards calls or parameters without changing abstraction.

## Expected Outcome

Produce an architecture rule set with style, layers, allowed dependencies, forbidden imports, module depth expectations, and review criteria for exceptions.
