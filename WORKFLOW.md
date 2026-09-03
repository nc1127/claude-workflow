# Workflow — Spec Kit + AI orchestration

## Tech lead accountability

1. **Spec spine** — constitution, spec, plan, tasks (Spec Kit shapes)  
2. **Agent orchestration** — context, lanes, guardrails, skills (in `plan.md`)  
3. **Effectiveness** — quality/speed; curate skills when weak  
4. **Prompt library curation** — update `.claude/skills/` when patterns change  

---

## Per-ticket flow

```text
1. Ticket / PO intent
        ↓
2. spec.md  (BDD + requirements) → Status: Locked
        ↓
3. plan.md  (tech context + Agent Orchestration section)
   - constitution check
   - contracts & flag
        ↓
4. context-pack.md  (/context-pack)
   - human tech-lead checkpoint (authz / PII / migrations)
        ↓
5. tasks.md  ([P] parallel + agent tags)
        ↓
6. Fan-out implementers
   - api / ui / release skills + test loops
        ↓
7. Review pack (/review-all or specialists)
   - human trust-boundary sign-off
        ↓
8. Dark deploy + progressive rollout
        ↓
9. Effectiveness notes → skill curation
```

---

## Parallelisation rules

**Safe in parallel** (after contract + context pack locked):

- API + unit tests  
- UI + RTL  
- Flag / telemetry scaffolding  
- Review specialists  

**Keep sequential:**

- Auth / permission model changes  
- DB migrations / shared enums  
- Design-system public API changes  
- Privacy-sensitive exports  

---

## Daily sprint habits

| Moment | Practice |
|---|---|
| Refinement | Is `spec.md` clear enough to lock? |
| Sprint start | `plan.md` + `tasks.md` ready for top stories |
| Standup | Task/agent lane status + blockers |
| PR | Same checklist for AI and human diffs |
| End of week | Skill curation from repeated review misses |

---

## Bug vs feature

| Type | Artefacts |
|---|---|
| Tiny bug | Short tasks or waiver; full Spec Kit optional |
| Feature | Full `spec` → `plan` → `context-pack` → `tasks` |
| Risky (PII/export/auth) | Extra sequential security gate before fan-out |

---

## Effectiveness metrics

- % features with locked spec + plan before coding  
- First-pass CI green rate on AI-assisted PRs  
- Rework rounds (authz / tests / flag / DS)  
- Escapes / vulns from team code  
- Cycle time vs quality  

---

## Definition of Done

- [ ] `spec.md` locked; scenarios covered  
- [ ] Contract implemented  
- [ ] `tasks.md` complete for the slice  
- [ ] Tests green; lint/typecheck/SAST green  
- [ ] Feature flag default OFF (if user-facing)  
- [ ] Review pack done; tech-lead trust-boundary OK  
- [ ] No PII in fixtures/prompts  
- [ ] Effectiveness / skill update if needed  
