# Agent 8 Brief — Casual Events, Organizer Analytics, Hardening

## Mission
Close out MVP with casual event workflows, organizer insights, and non-functional safeguards.

## PRD Mapping
- 6.8 Casual Events
- 9 Organizer analytics
- 11 Non-functional requirements
- 12G Delivery sequence

## Required Deliverables
- Casual event CRUD and RSVP states.
- Optional table/seat claiming with capacity enforcement.
- Organizer metrics (registration trend, fill rate, payment completion, no-show).
- Audit logging for critical organizer actions.
- GDPR basics (export/delete hooks) and OWASP baseline controls.

## Acceptance Criteria
- RSVP + seat capacity controls are enforced.
- Organizer metrics are reproducible from source data.
- Audit/security/compliance baseline is documented and active.

## Tests (minimum)
- RSVP capacity tests.
- Metric correctness tests.
- Audit emission tests for critical actions.

## Dependencies
- Agent 1, Agent 3, Agent 4/5/7.

## Handoff
Submit compliance/audit runbook and performance check results for key APIs.
