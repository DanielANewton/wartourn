# Agent 1 Brief — Platform Foundations (Auth + Org + RBAC)

## Mission
Deliver secure identity, organization membership, invitations, and permission enforcement that all other tracks depend on.

## PRD Mapping
- 6.1 Organization System
- 10 Permissions & Safety
- 12A Delivery sequence

## Required Deliverables
- User + org + membership + invitation schemas/migrations.
- Auth/session implementation.
- Invite accept/revoke flows.
- Role management (Owner/Admin/Organizer/Member).
- RBAC middleware and write-path checks.

## Acceptance Criteria
- Owner can invite/revoke members.
- Owner/Admin can modify roles.
- Non-authorized members cannot write org resources.

## Tests (minimum)
- Unit tests for role policy matrix.
- Integration tests for invite lifecycle.
- Authorization rejection tests for every protected write endpoint.

## Dependencies
- None.

## Handoff
Submit `docs/agent-briefs/handoff-template.md` with endpoint list and policy table.
