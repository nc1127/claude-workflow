---
name: openapi-first
description: Draft or refine OpenAPI (or equivalent API contract) from BDD scenarios before implementation. Use to lock contracts prior to parallel FE/BE agents.
---

# OpenAPI first

## Goal
Produce a **locked API contract** aligned to BDD scenarios.

## Rules
- Contract describes behaviour, status codes, and error shapes consistent with existing APIs
- Mirror naming/auth patterns from neighbouring endpoints
- Do not implement handlers here unless asked
- Call out breaking changes explicitly

## Process
1. Read BDD scenarios
2. Find a mirror endpoint in repo
3. Draft paths, request/response schemas, error responses
4. Note auth requirements and idempotency
5. List types that must be shared with frontend

## Output template

```markdown
## Contract status
draft | ready-for-lock

## Endpoints
### METHOD /path
- Auth:
- Request:
- Responses:
  - 200/201:
  - 400:
  - 403:
  - 404:

## Shared types to export

## Breaking changes
none |

## Alignment to BDD
- Scenario X → endpoint Y
```
