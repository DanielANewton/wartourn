# Agent 6 Brief — Player Roster Library

## Mission
Enable reusable roster management with schema-driven payloads and roster reuse for entries/logs.

## PRD Mapping
- 6.6 Player Roster Library
- 8 Extensibility strategy
- 12E Delivery sequence

## Required Deliverables
- Roster CRUD (name, faction, notes, payload).
- Copy roster flow with linkage to source roster.
- Attachment hooks for signup and logging workflows.
- Schema version support in payload.

## Acceptance Criteria
- Users can maintain multiple rosters.
- Copied roster preserves ancestry metadata.
- Roster attach flows work in entrant + logging contexts.

## Tests (minimum)
- CRUD validation tests.
- Copy behavior tests.
- Schema-version read/write compatibility tests.

## Dependencies
- Agent 1, Agent 4.

## Handoff
Provide payload schema/version contract and roster-copy lineage behavior.
