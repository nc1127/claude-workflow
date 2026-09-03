# Prompt library (domain index)

This is the **human-facing prompt library**.  
In Claude Code, the executable versions live in `.claude/skills/*/SKILL.md`.

**TTL ownership:** when review comments repeat twice, update the matching skill **and** this index note.

## Delivery skills

| ID | Name | When to use | Claude skill |
|---|---|---|---|
| PL-01 | BDD from ticket | Start of story | `/bdd-from-ticket` |
| PL-02 | OpenAPI first | Lock API before parallel work | `/openapi-first` |
| PL-03 | Context pack | Before FE/BE fan-out | `/context-pack` |
| PL-04 | API endpoint | Backend implementer loop | `/api-endpoint` |
| PL-05 | React form / UI | Frontend implementer loop | `/react-form` |
| PL-06 | Feature flag rollout | Dark deploy scaffolding | `/feature-flag-rollout` |

## Review skills (specialists)

| ID | Name | When to use | Claude skill |
|---|---|---|---|
| PL-07 | Review — React/TS quality | Frontend / shared TS diffs | `/review-react-ts` |
| PL-08 | Review — Security | Authz, PII, secrets, abuse | `/review-security` |
| PL-09 | Review — Performance | Render, bundle, API cost | `/review-performance` |
| PL-10 | Review — Test coverage | BDD ↔ tests gaps | `/review-test-coverage` |
| PL-11 | Review — Documentation | Specs, contracts, PR notes | `/review-documentation` |
| PL-12 | Review — All (orchestrator) | Feature PRs before merge | `/review-all` |
| PL-13 | PR review security (alias) | Back-compat → security | `/pr-review-security` |

## Curation log

| Date | Change | Why |
|---|---|---|
| 2026-09-03 | Split review into 5 specialists + `/review-all` | Need quality, security, perf, tests, docs coverage |
| YYYY-MM-DD | | |

## Tooling note

- Claude Code → skills  
- Codex / Cursor → copy the same procedure text from `.claude/skills/*/SKILL.md` into your tool’s prompt store  
- Keep one source of truth in git
