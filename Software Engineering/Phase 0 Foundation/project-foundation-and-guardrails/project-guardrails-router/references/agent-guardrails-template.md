# AGENT_GUARDRAILS.md Template

Use this structure when creating or updating the project guardrails document. This is not a one-time report. It is the file coding agents must read and follow from the beginning of the project through final delivery and future maintenance.

```markdown
# Agent Guardrails

## Read This First

- Coding agents must read this entire file before planning, editing, testing, committing, refactoring, adding dependencies, changing architecture, or handing off work.
- Keep referring to this file from the start of the project or task until the work is complete.
- This file is the source of truth for project foundation and guardrails.
- Treat these rules as the project-specific guardrails unless a newer explicit user instruction overrides them.
- If a rule conflicts with the codebase, stop and report the conflict before changing the system.

## 1. Project Goal And Scope

- Primary users:
- Core outcome:
- In scope:
- Out of scope:
- Success signals:

## 2. Technology Stack Rules

- Language and runtime:
- Framework:
- Database:
- Package manager:
- Testing tools:
- Approved libraries:
- Dependency approval rule:

## 3. Architecture Style

- Architecture style:
- Layers:
- Allowed dependency direction:
- Forbidden dependencies:
- Module depth rule:

## 4. Module Ownership Rules

| Knowledge or rule | Owner module | Public interface | Hidden details |
| --- | --- | --- | --- |
| TBD | TBD | TBD | TBD |

## 5. Folder And File Structure

- Source code:
- Feature or module code:
- Shared infrastructure:
- Tests:
- Migrations:
- Documentation:
- Files or folders to avoid:

## 6. Naming And Coding Conventions

- Naming vocabulary:
- File naming:
- Type or class naming:
- Function naming:
- Comment rules:
- Formatting:

## 7. Interface And API Rules

- Public interface style:
- Input and output rules:
- Error rules:
- Implementation details that must not leak:
- Documentation requirements:

## 8. Data And Migration Rules

- Schema ownership:
- Data access boundary:
- Constraint policy:
- Transaction policy:
- Migration process:
- Backfill and rollback rules:

## 9. Security And Safety Rules

- Authentication:
- Authorization:
- Validation:
- Secrets:
- Sensitive data:
- Logging:
- Prohibited actions:

## 10. Testing Rules

- Required test types:
- Test locations:
- Behavioral seams:
- Fixture rules:
- Regression test rule:
- Verification commands:

## 11. Git And Change Rules

- Branch rules:
- Commit scope:
- Files not to commit:
- Diff review checklist:
- Push conditions:
- PR or handoff expectations:

## 12. AI Agent Operating Rules

- Planning:
- Question policy:
- Scope control:
- Edit safety:
- Verification:
- Reporting:

## Open Questions And TBDs

- TBD:
```
