---
name: react-form
description: Implement a React UI flow (form/modal/page section) using design-system components, RTL tests, and feature-flag awareness from BDD + Context pack.
---

# React form / UI flow

## Goal
UI that satisfies BDD behaviour, reuses DS, and stays flag-aware.

## Rules
- Prefer DS components listed in Context pack
- Labels, errors, keyboard access basics
- Do not redesign unrelated page chrome
- Feature flag default OFF behaviour respected
- Run web tests; loop until green or blocked

## Process
1. Confirm BDD + pack + API types available
2. Implement UI against existing patterns/mirrors
3. Wire loading/error/empty states consistently with domain
4. Add RTL tests for primary scenarios
5. Run tests; fix failures
6. Summarise files changed + a11y notes

## Done checklist
- [ ] BDD UI behaviours covered
- [ ] DS reused (or gap escalated)
- [ ] Flag-aware
- [ ] Tests green
