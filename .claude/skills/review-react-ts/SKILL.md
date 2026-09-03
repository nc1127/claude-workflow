---
name: review-react-ts
description: Review React and TypeScript code quality in a diff. Use on frontend or shared TS PRs before merge.
---

# Review — React / TypeScript quality

## Goal
Findings-first review of React + TypeScript quality against project conventions and the Context pack.

## Check
- Unjustified `any`; weak prop typing
- Hooks rules and effect correctness
- Component structure; DS reuse vs one-off UI
- Error/loading/empty states
- A11y basics on forms/modals
- Scope creep / dead code

## Output template

```markdown
## React/TS quality
risk: low | medium | high

### Blockers
-

### Should fix
-

### Nits
-

### Notes
-
```
