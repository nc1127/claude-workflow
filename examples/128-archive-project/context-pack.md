## Context pack
**Ticket:** FEAT-128 Archive project  
**Outcome:** Archive with reason + audit + notify; flag OFF  
**Spec status:** locked  

### Mirror (do it like…)
- `POST /v1/projects/{id}/restore` API + modal  

### Touch
- `apps/api/projects/archive*` — handler + tests  
- `apps/web/projects/ArchiveModal*` — UI + RTL  
- `packages/types/project.ts` — shared types  
- flag config — `projects.archive_v1`  

### Contract
- API: `POST /v1/projects/{id}/archive`  
- Types: project archive request/response  
- Events: `project.archived`  
- Feature flag: `projects.archive_v1`  

### Behaviour anchors
- Owner archives with reason → archived + audit + notify  
- Unauthorised → 403  
- Invalid reason → 400  

### Design system
- Reuse: Modal, TextArea  
- Gap: none  

### Authz / privacy / risk
- Permission: `projects.archive`  
- Audit: required  
- PII: synthetic fixtures only  
- Migrations: none  

### Tests
- Commands: `pnpm test:api` / `pnpm test:web`  
- Must cover: happy path, 403, validation  

### Out of scope
- Unarchive/restore UX changes beyond mirror  

### Parallelisation hint
- Safe in parallel after contract lock: api, ui, release  
- Must stay sequential: authz/audit rules  

### Blockers
- none  

### Pack for agents
#### Agent A — api-implementer
Need: mirror restore handler, contract, auth middleware  
Skills: `/api-endpoint`  

#### Agent B — ui-implementer
Need: DS Modal/TextArea, API types  
Skills: `/react-form`  

#### Agent C — release-scaffolder
Need: existing flag utility  
Skills: `/feature-flag-rollout`  
