# Agent 7 Brief — Match Logging, Turn Logs, Player Stats

## Mission
Implement structured match logging with turn-by-turn entries and baseline player analytics.

## PRD Mapping
- 6.7 Match Logging (with Turns)
- 9 Player analytics
- 12F Delivery sequence

## Required Deliverables
- Match metadata logging (rosters, result, map/objectives, notes).
- Config-driven turn count support.
- Per-turn typed entries (`type`, `label`, `value`, `tags`, `timestamp`).
- Quick and detailed logging modes.
- Player stats: overall W/L, by roster, by opponent, tac ops frequency/success.

## Acceptance Criteria
- Complete match log can be captured and edited.
- Turn entries are validated by type.
- Analytics update from saved logs.

## Tests (minimum)
- Turn-entry validation tests.
- Match-log persistence tests.
- Stats aggregation tests with fixture datasets.

## Dependencies
- Agent 4, Agent 6, Agent 1.

## Handoff
Provide stats definitions and aggregation query/job design.
