---
name: project-guardrails-router
description: Automatically invoke the twelve Project Foundation and Guardrails skills one by one, then create or update the canonical AGENT_GUARDRAILS.md project operating document that coding agents must read from project start through final delivery. Use when the user wants one router skill to cover all foundation and guardrail decisions without manually invoking each skill.
---

# Project Guardrails Router

## Definition

Act as the single entry point for the full Project Foundation and Guardrails system. When this skill is invoked, do not merely summarize the twelve guardrail topics from memory. Invoke each named guardrail skill below, one after another, and use their outputs to create or update a single canonical Markdown document named `AGENT_GUARDRAILS.md`.

`AGENT_GUARDRAILS.md` is the project-long operating document for coding agents. It must cover all foundation and guardrail decisions from the start of the project through implementation, testing, review, commit, handoff, and future maintenance.

## Required Output Document

- Create or update exactly this file at the repository or workspace root: `AGENT_GUARDRAILS.md`.
- Make the first section tell every coding agent to read `AGENT_GUARDRAILS.md` before planning, editing, testing, committing, refactoring, adding dependencies, changing architecture, or handing off work.
- Write the document as a durable project reference, not as a one-time report.
- Cover all twelve foundation and guardrail areas in the same order as the invocation flow.
- If the project already has an agent instruction file such as `AGENTS.md`, `CLAUDE.md`, `.cursorrules`, or `.github/copilot-instructions.md`, keep `AGENT_GUARDRAILS.md` as the source document and add or recommend a short pointer from the existing file.
- Do not scatter these rules across many documents unless the user explicitly asks for a different documentation system.
- Read `references/agent-guardrails-template.md` before writing the document.

## Exact Skill Invocation Flow

Invoke the following skills explicitly, in this exact order. Complete the current skill's section in `AGENT_GUARDRAILS.md` before invoking the next skill. Do not skip a skill unless the user explicitly removes that guardrail from scope.

1. Invoke `$project-goal-and-scope`.
   - Write `## 1. Project Goal And Scope`.
   - Define what the app is, who it serves, what outcomes matter, what is in scope, and what is out of scope.
2. Invoke `$technology-stack-rules`.
   - Write `## 2. Technology Stack Rules`.
   - Define language, framework, database, package manager, testing tools, approved libraries, and dependency approval rules.
3. Invoke `$architecture-style`.
   - Write `## 3. Architecture Style`.
   - Define architecture style, layer boundaries, allowed dependency direction, and module-depth expectations.
4. Invoke `$module-ownership-rules`.
   - Write `## 4. Module Ownership Rules`.
   - Define which module owns each kind of knowledge, business rule, invariant, policy, and design decision.
5. Invoke `$folder-and-file-structure`.
   - Write `## 5. Folder And File Structure`.
   - Define where features, shared code, tests, migrations, configuration, and documentation belong.
6. Invoke `$naming-and-coding-conventions`.
   - Write `## 6. Naming And Coding Conventions`.
   - Define naming vocabulary, file patterns, formatting, comments, and consistency rules.
7. Invoke `$interface-and-api-rules`.
   - Write `## 7. Interface And API Rules`.
   - Define how modules and layers communicate, what they expose, and what implementation details must stay hidden.
8. Invoke `$data-and-migration-rules`.
   - Write `## 8. Data And Migration Rules`.
   - Define schema ownership, constraints, transactions, data access boundaries, and safe migration practices.
9. Invoke `$security-and-safety-rules`.
   - Write `## 9. Security And Safety Rules`.
   - Define authentication, authorization, validation, secrets, sensitive data, logging, and prohibited unsafe actions.
10. Invoke `$testing-rules`.
   - Write `## 10. Testing Rules`.
   - Define required tests for each change type, test locations, seams, fixtures, regression expectations, and verification commands.
11. Invoke `$git-and-change-rules`.
   - Write `## 11. Git And Change Rules`.
   - Define branch use, commit scope, files not to push, diff review, verification before push, and handoff rules.
12. Invoke `$ai-agent-operating-rules`.
   - Write `## 12. AI Agent Operating Rules`.
   - Define how coding agents must plan, ask questions, limit scope, protect user work, verify changes, and report deviations.

## Operating Rules

- Gather existing project facts from files before inventing rules.
- If a fact is unknown, write `TBD` with a specific question or decision owner.
- Prefer concise rules that reduce complexity over exhaustive policy prose.
- Keep every rule actionable: it must tell a future agent what to do, avoid, check, or ask.
- Preserve user-written project rules and reconcile conflicts explicitly.
- When updating an existing `AGENT_GUARDRAILS.md`, preserve valid project-specific decisions and only replace stale or conflicting text.
- The user should only need to invoke `$project-guardrails-router`; this router is responsible for invoking the other twelve skills automatically.

## Document Rules

The final document must include:

- A first section named `Read This First` that says coding agents must read the whole file before starting and keep referring to it until the project or task is complete.
- One section for each of the twelve guardrail areas, in the same order as the Auto Flow.
- A final section named `Open Questions And TBDs`.
- Short bullets or tables, not long essays.
- Concrete examples only when they prevent likely misuse.
- Exact commands or file paths where the project already defines them.
- Clear instructions that `AGENT_GUARDRAILS.md` is the source of truth for project foundation and guardrails.

## Done When

- `AGENT_GUARDRAILS.md` exists at the project root.
- All twelve sections are present in order.
- Each section was produced after invoking the matching named skill from the Exact Skill Invocation Flow.
- Unknowns are explicit as `TBD`, not hidden behind vague language.
- Existing project rules are respected or conflicts are called out.
- The final answer reports the document path and any important open questions.
