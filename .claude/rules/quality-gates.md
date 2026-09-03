# Quality gates (all code — AI or human)

Before considering work done:

1. Lint and typecheck pass for touched packages.
2. Unit/integration tests cover changed behaviour (happy path + authz/validation where relevant).
3. No secrets committed; no real PII in fixtures.
4. User-facing behaviour behind a feature flag unless TTL waives.
5. PR description states: spec references, flag name, test evidence, risks.
6. Security scan / SAST must be clean of new critical/high issues introduced by this change.
