# Implementation Plan: [FEATURE]

**Branch**: `[###-feature-name]` | **Date**: [DATE] | **Spec**: [`./spec.md`](./spec.md)  
**Ticket**: `[JIRA/ISSUE-ID]` | **Status**: Draft | Locked  

**Input**: Feature specification from `/specs/[###-feature-name]/spec.md`

## Summary

[Primary requirement + technical approach]

## Technical Context

**Language/Version**: TypeScript / Node (adjust)  
**Primary Dependencies**: React, Node API framework (adjust)  
**Storage**: [if applicable]  
**Testing**: unit / RTL / API / e2e as required  
**Target Platform**: Web  
**Project Type**: web application (frontend + backend)  
**Performance Goals**: [domain-specific or N/A]  
**Constraints**: authz, PII, feature flag default OFF  
**Scale/Scope**: [this slice only]

## Constitution Check

*GATE: Must pass before research/design. Re-check after design.*

- [ ] Spec-driven: acceptance scenarios + contract approach defined
- [ ] Same quality bar for AI and human code
- [ ] PII/secrets rules respected
- [ ] Feature flag / safe release planned for user-facing behaviour
- [ ] DS reuse preferred; new DS API needs approval
- [ ] No unjustified complexity

## Project Structure

### Documentation (this feature)

```text
specs/[###-feature]/
├── spec.md              # What / BDD / requirements
├── plan.md              # This file
├── research.md          # Optional Phase 0
├── data-model.md        # Optional Phase 1
├── quickstart.md        # Optional Phase 1
├── contracts/           # OpenAPI / GraphQL snippets
├── context-pack.md      # Output of /context-pack
└── tasks.md             # Phase 2 task list with [P] + agent lanes
```

### Source Code (repository root)

```text
apps/api/ … 
apps/web/ …
packages/types/ …
packages/ds/ …
```

**Structure Decision**: [document real paths]

## Contracts & Flags

- API/GraphQL:  
- Events:  
- Feature flag (default OFF):  

---

## Agent Orchestration *(extension — required for AI-assisted delivery)*

> This section is what engineers and agents execute against after the plan is locked.
> It replaces the old single “orchestration brief” file.

### Context pack
Paste `/context-pack` output or link [`./context-pack.md`](./context-pack.md).

### Work graph

**Sequential (must finish before fan-out)**
1. Spec locked (`spec.md` Status: Locked)
2. Constitution check passed
3. Context pack complete
4. Human tech-lead checkpoint (authz / PII / migrations)

**Parallel agent lanes (after checkpoint)**
| Lane | Agent | Skills | Scope |
|---|---|---|---|
| A | api-implementer | `/api-endpoint` | |
| B | ui-implementer | `/react-form` | |
| C | release-scaffolder | `/feature-flag-rollout` | flag, rollout notes |

```text
[spec] → [plan + context pack] → [tech lead gate]
                │
      ┌─────────┼─────────┐
   api-agent  ui-agent  release-agent
      └─────────┼─────────┘
            [review] → [flag OFF deploy] → [rollout]
```

### Guardrails (hard)
- [ ] No secrets / prod data / real PII in prompts or fixtures
- [ ] No new dependencies without approval
- [ ] Authz + validation on mutations
- [ ] Tests for changed behaviour
- [ ] Lint / unit / SAST must pass
- [ ] Feature flag for user-facing behaviour
- [ ] Do not change: _______________________________

### Review pack (parallel)
- [ ] `/review-react-ts`
- [ ] `/review-security`
- [ ] `/review-performance`
- [ ] `/review-test-coverage`
- [ ] `/review-documentation`
- Or `/review-all` → tech-lead trust-boundary sign-off

### Human checkpoints
- [ ] Architecture / contract approved by tech lead
- [ ] PR reviewed (tech lead accountable)
- [ ] Go/no-go for progressive rollout

### Effectiveness notes *(fill after)*
- What AI got wrong:  
- Skill/library update needed:  

---

## Complexity Tracking

> Fill ONLY if Constitution Check has violations that must be justified

| Violation | Why Needed | Simpler Alternative Rejected Because |
|-----------|------------|-------------------------------------|
| | | |
