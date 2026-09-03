---
paths:
  - "**/*.{ts,tsx,js,jsx,md}"
---

# HR / PII guardrails

- Never use real candidate, employee, or customer data in prompts, logs, fixtures, or screenshots.
- Use clearly fake synthetic data (e.g. `Alex Candidate`, `candidate_test_001@example.com`).
- Do not paste production database rows, tokens, or secrets into the session.
- For exports/downloads/reports: require field allow-lists, authz, audit, and retention notes in the spec before implementing.
- If a request would require real PII to proceed, stop and ask the human.
