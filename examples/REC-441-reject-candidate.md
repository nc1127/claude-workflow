# Example — REC-441 Reject candidate (filled brief)

**Ticket:** REC-441 Reject candidate with reason + notify HM  
**Owner (TTL):** Nick  
**Spec status:** locked  

## Outcome
Authorised hiring managers can reject a candidate with a reason; audit is written; HM notification queued; shipped dark behind a flag.

## Acceptance (BDD)
- Given an authorised HM on candidate C, When they reject with reason "Not a fit", Then C is rejected, audit stores actor+reason, notification is queued
- Given a user without permission, When they reject, Then 403
- Given reason empty/too long, When they submit, Then 400 with validation error

## Contracts
- `POST /v1/candidates/{id}/reject` body `{ "reason": "string 1..500" }`
- Event/notification: `candidate.rejected`
- Flag: `recruitment.reject_candidate_v1` (OFF)

## Work graph

### Sequential
1. BDD + OpenAPI locked  
2. `/context-pack`  
3. TTL checkpoint on authz + audit  

### Parallel
- Agent A api-implementer — reject handler + tests  
- Agent B ui-implementer — RejectModal + RTL  
- Agent C release-scaffolder — flag + rollout notes  

## Context pack (sample)
**Mirror:** `withdrawCandidate` API + modal  
**Touch:** reject route/tests, RejectModal, types, flags  
**DS:** Modal + TextArea  
**Authz:** `candidates.reject`  
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
