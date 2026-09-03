---
name: api-endpoint
description: Implement a Node API endpoint/mutation from locked contract + Context pack, including validation, authz, tests, and agent test-fix loop.
---

# API endpoint

## Goal
Production-ready backend slice matching contract + BDD + Context pack.

## Rules
- Follow Mirror paths from the Context pack
- Enforce authz + input validation
- Synthetic fixtures only
- No new deps without approval
- Run tests; loop on failures until green or blocked

## Process
1. Confirm contract + pack present; stop if blocked
2. Scaffold/update handler, validation, service wiring
3. Add/adjust unit tests (happy path, 403, validation)
4. Run test command from pack / CLAUDE.md
5. Fix failures (autonomous loop)
6. Summarise files changed + remaining risks

## Done checklist
- [ ] Contract satisfied
- [ ] Authz covered by test
- [ ] Validation covered by test
- [ ] Audit/log if required
- [ ] Tests green
