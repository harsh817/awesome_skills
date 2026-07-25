---
name: deployment-rollback-audit
description: Audit deployment and rollback readiness before production. Use when verifying build pipeline, staging deployment, environment configuration, migrations, smoke tests, release controls, rollback plan, and deploy safety.
---

# Deployment And Rollback Audit

## Definition

Confirm the release can be deployed and, if necessary, safely rolled back. Production readiness includes deploy mechanics, not just code quality.

## Questions To Ask

- What pipeline builds, tests, and deploys this release?
- Has the release deployed successfully to staging or an equivalent environment?
- What environment variables, secrets, and configuration differ in production?
- How do migrations interact with rollback?
- What smoke tests and release controls gate production?

## Existing Project Comparison

- Inspect CI/CD config, deployment scripts, environment examples, migration order, release docs, smoke tests, and rollback instructions.
- Compare deploy steps against actual project tooling and hosting platform behavior.
- Check whether rollback restores safe code and data states.

## Suggestive Plan

1. Map build, staging, production, and rollback flow.
2. Verify pipeline and staging evidence.
3. Inspect config, secrets, migrations, and release controls.
4. Confirm smoke tests and rollback steps are executable.
5. Update `PRODUCTION_READINESS.md`.

## Example

For a billing release, verify staging deploy, migration apply, invoice smoke test, production config, rollback command, and post-rollback data compatibility.

## Vocabulary

- Release control: gate that prevents unsafe production deployment.
- Smoke test: fast production-critical check after deploy.
- Rollback: returning code or configuration to a prior safe version.
- Staging: production-like environment used for release validation.

## Expected Outcome

Produce a deployment audit with pipeline evidence, staging status, config risks, migration and rollback safety, smoke tests, blockers, and accepted risks.
