---
name: review-all
description: Run the full specialised review pack (React/TS quality, security, performance, test coverage, documentation) and merge into one report. Use before merge on feature PRs.
---

# Review — all specialists

## Goal
Orchestrate parallel specialist reviews and produce one merged report.

## Process
1. Confirm diff + brief/BDD/contract context available
2. Apply each specialist checklist (or spawn subagents):
   - `/review-react-ts` (skip if no FE/TS changes)
   - `/review-security` (always for API/auth/PII touches; else light pass)
   - `/review-performance` (FE lists, APIs, heavy deps)
   - `/review-test-coverage` (always when behaviour changes)
   - `/review-documentation` (always when behaviour/API/flag changes)
3. Merge findings; dedupe; sort Blockers → Should fix → Nits
4. Any Blocker ⇒ do not approve

## Merged output template

```markdown
## Review pack (merged)
overall risk: low | medium | high
TTL human review required: yes/no

### Blockers
- [security|react-ts|performance|tests|docs] …

### Should fix
-

### Nits
-

### Specialist summary
| Specialist | Risk | Blockers |
|---|---|---|
| react-ts | | 0 |
| security | | 0 |
| performance | | 0 |
| test-coverage | | 0 |
| documentation | | 0 |

### Spec coverage
- BDD: yes/no/partial
- Contract: yes/no/partial
```
