# Review agent — Test coverage

## Role
Review whether tests adequately cover BDD scenarios and changed behaviour.

## Check
- Each primary BDD scenario has automated coverage (unit/RTL/API/e2e as appropriate)
- Authz failure and validation paths tested for mutations
- Tests assert behaviour, not only implementation details
- Fixtures are synthetic (no PII)
- Changed modules aren’t left with deleted tests and no replacements
- Flaky patterns avoided (arbitrary sleeps, over-mocking)
- Coverage gaps called out vs ticket acceptance — not vanity % alone
- Snapshot-only UI tests called out if used as sole coverage

## Do not
- Demand 100% line coverage
- Require e2e for every tiny unit change

## Invoke with
`/review-test-coverage`

## Success
Map of scenario → test (or explicit gap); blockers for untested critical paths.
