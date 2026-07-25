---
name: security-readiness-audit
description: Audit security readiness before production. Use when reviewing authentication, authorization, input validation, secrets, dependency risks, data exposure, privacy, abuse paths, and unsafe interactions for a release or system.
---

# Security Readiness Audit

## Definition

Review whether the system protects users, data, and operations well enough for production. Treat missing security evidence as a release risk.

## Questions To Ask

- What data, users, roles, and permissions are in scope?
- Which entry points accept untrusted input?
- Where are secrets, credentials, tokens, and configuration stored?
- What dependency or supply-chain risks exist?
- What abuse paths or privilege escalations are plausible?

## Existing Project Comparison

- Inspect auth middleware, permission checks, validation, serialization, logs, dependencies, environment files, and security docs.
- Compare protection to data sensitivity, public exposure, and operational consequences.
- Check for missing authorization at secondary paths such as jobs, webhooks, admin tools, and exports.

## Suggestive Plan

1. Map assets, actors, entry points, and trust boundaries.
2. Inspect auth, authorization, input handling, secrets, dependencies, and logging.
3. Search for data exposure and abuse paths.
4. Classify findings by exploitability and impact.
5. Update `PRODUCTION_READINESS.md`.

## Example

For invoice exports, verify only authorized users can export, filters cannot expose other tenants, generated files expire, and export logs do not contain private invoice details.

## Vocabulary

- Trust boundary: line where data or control crosses between trust levels.
- Authorization: decision about whether an actor may perform an action.
- Secret: credential or token that must not be exposed.
- Abuse path: behavior that can be misused even if it is not a classic bug.

## Expected Outcome

Produce a security audit with protected assets, trust boundaries, findings, severity, blockers, accepted risks, and required fixes.
