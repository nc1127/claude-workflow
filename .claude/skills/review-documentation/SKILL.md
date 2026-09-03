---
name: review-documentation
description: Review whether specs, contracts, PR notes, and operator docs match the code change. Use before merge when behaviour or APIs change.
---

# Review — Documentation

## Goal
Catch doc/spec drift and missing rollout notes.

## Check
- `specs/` BDD updated if behaviour changed
- OpenAPI/GraphQL updated if API changed
- PR description: outcome, flag, tests, risks, rollback
- Stale docs contradicted by diff
- Useful comments only where non-obvious

## Output template

```markdown
## Documentation
risk: low | medium | high

### Blockers
-

### Should fix
-

### Nits
-

### Artefacts to update
- specs:
- contracts:
- PR/rollout notes:
```
