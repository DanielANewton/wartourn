# Agent 3 Brief — Payments, Bookings, Finance

## Mission
Implement fee collection and reliable payment confirmation tied to entrant status, plus organizer finance operations.

## PRD Mapping
- 6.3 Payments & Bookings
- 11 Reliability
- 12C Delivery sequence

## Required Deliverables
- Entry fee configuration and checkout flow.
- Idempotent webhook handler and reconciliation logic.
- Entrant status sync (pending/confirmed/refunded/offline-paid).
- Manual refund and cash/offline marking.
- Finance views (revenue, fees, payouts, transactions).

## Acceptance Criteria
- Successful payment marks entrant confirmed.
- Duplicate webhook events do not duplicate state transitions.
- Organizer can inspect and update payment states safely.

## Tests (minimum)
- Webhook idempotency tests.
- Status transition tests with invalid transition rejections.
- Finance aggregate tests against transaction fixtures.

## Dependencies
- Agent 1, Agent 4.

## Handoff
Provide payment-state machine and webhook retry/reconciliation runbook.
