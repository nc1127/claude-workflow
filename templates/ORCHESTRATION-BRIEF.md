# Migration: orchestration brief → Spec Kit

The purpose-built single brief was replaced with Spec Kit artefacts.

## Old → new

| Old brief section | Spec Kit location |
|---|---|
| Outcome / Acceptance (BDD) | `spec.md` User Stories + Acceptance Scenarios |
| Contracts / flag | `plan.md` Contracts & Flags (+ `contracts/`) |
| Work graph / parallel agents | `plan.md` → **Agent Orchestration** |
| Context pack | `context-pack.md` (linked from plan) |
| Guardrails / skills / review | `plan.md` Agent Orchestration |
| Human checkpoints | `plan.md` + `tasks.md` Phase Review & Release |
| Effectiveness notes | `plan.md` Effectiveness notes |
| Task breakdown | `tasks.md` with `[P]` and `[api]/[ui]/…` |

## Engineer execute path

1. Read locked `spec.md`  
2. Read `plan.md` Agent Orchestration  
3. Execute assigned tasks in `tasks.md` with listed skills  
4. Attach `/review-all` before rollout tasks  
