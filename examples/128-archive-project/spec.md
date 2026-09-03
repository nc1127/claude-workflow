# Feature Specification: Archive project

**Feature Branch**: `128-archive-project`  
**Ticket**: `FEAT-128`  
**Created**: 2026-09-03  
**Status**: Locked  
**Owner (tech lead)**:  

**Input**: Allow project owners to archive a project with a reason and notify the owner.

## User Scenarios & Testing

### User Story 1 - Archive with reason (Priority: P1)

Authorised owners archive a project and stakeholders can see it was archived with a reason.

**Why this priority**: Core value of the feature  
**Independent Test**: Archive one project as owner; verify status, audit, notification  

**Acceptance Scenarios**:

1. **Given** an authorised owner on project P, **When** they archive with reason "Completed", **Then** P is archived, audit stores actor+reason, and a notification is queued
2. **Given** a user without permission, **When** they archive, **Then** they receive 403
3. **Given** reason empty or too long, **When** they submit, **Then** they receive 400 with validation error

### Edge Cases

- Project already archived?
- Concurrent archive requests?

## Requirements

### Functional Requirements

- **FR-001**: System MUST allow authorised owners to archive a project with a reason (1..500 chars)
- **FR-002**: System MUST write an audit event with actor and reason
- **FR-003**: System MUST queue a notification to the project owner
- **FR-004**: System MUST reject unauthorised archive attempts with 403

### Key Entities

- **Project**: id, status (`active` \| `archived`), …
- **Archive action**: actor, reason, timestamp

## Success Criteria

- **SC-001**: Owner completes archive in one flow without support intervention
- **SC-002**: Unauthorised users cannot archive (automated test)

## Assumptions

- Restore/unarchive is out of scope for this slice
- Existing notification pipeline is reused
