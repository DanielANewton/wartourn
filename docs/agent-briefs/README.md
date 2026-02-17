# WarTourn Agent Brief Pack (Execution-Ready)

This directory operationalizes `docs/PRD.md` into assignable briefs that can be handed to independent implementation agents.

## Contents
- `01-platform-foundations.md`
- `02-organizer-onboarding.md`
- `03-payments-bookings-finance.md`
- `04-tournament-lifecycle.md`
- `05-availability-matchmaking.md`
- `06-roster-library.md`
- `07-match-logging-and-stats.md`
- `08-casual-events-analytics-hardening.md`
- `execution-plan.md`
- `handoff-template.md`

## Usage
1. Assign one brief per implementation agent.
2. Require each agent to deliver the handoff template with evidence.
3. Validate completion against `execution-plan.md` gates.

## Brief Invariants (all agents)
- Keep scope to MVP unless marked explicitly as Phase 2+.
- Include API contracts and data model impacts in every PR.
- Include automated tests for acceptance criteria.
- Tag blocked items with dependency and owner.
