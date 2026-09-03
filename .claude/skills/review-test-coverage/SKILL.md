---
name: review-test-coverage
description: Review whether tests cover BDD scenarios and changed behaviour (authz, validation, happy path). Use before merge.
---

# Review — Test coverage

## Goal
Map acceptance behaviour to tests; flag critical gaps (not vanity coverage %).

## Check
- BDD scenarios → tests
- Authz + validation paths for mutations
- Behaviour assertions vs brittle implementation details
- Synthetic fixtures only
- Gaps from deleted/missing tests

## Output template

```markdown
## Test coverage
risk: low | medium | high

### Scenario coverage map
| Scenario | Covered by | Gap? |
|---|---|---|
| | | |

### Blockers
-

### Should fix
-

### Nits
-
```
