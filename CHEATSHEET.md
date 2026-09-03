# Cheat sheet — Spec Kit + agent orchestration

```text
0) constitution (once per repo)     → templates/constitution.md
1) spec.md                          → BDD / requirements (Status: Locked)
2) plan.md                          → tech plan + Agent Orchestration section
3) /context-pack                    → context-pack.md
4) tasks.md                         → [P] parallel + [api]/[ui]/[release]/[review]
5) Implement lanes with skills:
     /api-endpoint  /react-form  /feature-flag-rollout
6) Review: /review-all (or specialists)
7) Dark deploy → progressive rollout
8) Effectiveness notes → curate skills
```

## Per-feature folder

```text
specs/[###-feature]/
├── spec.md
├── plan.md          ← includes Agent Orchestration
├── context-pack.md
├── tasks.md
└── contracts/
```

## Review agents

| Agent | Skill |
|---|---|
| review-react-ts-quality | `/review-react-ts` |
| review-security | `/review-security` |
| review-performance | `/review-performance` |
| review-test-coverage | `/review-test-coverage` |
| review-documentation | `/review-documentation` |
| review-agent (orchestrator) | `/review-all` |

## Explainability mapping

| Topic | Where |
|---|---|
| Spec-driven spine | `templates/spec.md` `plan.md` `tasks.md` |
| Agent orchestration | `plan.md` → Agent Orchestration |
| Context agents need | `context-pack.md` + `/context-pack` |
| Prompt library | `prompt-library/` + `.claude/skills/` |
| Review pack | `.claude/agents/review-*.md` |
