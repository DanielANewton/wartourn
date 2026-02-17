# WarTourn Execution Plan (Agent-Oriented)

## Phase Gates

### Gate A — Foundations Ready
Owner: Agent 1
- Auth/org/invite/RBAC merged.
- Permission tests passing.
- Contract: role enum + permission matrix frozen.

### Gate B — Monetized Organizer Flow
Owners: Agents 2, 3, 4
- Organizer onboarding path complete.
- Tournament publish + paid registration complete.
- Pairing generation available for league + swiss.

### Gate C — Scheduling + Player Depth
Owners: Agents 5, 6, 7
- Availability proposals + confirmations complete.
- Roster library integrated with signup/logging.
- Match logs and player stats active.

### Gate D — MVP Hardening
Owner: Agent 8
- Casual events live.
- Organizer analytics dashboard live.
- Audit/compliance/performance evidence attached.

## Parallelization Rules
- Agents can proceed in parallel within each gate once dependencies are met.
- Cross-agent contract changes require coordinator approval and version bump.

## Cross-Agent Contracts
- Shared status enums (membership/payment/tournament/proposal/rsvp).
- Date-time standard: ISO 8601 UTC storage, localized render at UI.
- Error model: stable error codes for auth/validation/conflict/not-found.
- Audit event format: actor, action, entity, entityId, timestamp, metadata.

## Quality Bar
- Every acceptance criterion has at least one automated test.
- Every gate has a demo script + verification checklist.
- Deferred items must be labeled Phase 2+ with rationale.
