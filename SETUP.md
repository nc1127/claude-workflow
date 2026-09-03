# Setup — copy into a repo

## 1. Copy files

From this kit, copy into your application repo root:

```bash
cp -R .claude /path/to/your-repo/
# optional: keep templates/examples for the team wiki
cp -R templates examples prompt-library /path/to/your-repo/docs/ai-orchestration/
```

## 2. Edit project facts

Open `.claude/CLAUDE.md` and replace placeholders:

- monorepo layout
- test / lint / typecheck commands
- design-system package name
- feature-flag helper path
- domain name (e.g. Recruitment)

## 3. Enable Claude Code

```bash
# install Claude Code if needed, then in repo:
claude
```

Confirm skills appear (name/description only at session start):

- `context-pack`
- `bdd-from-ticket`
- `openapi-first`
- `api-endpoint`
- `react-form`
- `feature-flag-rollout`
- `pr-review-security`

## 4. Team agreement (Definition of Done for AI work)

Add to team wiki / CONTRIBUTING:

1. No feature work starts without an **orchestration brief** (or TTL waiver for tiny bugs).
2. **Context pack** required before parallel FE/BE agents.
3. BDD scenarios + contract are source of truth.
4. AI-generated and human code use the **same** PR checklist and CI gates.
5. Feature flags: new user-facing behaviour deploys **dark** by default.
6. No prod/PII data in prompts or fixtures.
7. Skills/prompts are versioned in git; TTL owns curation for the domain.

## 5. Optional: prompt-library mirror

If some engineers use Codex/Cursor instead of Claude Code:

- Keep `prompt-library/*.md` as the **canonical text**
- Claude Code `skills/*/SKILL.md` should stay in sync with those files
- TTL reviews both in the same PR when changing a procedure

## 6. Smoke test

Pick a small ticket and run:

```text
/context-pack
```

Paste a fake ticket + 2 BDD scenarios. Confirm the pack fills the template without implementing code.
