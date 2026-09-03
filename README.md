# AI Orchestration Kit (Claude Code)

Paste-ready setup for a Technical Team Lead running **spec-driven + agentic** delivery.

Use this to:
- Own the **AI orchestration plan** per piece of work
- Produce an **agent orchestration brief** engineers execute against
- Curate a **prompt library / skills** for your domain
- Prove **effectiveness** of AI-directed delivery

---

## Folder map

```text
elmo-ai-orchestration-kit/
├── README.md                          ← you are here
├── SETUP.md                           ← install into a repo
├── WORKFLOW.md                        ← daily / sprint operating model
├── CONCEPTS.md                        ← prompt library vs skill vs agent vs brief
├── templates/
│   ├── ORCHESTRATION-BRIEF.md
│   └── CONTEXT-PACK.md
├── examples/
│   └── REC-441-reject-candidate.md
├── prompt-library/
│   └── README.md                      ← human-readable library index
└── .claude/
    ├── CLAUDE.md                      ← always-on project facts (keep short)
    ├── rules/                         ← hard constraints
    ├── skills/                        ← on-demand procedures (prompt library)
    └── agents/                        ← specialised agent role defs
```

---

## Quick start (5 minutes)

1. Copy `.claude/` into your repo root.
2. Edit `.claude/CLAUDE.md` paths/commands for your monorepo.
3. Read `WORKFLOW.md`.
4. For the next ticket: run skill `/context-pack` → fill `templates/ORCHESTRATION-BRIEF.md` → fan out agents.
5. After the PR: update skills if the same review comment appeared twice (curation).

---

## Ownership (TTL)

| JD responsibility | Artefact in this kit |
|---|---|
| AI orchestration plan | `WORKFLOW.md` + brief parallel graph |
| Agent orchestration brief | `templates/ORCHESTRATION-BRIEF.md` |
| Context agents need | `/context-pack` skill + context agent |
| Guardrails | `.claude/rules/` + brief Guardrails section |
| Prompt library curation | `.claude/skills/` + `prompt-library/README.md` |
| Effectiveness | metrics section in `WORKFLOW.md` |

---

## Suggested interview one-liner

> I run a Claude Code harness: short CLAUDE.md, path-scoped rules, a curated skill/prompt library, and specialised agents. Each ticket gets an orchestration brief—context pack first, then parallel implementers against locked BDD/OpenAPI, same quality gates as human code.
