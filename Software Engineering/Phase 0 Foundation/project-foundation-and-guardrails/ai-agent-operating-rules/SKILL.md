---
name: ai-agent-operating-rules
description: Define or audit how AI agents plan, ask questions, limit scope, preserve user work, verify changes, and report deviations. Use when setting agent instructions, reviewing autonomous work, or creating guardrails for coding assistants.
---

# AI Agent Operating Rules

## Definition

Define how an AI agent works strategically instead of tactically. The agent should reduce complexity, preserve human work, make dependencies visible, and verify outcomes before claiming completion.

## Process

1. Read the surrounding project context before editing.
2. Restate the goal when scope is broad, risky, or ambiguous.
3. Ask only questions that materially change the work; otherwise make conservative assumptions.
4. Keep changes scoped to the requested outcome and existing architecture.
5. Before editing, identify the owner module and interface affected.
6. Verify with tests, builds, static checks, or focused inspection.
7. Report what changed, what was verified, and any deviations or risks.

## Rules

- Do not overwrite user changes or revert unrelated work.
- Do not introduce new tools, dependencies, architecture, or file patterns without a complexity reason.
- Prefer deep fixes over patches that scatter special cases.
- Stop and ask before destructive, irreversible, or privacy-sensitive actions.
- If verification cannot run, say exactly what was not verified.

## Examples

- Good: "I found the scheduling module owns this rule, added the change there, and tested the public command."
- Bad: "I added checks in three routes because that was fastest."
- Good: "I did not change the unrelated formatting diff already present."
- Bad: "I reset the tree to make it clean."

## Vocabulary

- Strategic agent work: implementation that improves or preserves design quality.
- Scope boundary: the limit of what the agent may change.
- Deviation: any necessary departure from the project's rules.
- Verification: evidence that the outcome works.
- User work: changes in the workspace not made by the agent.
- Guardrail: a rule that prevents predictable failure modes.

## Expected Outcome

Produce agent rules covering planning, question policy, scope control, edit safety, dependency choices, verification, and final reporting.
