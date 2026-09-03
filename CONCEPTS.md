# Concepts — shared language map

Use **delivery words** with stakeholders; use **Claude Code words** with engineers.

| Stakeholder term | Claude Code / kit term | What it is |
|---|---|---|
| Spec / BDD | `spec.md` | What to build; acceptance scenarios |
| Implementation plan | `plan.md` | How; includes Agent Orchestration |
| Task list | `tasks.md` | Ordered work with `[P]` + agent tags |
| Prompt library | `.claude/skills/` (+ `prompt-library/`) | Curated reusable procedures |
| Skill | `SKILL.md` | One library entry, loaded on demand |
| Agent orchestration brief | `plan.md` Agent Orchestration + `tasks.md` | What engineers/agents execute against |
| Context agents need | `context-pack.md` | Paths, mirrors, contracts, constraints |
| Context agent | `agents/context-agent.md` + `/context-pack` | Research-only pack builder |
| Guardrails | constitution + rules + plan | Hard constraints |
| Spec-driven / BDD | Spec Kit spine + scenarios | Behaviour + contract as source of truth |
| Agentic development | specialised agents + loops | Named workflows, not freestyle chat |
| Feature scaffolding | stub from contract/tasks | Vertical slice before fill |

---

## What loads when (Claude Code)

| Primitive | When loaded | Put here |
|---|---|---|
| `CLAUDE.md` | Always | Repo map, commands, norms (keep short) |
| `rules/` | Always or path-scoped | Must / must-not constraints |
| `skills/` | On invoke / match | Step-by-step procedures |
| `agents/` | When delegated | Role, tools mindset, success criteria |
| Brief | Pasted each ticket | Parallel graph + pack + gates |

**Rule of thumb:** facts → CLAUDE.md · constraints → rules · procedures → skills · workers → agents · this ticket → brief.
