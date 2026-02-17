# Agent 5 Brief — Availability Scheduling & Matchmaking

## Mission
Implement availability collection and constraint-aware slot proposals for league-style scheduling.

## PRD Mapping
- 6.5 Availability & Dynamic Matchmaking
- 12D Scheduling

## Required Deliverables
- Availability window input with timezone-safe normalization.
- Overlap engine for required pairings.
- Constraints: table count, max matches/day, optional rest time.
- Player confirm/decline workflow.
- Organizer override and audit trail.

## Acceptance Criteria
- Valid overlap proposals can be generated.
- Constraint violations are rejected.
- Organizer overrides are recorded.

## Tests (minimum)
- Timezone normalization tests.
- Constraint solver tests.
- Proposal lifecycle tests.

## Dependencies
- Agent 4, Agent 1 (optional Agent 3 coupling).

## Handoff
Deliver algorithm assumptions and proposal-state transition table.
