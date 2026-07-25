---
name: code-quality-documentation-audit
description: Audit code quality and documentation before production. Use when checking consistency, readability, interface comments, design notes, stale comments, TODOs, debug code, naming, and nonobvious implementation choices.
---

# Code Quality And Documentation Audit

## Definition

Check whether the code and documentation will be readable and maintainable under production pressure. Comments should explain nonobvious intent and interfaces, not repeat code.

## Questions To Ask

- Does the code follow existing naming, formatting, and organization patterns?
- Are public interfaces documented with caller-relevant contracts?
- Are design notes recorded where future maintainers will find them?
- Are comments stale, duplicative, or implementation-contaminated?
- Are TODOs, debug logs, or temporary code still present?

## Existing Project Comparison

- Compare changed files to neighboring conventions and docs.
- Inspect README files, API docs, comments, examples, changelogs, and design notes.
- Check for vague names, hard-to-describe code, stale docs, excessive comments, and missing comments on nonobvious behavior.

## Suggestive Plan

1. Review changed and high-risk files for readability.
2. Check documentation against actual behavior.
3. Find stale comments, TODOs, debug code, and misleading notes.
4. Add or request concise interface and design-intent documentation.
5. Update `PRODUCTION_READINESS.md`.

## Example

If a billing retry policy is only explained in a commit message, require a design note near the retry owner or in durable operations docs.

## Vocabulary

- Interface comment: caller-facing contract and expectation.
- Design note: durable explanation of an important tradeoff.
- Stale comment: comment contradicting current behavior.
- Obvious code: code whose behavior and intent are easy to understand.

## Expected Outcome

Produce a code quality and documentation audit with consistency issues, stale docs, TODO/debug findings, readability risks, and required updates.
