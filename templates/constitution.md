# [PROJECT_NAME] Constitution

## Core Principles

### I. Spec-Driven Delivery
Behaviour and contracts are locked before parallel implementation. BDD acceptance scenarios and API/GraphQL contracts are the source of truth.

### II. Agent Orchestration Accountability
AI-assisted work runs from a published plan and task list. Engineers execute against those artefacts; freestyle prompting is not the default for feature work.

### III. Same Quality Bar (AI and Human)
AI-generated and human-written code meet the same lint, test, security, and review standards before merge.

### IV. Security & Privacy by Default
No real PII/secrets in prompts, fixtures, or logs. Mutations enforce authz and validation. Sensitive actions are audited when the domain requires it.

### V. Safe Release
User-facing behaviour ships behind a feature flag (default OFF), dark deploy, then progressive rollout with a clear rollback path.

### VI. Design-System Preferential Reuse
Prefer existing design-system components. New DS public APIs require tech-lead approval.

### VII. Simplicity
Do not expand scope beyond the locked spec. No drive-by refactors or unapproved dependencies.

## Quality Gates

- Lint, typecheck, and required tests must pass
- SAST/security scans must not introduce new critical/high issues from this change
- Review pack required for feature PRs: React/TS quality, security, performance, test coverage, documentation (or `/review-all`)
- Tech-lead review required for trust-boundary changes (authz, PII, migrations)

## Agent Workflow

1. `/speckit.specify` (or fill `spec.md`) → lock behaviour  
2. `/speckit.plan` (or fill `plan.md`) including **Agent Orchestration** section  
3. Context pack via `/context-pack`  
4. `/speckit.tasks` with `[P]` parallel markers and agent lane tags  
5. Implement with domain skills → `/review-all` → flag/rollout  
6. Record effectiveness notes; curate skills when misses repeat  

## Governance

- This constitution supersedes ad-hoc practice for AI-assisted delivery
- Amendments require a PR and tech-lead approval
- Complexity or constitution exceptions must be recorded in `plan.md` Complexity Tracking

**Version**: 1.0.0 | **Ratified**: 2026-09-03 | **Last Amended**: 2026-09-03
