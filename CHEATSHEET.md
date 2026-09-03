# Cheat sheet — run a story with this kit

```text
1) /bdd-from-ticket
2) /openapi-first          → TTL locks contract
3) /context-pack           → paste into brief
4) Fill templates/ORCHESTRATION-BRIEF.md and share with squad
5) Parallel:
     - api agent  + /api-endpoint
     - ui agent   + /react-form
     - release    + /feature-flag-rollout
6) Each agent: implement → test → fix loop
7) /pr-review-security + TTL trust-boundary review
8) Dark deploy → progressive rollout → 24h health
9) Update prompt-library curation log if needed
```

## Interview mapping

| They ask | You show |
|---|---|
| AI orchestration plan | WORKFLOW.md parallel rules |
| Agent brief | templates/ORCHESTRATION-BRIEF.md |
| Context agents need | `/context-pack` + agents/context-agent.md |
| Guardrails | `.claude/rules/*` |
| Prompt library | prompt-library/README.md + skills |
| Agentic / multi-file / loops | api-endpoint & react-form skills (test loops) |
| Spec-driven + BDD | bdd-from-ticket + openapi-first |
