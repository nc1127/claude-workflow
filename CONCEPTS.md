# Concepts — shared language map

Use **delivery words** with stakeholders; use **Claude Code words** with engineers.

| Stakeholder term | Claude Code / kit term | What it is |
|---|---|---|
| Prompt library | `.claude/skills/` (+ `prompt-library/`) | Curated reusable procedures |
| Skill | `SKILL.md` | One library entry, loaded on demand |
| Agent orchestration brief | `ORCHESTRATION-BRIEF.md` | Per-ticket playbook engineers execute |
| Context agents need | Context pack | Paths, mirrors, contracts, constraints |
| Context agent | `agents/context-agent.md` + `/context-pack` | Research-only pack builder |
| Guardrails | `.claude/rules/` + hooks + brief rules | Hard constraints |
| Spec-driven / BDD | scenarios + OpenAPI first | Behaviour + contract as source of truth |
| Agentic development | specialised agents + loops | Named workflows, not freestyle chat |
| Autonomous agent loop | edit → test → fix → repeat | Self-correct until green or blocked |
| Feature scaffolding | stub files from spec | Vertical slice skeleton before fill |

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
