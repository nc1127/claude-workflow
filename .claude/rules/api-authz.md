---
paths:
  - "apps/api/**"
  - "**/resolvers/**"
  - "**/routes/**"
---

# API authz & mutation rules

- Every mutating endpoint must enforce authorisation explicitly; do not rely on UI hiding alone.
- Validate inputs at the boundary (schema/validator). Reject with clear 4xx errors.
- Prefer mirroring existing auth middleware and permission naming in this codebase.
- Sensitive actions (reject, delete, export, permission changes) must write an audit/log event when the domain pattern requires it.
- Do not weaken auth checks to make tests pass — fix fixtures/permissions instead.
- Do not introduce new dependency packages without human approval.
