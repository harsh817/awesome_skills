# awesome_skills

Project planning, foundation, and guardrail skills for coding agents.

This repository contains a coordinated set of skills based on the design principles from John Ousterhout's *A Philosophy of Software Design*: reduce complexity, prefer deep modules, hide information behind stable interfaces, keep dependencies obvious, and work strategically.

## Software Engineering

All skills live under `Software Engineering/`.

## Phase 0 Foundation

Main entry point:

- `project-guardrails-router` - invokes all guardrail skills one by one and creates `AGENT_GUARDRAILS.md`, the project-wide document coding agents must read from start to finish.

Folder:

- `Software Engineering/Phase 0 Foundation/project-foundation-and-guardrails`

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

## Phase 1 Features

Main entry point:

- `feature-breakdown-router` - invokes the feature-breakdown skills one by one and creates `FEATURE_MAP.md`, the ordered feature map coding agents can build from.

Folder:

- `Software Engineering/Phase 1 Features/app-feature-breakdown`

The feature-breakdown skills are:

- `outcome-definition`
- `user-identification`
- `user-journey-mapping`
- `journey-to-action-breakdown`
- `action-to-feature-breakdown`
- `business-rule-discovery`
- `failure-case-discovery`
- `feature-grouping`
- `feature-prioritization`
- `vertical-slice-creation`
- `feature-map-document`

## Recommended Use

For project guardrails:

```text
Use $project-guardrails-router to create AGENT_GUARDRAILS.md for this project.
```

For feature breakdown:

```text
Use $feature-breakdown-router to create FEATURE_MAP.md for this project.
```

Each router skill tells the agent to invoke the matching group skills in order and synthesize the results into a durable Markdown reference for future coding work.
