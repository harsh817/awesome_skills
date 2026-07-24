---
name: module-ownership-rules
description: Define or audit which module owns each business rule, data concept, policy, and design decision. Use when assigning responsibility, removing duplicated rules, fixing information leakage, or deciding where new behavior belongs.
---

# Module Ownership Rules

## Definition

Assign one home for every important piece of knowledge. Ownership is information hiding in organizational form: the owner module may know the details; other modules may only depend on its interface.

## Process

1. List each business rule, invariant, policy, external protocol, and persistence rule.
2. Assign exactly one owner module for each item.
3. Define what the owner exposes and what it hides.
4. Search for duplicated knowledge across modules and move it behind the owner.
5. If two modules must know the same detail, either introduce a deeper owner or document the dependency as intentional.
6. Keep ownership aligned with concepts, not request flow order.

## Rules

- A design decision reflected in multiple modules is information leakage.
- Do not let UI, database, or transport modules own domain rules.
- Do not let shared utility folders become owners of business meaning.
- Prefer owner APIs that answer intent-level questions over APIs that expose internal state.
- Move defaults, validation rules, and policy choices to the module that can hide the reason for them.

## Examples

- Good: `billing` owns invoice status transitions; other modules request `markInvoicePaid`.
- Bad: UI, API route, and database trigger each reimplement "invoice can be paid only once."
- Good: `scheduling` owns timezone normalization.
- Bad: every caller formats appointment times with its own offset rules.

## Vocabulary

- Information hiding: keeping design knowledge inside one module.
- Information leakage: the same design decision appearing in multiple modules.
- Owner module: the module responsible for a concept and its invariants.
- Invariant: a rule that must always remain true.
- Domain rule: a business rule independent of UI and storage.
- Temporal decomposition: organizing by steps in time rather than by hidden knowledge; usually a design smell.

## Expected Outcome

Produce an ownership map with concept or rule, owning module, public interface, hidden decisions, forbidden duplicate locations, and tests that prove ownership.
