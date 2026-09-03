# Prompt library (domain index)

This is the **human-facing prompt library**.  
In Claude Code, the executable versions live in `.claude/skills/*/SKILL.md`.

**TTL ownership:** when review comments repeat twice, update the matching skill **and** this index note.

| ID | Name | When to use | Claude skill |
|---|---|---|---|
| PL-01 | BDD from ticket | Start of story | `/bdd-from-ticket` |
| PL-02 | OpenAPI first | Lock API before parallel work | `/openapi-first` |
| PL-03 | Context pack | Before FE/BE fan-out | `/context-pack` |
| PL-04 | API endpoint | Backend implementer loop | `/api-endpoint` |
| PL-05 | React form / UI | Frontend implementer loop | `/react-form` |
| PL-06 | Feature flag rollout | Dark deploy scaffolding | `/feature-flag-rollout` |
| PL-07 | PR review security | Pre-merge review agent | `/pr-review-security` |

## Curation log

| Date | Change | Why |
|---|---|---|
| YYYY-MM-DD | e.g. API skill must require audit event | Missed twice on reject/withdraw |

## Tooling note

- Claude Code → skills  
- Codex / Cursor → copy the same procedure text from `.claude/skills/*/SKILL.md` into your tool’s prompt store  
- Keep one source of truth in git
