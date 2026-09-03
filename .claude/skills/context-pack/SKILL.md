---
name: context-pack
description: Research the codebase and produce a tight Context pack for implementer agents. Use before parallel FE/BE work or when an orchestration brief needs mirrors, paths, contracts, and constraints.
---

# Context pack

You are the **context / research agent**. Do **not** implement production feature code.

## Goal
Produce a minimum-viable **Context pack** so API/UI agents share one truth.

## Rules
- Signal over volume; cite paths instead of dumping files
- No real PII, secrets, or prod data
- Do not invent contracts — use **Blockers** if unclear
- Prefer existing design-system components
- Output **only** the template below

## Process
1. Read ticket / BDD / contract from the user
2. Find 1–2 golden mirror implementations
3. List touch paths, contract fragments, DS reuse, authz/PII, tests, out-of-scope, blockers
4. Add parallelisation hints

## Output template

```markdown
## Context pack
**Ticket:**
**Outcome:**
**Spec status:** locked | draft | blocked

### Mirror (do it like…)
-

### Touch
-

### Contract
- API/GraphQL:
- Types:
- Events:
- Feature flag:

### Behaviour anchors (from BDD)
-

### Design system
- Reuse:
- Gap:

### Authz / privacy / risk
- Permission(s):
- Audit/logging:
- PII: synthetic fixtures only
- Migrations:

### Tests
- Mirror tests:
- Commands:
- Must cover:

### Out of scope
-

### Guardrails for implementers
- No new dependencies without approval
- Same quality gates as human code

### Parallelisation hint
- Safe in parallel after contract lock:
- Must stay sequential:

### Blockers
-

### Pack for agents (copy into brief)
#### Agent A — api-implementer
Need:
Skills: `/api-endpoint`

#### Agent B — ui-implementer
Need:
Skills: `/react-form`

#### Agent C — release-scaffolder
Need:
Skills: `/feature-flag-rollout`
```
