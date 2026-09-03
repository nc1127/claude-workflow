# Spec Kit alignment

This repo follows **GitHub Spec Kit** artefact shapes (MIT):

`constitution` → `spec` → `plan` → `tasks` → implement

Plus our extensions for tech-lead **agent orchestration** (context pack, agent lanes, review pack, flags).

## Templates

| Spec Kit | Our file | Role |
|---|---|---|
| constitution | `templates/constitution.md` | Project non-negotiables |
| spec | `templates/spec.md` | What / BDD / requirements |
| plan | `templates/plan.md` | How + **Agent Orchestration** section |
| tasks | `templates/tasks.md` | Ordered tasks with `[P]` + agent tags |
| (extension) | `templates/CONTEXT-PACK.md` | Context pack body (also `context-pack.md` per feature) |

Per feature, copy into:

```text
specs/[###-feature-name]/
├── spec.md
├── plan.md
├── context-pack.md
├── tasks.md
└── contracts/
```

## Commands (if you install Spec Kit)

```text
/speckit.constitution
/speckit.specify
/speckit.plan
/speckit.tasks
/speckit.implement
```

You can fill the markdown templates manually or via Spec Kit commands — same shapes.

## What replaced the old brief

| Old | New |
|---|---|
| `ORCHESTRATION-BRIEF.md` (single file) | `spec.md` + `plan.md` (**Agent Orchestration** section) + `tasks.md` |

Engineers still “execute against the brief” — now the brief is the **locked plan + tasks**, Spec Kit style.
