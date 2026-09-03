# Agent orchestration brief

**Ticket:**  
**Owner (TTL):**  
**Engineers:**  
**Date:**  
**Spec status:** locked | draft | blocked  

---

## Outcome
One sentence: business + technical done state.

## Acceptance (BDD)
- Given … When … Then …
- Given … When … Then …
- Given … When … Then …

## Contracts
- OpenAPI / GraphQL:  
- Types / events:  
- Feature flag (default OFF):  

## Work graph

### Sequential
1. Spec lock (BDD + contract)
2. Context pack (`/context-pack`)
3. Human TTL checkpoint (authz / PII / migrations)

### Parallel (after checkpoint)
- Agent A — api-implementer:  
- Agent B — ui-implementer:  
- Agent C — release-scaffolder:  

### Then
- Integrate → review pack → TTL review → dark deploy → progressive rollout

### Review pack (parallel)
- [ ] `/review-react-ts` — React/TS quality
- [ ] `/review-security` — authz, PII, secrets
- [ ] `/review-performance` — render/API/bundle risks
- [ ] `/review-test-coverage` — BDD ↔ tests
- [ ] `/review-documentation` — specs/contracts/PR notes
- Or: `/review-all` then TTL trust-boundary sign-off  

```text
[spec] → [context pack] → [TTL gate]
                │
      ┌─────────┼─────────┐
   api-agent  ui-agent  release-agent
      └─────────┼─────────┘
            [review] → [flag OFF deploy] → [rollout]
```

---

## Context pack
> Paste output of `/context-pack` here (or attach link).

## Guardrails (hard)
- [ ] No secrets / prod data / real PII in prompts or fixtures  
- [ ] No new dependencies without approval  
- [ ] Authz + validation required on mutations  
- [ ] Tests required for changed behaviour  
- [ ] Lint / unit / SAST must pass  
- [ ] Feature flag required for user-facing behaviour  
- [ ] Do not change: _______________________________  

## Skills to use
- `/context-pack`
- `/api-endpoint` and/or `/react-form`
- `/feature-flag-rollout`
- `/review-all` (or individual `/review-*` specialists)

## Human checkpoints
- [ ] Architecture / contract approved by TTL  
- [ ] PR reviewed (TTL accountable)  
- [ ] Go/no-go for progressive rollout  

## Effectiveness notes (fill after)
- What AI got wrong:  
- Skill/library update needed:  
