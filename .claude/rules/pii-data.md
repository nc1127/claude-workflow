---
paths:
  - "**/*.{ts,tsx,js,jsx,md}"
---

# PII / sensitive data guardrails

- Never use real user or customer data in prompts, logs, fixtures, or screenshots.
- Use clearly fake synthetic data (e.g. `Alex Example`, `user_test_001@example.com`).
- Do not paste production database rows, tokens, or secrets into the session.
- For exports/downloads/reports: require field allow-lists, authz, and retention notes in the spec before implementing.
- If a request would require real PII to proceed, stop and ask the human.
