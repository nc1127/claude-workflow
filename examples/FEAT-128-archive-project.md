# Example — FEAT-128 Archive project (filled brief)

**Ticket:** FEAT-128 Archive project with reason + notify owner  
**Owner (tech lead):**  
**Spec status:** locked  

## Outcome
Authorised project owners can archive a project with a reason; audit is written; owner notification is queued; shipped dark behind a flag.

## Acceptance (BDD)
- Given an authorised owner on project P, When they archive with reason "Completed", Then P is archived, audit stores actor+reason, notification is queued
- Given a user without permission, When they archive, Then 403
- Given reason empty/too long, When they submit, Then 400 with validation error

## Contracts
- `POST /v1/projects/{id}/archive` body `{ "reason": "string 1..500" }`
- Event/notification: `project.archived`
- Flag: `projects.archive_v1` (OFF)

## Work graph

### Sequential
1. BDD + OpenAPI locked  
2. `/context-pack`  
3. Tech-lead checkpoint on authz + audit  

### Parallel
- Agent A api-implementer — archive handler + tests  
- Agent B ui-implementer — ArchiveModal + RTL  
- Agent C release-scaffolder — flag + rollout notes  

## Context pack (sample)
**Mirror:** `POST /v1/projects/{id}/restore` API + modal  
**Touch:** archive route/tests, ArchiveModal, types, flags  
**DS:** Modal + TextArea  
**Authz:** `projects.archive`  
**Tests:** `pnpm test:api` / `pnpm test:web`  
**Sequential still:** none beyond authz already locked  
**Blockers:** none  

## Guardrails
- Synthetic fixtures only  
- No new deps  
- Flag default OFF  
- Same CI gates  

## Skills
`/context-pack` → `/api-endpoint` + `/react-form` + `/feature-flag-rollout` → `/review-all` (react-ts, security, performance, test-coverage, documentation)

## Effectiveness notes (after)
- Miss: audit field omitted once → updated `/api-endpoint` done checklist to require audit when sensitive action
