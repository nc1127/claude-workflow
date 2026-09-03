---
name: review-security
description: Review a diff for authz, PII, secrets, validation, and sensitive-action audit gaps. Use before merge on AI or human PRs.
---

# Review — Security

## Goal
Security/privacy review of the diff (findings-first).

## Check
- Authz on mutations; validation at boundary
- Secrets/PII in code, logs, fixtures
- Audit/logging for sensitive actions
- Flag vs privileged paths
- XSS/injection basics; unsafe HTML
- Exports: allow-list, authz, retention

## Output template

```markdown
## Security
risk: low | medium | high

### Blockers
-

### Should fix
-

### Nits
-

### Human tech-lead review required?
- authz/PII/migration: yes/no

### Residual risks
-
```
