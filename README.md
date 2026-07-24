# awesome_skills

Project foundation and guardrail skills for coding agents.

This repository contains a coordinated set of skills based on the design principles from John Ousterhout's *A Philosophy of Software Design*: reduce complexity, prefer deep modules, hide information behind stable interfaces, keep dependencies obvious, and work strategically.

## Skills

The main entry point is:

- `project-guardrails-router` - invokes all guardrail skills one by one and creates `AGENT_GUARDRAILS.md`, the project-wide document coding agents must read from start to finish.

The guardrail skills are:

- `project-goal-and-scope`
- `technology-stack-rules`
- `architecture-style`
- `module-ownership-rules`
- `folder-and-file-structure`
- `naming-and-coding-conventions`
- `interface-and-api-rules`
- `data-and-migration-rules`
- `security-and-safety-rules`
- `testing-rules`
- `git-and-change-rules`
- `ai-agent-operating-rules`

## Recommended Use

Invoke:

```text
Use $project-guardrails-router to create AGENT_GUARDRAILS.md for this project.
```

The router skill tells the agent to invoke each guardrail skill in order and synthesize the results into a durable Markdown reference for future coding work.
