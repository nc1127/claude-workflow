---
name: feature-flag-rollout
description: Add feature-flag scaffolding and progressive rollout notes for dark deploy. Use for new user-facing behaviour.
---

# Feature flag rollout

## Goal
Make the change **dark-deployable** with a clear progressive rollout plan.

## Rules
- Default OFF in production-like configs
- Use existing flag utilities/patterns in repo
- Do not enable globally in the PR
- Document go/no-go signals (errors, latency, support noise)

## Process
1. Add flag name from brief/pack
2. Gate UI and/or API behaviour as domain requires
3. Add minimal metrics/log markers if pattern exists
4. Write rollout plan in PR description

## Output for PR

```markdown
## Flag
- Name:
- Default: OFF

## Rollout plan
1. Deploy dark
2. Enable 10% / internal tenant
3. Monitor 24h (errors, p95, complaints)
4. 50% → 100% or rollback

## Rollback
- Disable flag immediately; no hotfix required for disable path
```
