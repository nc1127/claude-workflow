---
name: review-performance
description: Review a diff for React and API performance risks (renders, bundle, N+1, over-fetch). Use before merge on user-facing or data-heavy changes.
---

# Review — Performance

## Goal
Identify meaningful performance risks; avoid premature micro-optimisation nits.

## Check
- Hot-path re-renders; expensive render work
- List virtualisation when needed by pattern
- API N+1, missing pagination, unbounded queries
- Heavy imports / bundle regressions
- Duplicate network calls

## Output template

```markdown
## Performance
risk: low | medium | high

### Blockers
-

### Should fix
-

### Nits
-

### Evidence / assumption
-
```
