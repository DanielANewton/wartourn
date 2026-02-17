# Agent 4 Brief — Tournament Lifecycle

## Mission
Deliver tournament creation through pairing generation with capacity controls and waitlist handling.

## PRD Mapping
- 6.4 Tournament Management
- 7 Organizer journey
- 12C/12D prerequisites

## Required Deliverables
- Tournament CRUD and publish lifecycle.
- Format support: Swiss, round-robin, single-elimination, league.
- Pairing generation for league + swiss minimum.
- Waitlist queue and promotion behavior.
- Rules-pack attachment metadata.

## Acceptance Criteria
- Tournament can be configured and published.
- Entrant capacity/waitlist prevent overbooking.
- Pairings generate correctly for league and swiss.

## Tests (minimum)
- Capacity boundary tests.
- Waitlist promotion tests.
- Pairing generation tests for each MVP format.

## Dependencies
- Agent 1, Agent 3.

## Handoff
Publish tournament state machine and pairing invariants document.
