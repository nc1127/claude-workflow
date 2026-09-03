# Workflow — AI orchestration operating model

## TTL accountability

For each piece of work you own:

1. **Orchestration plan** — parallel vs sequential, context, guardrails  
2. **Brief** — engineers execute against it  
3. **Effectiveness** — quality/speed metrics; fix skills if weak  
4. **Prompt library curation** — update skills when patterns change  

---

## Per-ticket flow

```text
1. Ticket / PO intent
        ↓
2. Spec lock
   - /bdd-from-ticket
   - /openapi-first   (or GraphQL equivalent)
   - Human TTL checkpoint on authz / PII / migrations
        ↓
3. Context pack
   - /context-pack  (context agent)
        ↓
4. Publish orchestration brief
   - templates/ORCHESTRATION-BRIEF.md
        ↓
5. Fan-out (parallel where safe)
   - api-implementer
   - ui-implementer
   - release-scaffolder (flag, metrics)
        ↓
6. Agent loops
   - implement → run tests → fix → until green or blocker
        ↓
7. Review (parallel specialists)
   - /review-react-ts
   - /review-security
   - /review-performance
   - /review-test-coverage
   - /review-documentation
   - or /review-all (orchestrator merges findings)
   - human TTL on trust boundaries
        ↓
8. Release safety
   - dark deploy + progressive rollout
   - 24h health check
        ↓
9. Retrospective on AI effectiveness
   - update skill/prompt library if repeated misses
```

---

## Parallelisation rules

**Safe in parallel** (after contract + context pack locked):

- API + unit tests  
- UI + RTL  
- Flag / telemetry scaffolding  

**Keep sequential:**

- Auth / permission model changes  
- DB migrations / shared enums  
- Design-system public API changes  
- Privacy-sensitive exports  

---

## Daily sprint habits

| Moment | Practice |
|---|---|
| Refinement | TTL notes whether work is agentic-ready (spec clear?) |
| Sprint start | Briefs written for top stories before coding |
| Standup | “Agent lane status + blockers,” not only human tasks |
| PR | Same checklist for AI and human diffs |
| End of week | Skill curation: merge repeated review comments into skills |

---

## Bug vs feature

| Type | Orchestration |
|---|---|
| Tiny bug | Often **no** parallel agents; one session + test loop |
| Feature | Full brief + context pack + parallel lanes |
| Risky (PII/export/auth) | Extra sequential privacy/security gate before fan-out |

---

## Effectiveness metrics (report to EM)

Track weekly:

- % stories with a written brief  
- First-pass CI green rate on AI-assisted PRs  
- Rework rounds (authz / tests / flag / DS misses)  
- Defect escapes / security vulns from team code  
- Cycle time trend (should not rise escapes)  

**Interpretation:** speed up + quality down ⇒ orchestration failed → fix briefs, skills, or gates.

---

## Definition of Done (AI-assisted story)

- [ ] BDD scenarios covered  
- [ ] Contract implemented  
- [ ] Tests green (unit + relevant e2e)  
- [ ] Lint / typecheck / SAST green  
- [ ] Feature flag default OFF (if user-facing)  
- [ ] No PII in fixtures/prompts  
- [ ] TTL review on trust boundaries  
- [ ] Observability/logging adequate  
- [ ] Skill/library update if a new recurring lesson  
