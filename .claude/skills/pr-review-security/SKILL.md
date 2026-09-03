---
name: pr-review-security
description: Review a diff for authz, PII, validation, flags, tests, DS misuse, and scope creep. Use before merge on AI or human PRs.
---

# PR review (security & quality)

## Goal
Findings-first review against spec + Context pack + rules.

## Rules
- Prefer actionable findings over rewrites
- Separate **Blockers** vs **Nits**
- Trust-boundary issues → “needs TTL human review”
- Do not approve missing authz/tests on mutations

## Process
1. Read PR diff + brief/BDD/contract if provided
2. Check authz, validation, PII fixtures, flag default, tests, DS, scope
3. Output report template

## Output template

```markdown
## Summary
risk: low | medium | high

## Blockers
-

## Should fix
-

## Nits
-

## Spec coverage
- BDD covered: yes/no/partial
- Contract covered: yes/no/partial

## TTL human review required?
- authz/PII/migration: yes/no
```
