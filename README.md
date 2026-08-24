# awesome_skills

Project planning, foundation, guardrail, unknown discovery, design, delivery, shipping, and production readiness skills for coding agents.

This repository contains a coordinated set of skills based on the design principles from John Ousterhout's *A Philosophy of Software Design*: reduce complexity, prefer deep modules, hide information behind stable interfaces, keep dependencies obvious, and work strategically.

## Software Engineering

All skills live under `Software Engineering/`.

## Video Video Editing

Main entry point:

- `production-video-pipeline` - coordinates reference analysis, storyboard planning, ComfyUI video generation, Hyperframes editing, and quality review/fix into one production workflow.

Folder:

- `Video Video Editing/production-video-pipeline`

The video production skills are:

- `production-video-pipeline`
- `reference-video-analysis`
- `video-storyboard-planner`
- `comfyui-video-generation`
- `fashion-visual-direction`
- `hyperframes-video-editing`
- `video-quality-review-fix`

For AI-assisted video production:

```text
Use $production-video-pipeline to create a coherent short video from a reference, concept, or outfit brief with final proof.
```

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

## Phase 2 EndToEnd

Main entry point:

- `feature-design-router` - invokes the end-to-end feature design skills one by one and creates `FEATURE_DESIGN.md`, the comprehensive frontend, API, backend, database, and test plan for one feature.

Folder:

- `Software Engineering/Phase 2 EndToEnd/feature-end-to-end-design`

The end-to-end feature design skills are:

- `feature-outcome-definition`
- `feature-scope-definition`
- `acceptance-criteria-writing`
- `design-it-twice`
- `module-and-boundary-design`
- `interface-first-design`
- `data-model-design`
- `backend-and-business-logic-design`
- `api-contract-design`
- `frontend-flow-design`
- `error-and-edge-case-design`
- `test-plan-design`

## Recommended Use

For unknown discovery between phases:

```text
Use $unknowns-router to create UNKNOWNS.md and ask focused questions before the next phase.
```

For project guardrails:

```text
Use $project-guardrails-router to create AGENT_GUARDRAILS.md for this project.
```

For feature breakdown:

```text
Use $feature-breakdown-router to create FEATURE_MAP.md for this project.
```

For end-to-end feature design:

```text
Use $feature-design-router to create FEATURE_DESIGN.md for this feature.
```

## Phase 3 Ship

Main entry point:

- `feature-ship-router` - invokes the build, review, test, and push skills one by one and creates or updates `FEATURE_DELIVERY.md`, the comprehensive delivery document for one working feature.

Folder:

- `Software Engineering/Phase 3 Ship/feature-build-review-test-push`

The feature shipping skills are:

- `repository-inspection`
- `implementation-planning`
- `coding-agent-instructions`
- `small-slice-implementation`
- `run-behavior-verification`
- `plan-to-code-comparison`
- `design-complexity-review`
- `strategic-fixing-refactoring`
- `test-implementation`
- `documentation-review`
- `final-diff-review`
- `commit-and-push`

For build, review, test, and push:

```text
Use $feature-ship-router to create FEATURE_DELIVERY.md and ship this feature.
```

## Phase 4 Audit

Main entry point:

- `production-readiness-router` - invokes the production readiness audit skills one by one and creates or updates `PRODUCTION_READINESS.md`, the comprehensive audit document for deciding production readiness.

Folder:

- `Software Engineering/Phase 4 Audit/production-readiness-audit`

The production readiness audit skills are:

- `requirements-completeness-audit`
- `architecture-complexity-audit`
- `code-quality-documentation-audit`
- `functional-regression-test-audit`
- `security-readiness-audit`
- `data-migration-audit`
- `performance-capacity-audit`
- `reliability-failure-audit`
- `deployment-rollback-audit`
- `observability-operations-audit`
- `full-system-adversarial-review`
- `production-readiness-decision`

For production readiness:

```text
Use $production-readiness-router to create PRODUCTION_READINESS.md and decide readiness.
```

## Unknowns Toolkit

Main entry point:

- `unknowns-router` - invokes the four question-first unknown discovery skills one by one and creates or updates `UNKNOWNS.md`, the lightweight document for clarifying what to ask, inspect, assume, or defer before the next workflow phase.

Folder:

- `Software Engineering/Unknowns Toolkit/agentic-unknown-discovery`

The unknown discovery skills are:

- `clarify-knowns`
- `surface-questions`
- `make-tacit-visible`
- `find-blindspots`

Use this toolkit between phases:

```text
Phase 0 Foundation -> Unknowns Toolkit -> Phase 1 Features
Phase 1 Features -> Unknowns Toolkit -> Phase 2 EndToEnd
Phase 2 EndToEnd -> Unknowns Toolkit -> Phase 3 Ship
Phase 3 Ship -> Unknowns Toolkit -> Phase 4 Audit
```

Each router skill tells the agent to invoke the matching group skills in order and synthesize the results into a durable Markdown reference for future coding work.
