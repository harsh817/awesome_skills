---
name: architecture-complexity-audit
description: Audit architecture and complexity before production. Use when reviewing module boundaries, deep interfaces, information hiding, information leakage, pass-through layers, repetition, vague names, nonobvious code, and Ousterhout-style red flags.
---

# Architecture And Complexity Audit

## Definition

Review whether the system structure is understandable enough to operate and change safely in production. Working code is not enough if it increases complexity beyond what the team can manage.

## Questions To Ask

- Which modules own the core business rules and production risks?
- Are interfaces simpler than their implementations?
- Where do design decisions leak across modules?
- Which names, layers, or abstractions are hard to explain?
- What complexity was intentionally accepted?

## Existing Project Comparison

- Inspect modules, interfaces, service boundaries, routes, jobs, data access, and tests.
- Check book red flags: shallow modules, information leakage, temporal decomposition, overexposure, pass-through methods, repetition, special-general mixtures, conjoined methods, vague names, and nonobvious code.
- Compare findings against existing architecture rules and delivery documents.

## Suggestive Plan

1. Map owner modules and dependency direction.
2. Inspect changed and high-risk paths for red flags.
3. Identify complexity that increases change amplification, cognitive load, or unknown unknowns.
4. Recommend must-fix simplifications and accepted tradeoffs.
5. Update `PRODUCTION_READINESS.md`.

## Example

If payment rules live in UI, route handlers, and database hooks, flag information leakage and require one payment owner module before production.

## Vocabulary

- Deep interface: small interface hiding substantial useful behavior.
- Information leakage: design decision duplicated across modules.
- Change amplification: one small change requiring edits in many places.
- Cognitive load: knowledge required to safely change the system.

## Expected Outcome

Produce an architecture audit with red flags, boundary issues, complexity risks, recommended fixes, and accepted design tradeoffs.
