# Feature Specification: Phase 1 Product Vision

**Feature Branch**: `001-phase1-product-vision`  
**Created**: 2026-02-10  
**Status**: Draft  
**Input**: Define the Phase 1 product vision for an app called Grove Log. The app exists to help home plant owners and bonsai enthusiasts track individual plants, their care history, and urgent risks. Explain the core problem it solves, who it is for, and what success looks like in the first release.

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Log and review a single plant (Priority: P1)

As a user, I want to add a plant, record care, and review its individual history.

**Why this priority**: This provides core functionality that everything else builds on.

**Independent Test**: Can be fully tested by having a new user add a plant, record at least one care event, close and reopen the app, and then find that plant and see its recorded care history without using any “today” or risk views.

**Acceptance Scenarios**:

1. **Given** a new user with no plants, **When** they create a new plant and record at least one care event for it, **Then** the plant appears in their list with the recorded care event visible in that plant’s history.
2. **Given** a user who previously created a plant and recorded at least one care event, **When** they reopen the app and open that plant, **Then** they see a chronological list of the care events associated with that plant.

---

### User Story 2 - See what needs attention today (Priority: P1)

As a user, I want to see a “today” view listing plants that are due/overdue for care, and be able to mark tasks as done

**Why this priority**: This is the primary day‑to‑day value of Grove Log, helping users see exactly what needs attention now without checking each plant individually.

**Independent Test**: Can be fully tested by seeding several plants with care intervals, opening the “today” view to see only due/overdue plants, marking at least one care task as done, and confirming it disappears from the “today” list and its next due time is updated without inspecting each plant individually.

**Acceptance Scenarios**:

1. **Given** a user with several plants where some are due or overdue for care and others are not, **When** they open the “today” view, **Then** only the plants that are due or overdue for care appear in the list.
2. **Given** a plant that appears in the “today” view as needing care, **When** the user records the required care action from the “today” view, **Then** that plant is removed from the “today” list and does not appear again until its next care is due.

---

### User Story 3 - Notice urgent risks before it’s too late (Priority: P2)

As a user, I want to highlight at-risk plants (e.g., very overdue watering) and clear the risk once care is recorded.

**Why this priority**: Clear visibility into urgent risks directly supports the goal of preventing avoidable plant loss, which is especially important for high‑value or fragile plants like bonsai.

**Independent Test**: Can be fully tested by preparing at least one plant with significantly overdue critical care, confirming it appears prominently as high risk with a short explanation, recording the required care, and confirming the risk indicator clears and the plant no longer appears in any urgent list.

**Acceptance Scenarios**:

1. **Given** a plant whose critical care is significantly overdue beyond a defined risk threshold, **When** the user opens the app, **Then** that plant is prominently flagged as high risk with a short explanation of the issue (for example, “watering overdue by several days”).
2. **Given** a plant that is currently flagged as high risk due to overdue care, **When** the user records the required care action, **Then** the high‑risk flag is cleared and the plant no longer appears in any urgent or high‑risk list.

---

### Edge Cases

- What happens when multiple plants share the same or very similar names?
- How does the system behave when a user skips logging care for an extended period?
- What happens when a user accidentally deletes a plant they still care about?

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: System MUST allow users to create, update, and archive plants.
- **FR-002**: System MUST allow users to record time‑stamped care events for each plant.
- **FR-003**: System MUST provide a “today” view of plants needing care.
- **FR-004**: System MUST highlight plants that are at elevated risk based on overdue care.
- **FR-005**: System MUST allow users to view each plant’s full care history.

### Key Entities

- **Plant**: Represents an individual plant or bonsai tree with identifying details such as name, species, and location.
- **Care Event**: Represents a single care action applied to a plant, including what was done and when.
- **User**: Represents the person managing plants in Grove Log and owning their associated data.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: ≥80% of new users who start onboarding log ≥3 plants in the first week.
- **SC-002**: ≥75% of weekly active users record at least one care event per week.
- **SC-003**: In usability tests, ≥90% of participants can add a plant and record care in under 5 minutes without help.
- **SC-004**: After 4 weeks, ≥70% of surveyed users say Grove Log helped them avoid missing important care for at least one plant.