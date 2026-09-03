# AI Orchestration Kit (Claude Code + Spec Kit)

Paste-ready setup for a technical lead running **Spec-Driven Development** with **agentic** delivery.

Use this to:
- Follow **GitHub Spec Kit** shapes: constitution → spec → plan → tasks  
- Own **agent orchestration** inside `plan.md` (context, lanes, guardrails, skills)  
- Curate a **prompt library / skills** for your domain  
- Prove **effectiveness** of AI-directed delivery  

Official Spec Kit: https://github.com/github/spec-kit (MIT)

---

## Folder map

```text
claude-workflow/
├── README.md
├── SETUP.md
├── WORKFLOW.md
├── CONCEPTS.md
├── CHEATSHEET.md
├── templates/
│   ├── README.md                 ← Spec Kit alignment
│   ├── constitution.md
│   ├── spec.md
│   ├── plan.md                   ← includes Agent Orchestration
│   ├── tasks.md
│   ├── CONTEXT-PACK.md
│   └── ORCHESTRATION-BRIEF.md    ← migration pointer (legacy)
├── examples/
│   └── 128-archive-project/      ← full Spec Kit example
├── prompt-library/
└── .claude/                      ← Claude Code harness
```

---

## Quick start

1. Copy `.claude/` into your repo; edit `CLAUDE.md`.  
2. Copy `templates/constitution.md` → `.specify/memory/constitution.md` or `docs/constitution.md`.  
3. Per feature: copy `spec.md` `plan.md` `tasks.md` into `specs/[###-feature]/`.  
4. Run `/context-pack` → `context-pack.md`, lock plan, execute tasks.  
5. `/review-all` → flag/rollout → curate skills.  

Optional: install Spec Kit (`specify init`) and use `/speckit.*` commands with the same artefact shapes.

---

## Ownership (tech lead)

| Responsibility | Artefact |
|---|---|
| Spec-driven spine | `spec.md` / `plan.md` / `tasks.md` |
| Agent orchestration | `plan.md` → Agent Orchestration |
| Context agents need | `context-pack.md` + `/context-pack` |
| Guardrails | constitution + plan guardrails + `.claude/rules/` |
| Prompt library curation | `.claude/skills/` + `prompt-library/README.md` |
| Effectiveness | plan notes + WORKFLOW metrics |

---

## Agents at a glance

**Build:** context · api-implementer · ui-implementer · release-scaffolder  

**Review:** React/TS · security · performance · test coverage · documentation · `/review-all`

## One-liner

> We use Spec Kit artefacts for spec → plan → tasks, and embed agent orchestration in the plan—context packs, parallel lanes, guardrails, specialised reviews, and flagged rollouts—so AI delivery stays accountable.
