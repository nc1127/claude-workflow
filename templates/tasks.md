# Tasks: [FEATURE NAME]

**Input**: Design documents from `/specs/[###-feature-name]/`  
**Prerequisites**: `plan.md` (required), `spec.md` (required), `context-pack.md` (required for AI fan-out), `contracts/`  

**Organization**: Tasks are grouped by phase and user story so work can be implemented and tested independently.

## Format: `[ID] [P?] [Story?] [Agent?] Description`

- **[P]**: Can run in parallel (different files, no unfinished dependencies)
- **[Story]**: User story id (e.g. US1)
- **[Agent]**: `context` | `api` | `ui` | `release` | `review` | `human`
- Include exact file paths in descriptions

## Path Conventions

Adjust to repo layout from `plan.md` (e.g. `apps/api/`, `apps/web/`).

---

## Phase 1: Setup

**Purpose**: Align artefacts and shared types

- [ ] T001 [human] Lock `spec.md` status to Locked
- [ ] T002 [human] Pass constitution check in `plan.md`
- [ ] T003 [P] [context] Generate `context-pack.md` via `/context-pack`
- [ ] T004 [human] Tech-lead checkpoint on authz / PII / migrations

**Checkpoint**: Ready for foundational + story work

---

## Phase 2: Foundational (Blocking)

**Purpose**: Shared prerequisites before parallel story implementation

**CRITICAL**: No parallel US implementation until this phase completes

- [ ] T005 Add/confirm OpenAPI or GraphQL contract under `contracts/`
- [ ] T006 [P] Export shared types used by API and UI
- [ ] T007 [release] Add feature flag default OFF

**Checkpoint**: Foundation ready — user stories may proceed (respect [P] and agent lanes)

---

## Phase 3: User Story 1 - [Title] (Priority: P1) 🎯 MVP

**Goal**: [what this story delivers]  
**Independent Test**: [how to verify alone]

### Tests for User Story 1

- [ ] T010 [P] [US1] [api] API tests for happy path + 403 + validation
- [ ] T011 [P] [US1] [ui] RTL tests for primary acceptance scenarios

### Implementation for User Story 1

- [ ] T012 [P] [US1] [api] Implement endpoint/handler + authz + validation (`apps/api/...`)
- [ ] T013 [P] [US1] [ui] Implement UI flow using DS components (`apps/web/...`)
- [ ] T014 [US1] [api] Audit/logging if required
- [ ] T015 [US1] [human] Integrate API + UI against locked contract

**Checkpoint**: US1 independently testable

---

## Phase 4: Review & Release

- [ ] T020 [P] [review] `/review-react-ts`
- [ ] T021 [P] [review] `/review-security`
- [ ] T022 [P] [review] `/review-performance`
- [ ] T023 [P] [review] `/review-test-coverage`
- [ ] T024 [P] [review] `/review-documentation`
- [ ] T025 [review] Or single `/review-all` and attach report
- [ ] T026 [human] Tech-lead trust-boundary sign-off
- [ ] T027 [release] Dark deploy (flag OFF)
- [ ] T028 [human] Progressive rollout go/no-go (10% → … → 100%)
- [ ] T029 [human] Effectiveness notes in `plan.md` + skill curation if needed

---

## Dependencies & Parallel Example

```text
T001 → T002 → T003 → T004 → T005/T006/T007
                              ↓
                     T012[P][api] ∥ T013[P][ui]
                              ↓
                            T015
                              ↓
                   T020–T024[P][review] → T026 → T027 → T028
```

## Notes

- Do not start [P] tasks that share unresolved contract/authz decisions
- Agent lanes use skills listed in `plan.md` Agent Orchestration section
