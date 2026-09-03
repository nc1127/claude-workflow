---
name: bdd-from-ticket
description: Turn a Jira/PO ticket into BDD Given/When/Then scenarios and edge cases. Use at the start of a story before coding or context packing.
---

# BDD from ticket

## Goal
Convert intent into **behaviour specs** that become the source of truth for agents and tests.

## Rules
- Write from user/system behaviour, not implementation steps
- Include authz failure and validation/empty cases
- Mark unknowns as questions — do not invent product policy
- Keep language understandable to PO/QA

## Process
1. Restate outcome in one sentence
2. List primary actor(s) and permissions assumptions
3. Write happy-path scenarios
4. Write failure/edge scenarios (403, validation, not found, idempotency if relevant)
5. List open questions for tech lead/PO

## Output template

```markdown
## Outcome

## Actors & permissions (assumed)

## Scenarios
### Scenario: …
Given …
When …
Then …

### Scenario: …
Given …
When …
Then …

## Edge / abuse cases
-

## Non-functionals
- Flag:
- Audit/logging:
- Performance notes:

## Open questions
-
```
