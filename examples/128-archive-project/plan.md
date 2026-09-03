# Implementation Plan: Archive project

**Branch**: `128-archive-project` | **Date**: 2026-09-03 | **Spec**: [`./spec.md`](./spec.md)  
**Ticket**: `FEAT-128` | **Status**: Locked  

## Summary

Add `POST /v1/projects/{id}/archive` with authz, validation, audit, and notification; UI modal using design-system Modal + TextArea; ship behind `projects.archive_v1` (OFF).

## Technical Context

**Language/Version**: TypeScript  
**Primary Dependencies**: React, Node API  
**Testing**: API unit tests + RTL  
**Project Type**: web application  
**Constraints**: authz, audit, feature flag default OFF, synthetic fixtures only  

## Constitution Check

- [x] Spec locked with BDD scenarios
- [x] Same quality bar AI/human
- [x] PII rules (synthetic fixtures)
- [x] Feature flag planned
- [x] DS reuse (Modal + TextArea)
- [x] Scope limited to archive slice

## Project Structure

```text
specs/128-archive-project/
├── spec.md
├── plan.md
├── context-pack.md
├── tasks.md
└── contracts/
```

**Structure Decision**: `apps/api/projects/`, `apps/web/projects/`

## Contracts & Flags

- API: `POST /v1/projects/{id}/archive` body `{ "reason": "string 1..500" }`
- Event: `project.archived`
- Flag: `projects.archive_v1` (OFF)

## Agent Orchestration

### Context pack
See [`./context-pack.md`](./context-pack.md)

### Work graph

**Sequential:** spec lock → context pack → tech-lead authz/audit gate  

**Parallel lanes:**

| Lane | Agent | Skills | Scope |
|---|---|---|---|
| A | api-implementer | `/api-endpoint` | archive handler + tests |
| B | ui-implementer | `/react-form` | ArchiveModal + RTL |
| C | release-scaffolder | `/feature-flag-rollout` | flag + rollout notes |

### Guardrails

- Synthetic fixtures only; no new deps; flag default OFF; authz + audit required

### Review pack

`/review-all` then tech-lead trust-boundary sign-off

### Human checkpoints

- [ ] Contract/authz approved
- [ ] PR reviewed
- [ ] Rollout go/no-go

### Effectiveness notes

- Miss: audit field omitted once → updated `/api-endpoint` checklist to require audit on sensitive actions
