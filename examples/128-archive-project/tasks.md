# Tasks: Archive project

**Input**: `examples/128-archive-project/`  
**Prerequisites**: spec locked, plan locked, context-pack complete  

## Phase 1: Setup

- [x] T001 [human] Lock `spec.md`
- [x] T002 [human] Constitution check in `plan.md`
- [x] T003 [context] Generate `context-pack.md`
- [x] T004 [human] Tech-lead checkpoint on authz/audit

## Phase 2: Foundational

- [ ] T005 Add contract snippet under `contracts/`
- [ ] T006 [P] Export shared types
- [ ] T007 [release] Add `projects.archive_v1` default OFF

## Phase 3: User Story 1 - Archive with reason (P1)

### Tests

- [ ] T010 [P] [US1] [api] Tests: happy path, 403, validation
- [ ] T011 [P] [US1] [ui] RTL: archive modal scenarios

### Implementation

- [ ] T012 [P] [US1] [api] Archive handler + authz + validation + audit
- [ ] T013 [P] [US1] [ui] ArchiveModal with DS components
- [ ] T014 [US1] [human] Integrate API + UI

## Phase 4: Review & Release

- [ ] T020 [P] [review] `/review-all` (or specialists)
- [ ] T021 [human] Trust-boundary sign-off
- [ ] T022 [release] Dark deploy
- [ ] T023 [human] Progressive rollout go/no-go
- [ ] T024 [human] Effectiveness notes + skill curation if needed
