# Project guide for Claude Code

Keep this file short. Procedures belong in skills. Constraints belong in rules.

## Product / domain
- Domain: (set your product domain)
- Sensitive data: user/customer PII — synthetic fixtures only

## Repo map
- `apps/web/` — React / Next frontend
- `apps/api/` — Node API
- `packages/types/` — shared types
- `packages/ds/` — design system (prefer existing components)

## Commands
- Install: `pnpm install`
- Lint: `pnpm lint`
- Typecheck: `pnpm typecheck`
- Unit tests: `pnpm test`
- API tests: `pnpm test:api`
- Web tests: `pnpm test:web`
- E2E (when needed): `pnpm test:e2e`

## Engineering norms
- Spec-driven: BDD scenarios + OpenAPI/GraphQL are source of truth
- AI and human code: same quality bar
- New user-facing behaviour: feature flag default OFF, dark deploy
- Prefer design-system components; new DS APIs need tech-lead approval
- No drive-by refactors outside the ticket

## Orchestration
- Start features with Spec Kit artefacts (`spec` → `plan` → `tasks`)
- Put agent lanes, guardrails, and skills in `plan.md` Agent Orchestration
- Run `/context-pack` before parallel FE/BE agents
- Trust-boundary changes (authz, PII, migrations) need human tech-lead review

## Where to look next
- Skills: `.claude/skills/`
- Rules: `.claude/rules/`
- Agent roles: `.claude/agents/`
- Brief template: use Spec Kit `spec.md` / `plan.md` / `tasks.md` under `specs/[###-feature]/`
- Agent orchestration lives in `plan.md` (Agent Orchestration section)
