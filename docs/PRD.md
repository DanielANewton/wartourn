# WarTourn Product Requirements Document (PRD)

## 1) Product Overview
- **Working name:** WarTourn
- **Primary business driver:** Help tournament organizers launch successful events quickly (bookings, payments, scheduling) while giving players rich personal stats and game logs.
- **Initial game focus:** Kill Team
- **Design constraint:** The data model must extend to tabletop games with different roster structures, scoring systems, and turn counts.

## 2) Problem & Opportunity
### Problems today
- Organizers coordinate signups, payments, brackets, and scheduling across disconnected tools.
- League scheduling across multiple days is manually intensive.
- Players lack consistent systems for logging game metadata and per-turn outcomes.

### Opportunity
Build a single platform that:
1. Reduces organizer admin overhead and accelerates event launch.
2. Gives players deep, actionable match history and performance tracking.
3. Supports both structured tournaments and casual club-style play.

## 3) Goals & Non-Goals
### MVP Goals
- Organizer can create organizations, configure payouts, publish events/tournaments, invite members, collect fees, and manage attendance.
- Player can join/create organizations, manage rosters, and log matches with turn-by-turn data.
- Availability-based matchmaking can propose schedule slots while respecting pairing + table constraints.

### Phase 2+
- Multi-game template system (40K, AoS, Blood Bowl, etc.).
- Advanced competition systems (ELO/ladders, richer bracketing, scoring imports).
- Organizer storefront/discovery and marketing tools.

### MVP Non-Goals
- Full roster legality/rules validation.
- Complex judge/dispute real-time tooling.
- Deep third-party tournament platform integrations.

## 4) Personas
1. **Tournament Organizer** (primary buyer)
2. **Player / Competitor**
3. **Club Admin / Co-Organizer** (role-based access)

## 5) Core Concepts
- **Organization**: Group with members, roles, events, tournaments.
- **Event (Casual)**: RSVP-based session.
- **Tournament (Structured)**: Format + rounds + entrants + schedule/fees.
- **Roster**: Player team entity with game-specific fields.
- **Match**: Game instance between entrants.
- **Turn Log**: Flexible typed turn-by-turn data entries.

## 6) MVP Functional Scope
### 6.1 Organization System
- Create orgs (name, location, description, logo).
- Invite members by email/link.
- Roles: Owner, Admin, Organizer, Member.
- Dashboard includes upcoming events, tournaments, and member roster.

**Acceptance**
- Owner can invite/revoke.
- Owner/Admin can edit roles.
- Members can view authorized org events/tournaments.

### 6.2 Organizer Onboarding
- Guided wizard with save/resume.
- Steps: org setup → payment setup → first Kill Team tournament template.
- Completion checklist on organizer dashboard.

**Acceptance**
- New organizer can publish a paid tournament within 10 minutes (UX target).
- Test-mode/sandbox payment flow supported.

### 6.3 Payments & Bookings
- Entry fee amount/currency.
- Checkout + confirmation.
- Manual refunds and offline/cash payment marking.
- Finance view: revenue, fees, payouts, transaction list.

**Acceptance**
- Successful payment marks entrant as confirmed.
- Organizer can view entrant payment statuses.

### 6.4 Tournament Management
- Fields: name, game template, date range, venue, fee, capacity, registration window.
- Formats: Swiss, round-robin, single-elimination, league (availability scheduling).
- Upload rules pack.
- Generate pairings/matches by chosen format.
- Waitlist support (ordered queue).

### 6.5 Availability & Dynamic Matchmaking
- Availability window submission with timezone support.
- Suggest overlap slots for each required pairing.
- Respect constraints:
  - table capacity per slot
  - max matches per player/day
  - optional rest time
- Players confirm/decline proposals; organizer override available.
- Notification hooks: email + in-app.

### 6.6 Player Roster Library
- Create/edit/delete roster.
- Required fields: name, faction, notes + schema-driven payload.
- “Copy roster” flow for lightweight versioning.
- Attach roster to signup and logs.

### 6.7 Match Logging (with Turns)
- Match metadata: players, rosters, result, map setup, tac ops/objectives, notes.
- Configurable turn count from template (Kill Team default = 4).
- Per-turn typed entry structure:
  - `type`
  - `label`
  - `value` (number/string/boolean/json)
  - `tags[]` (optional)
  - `timestamp` (optional)
- UX modes: quick logging + detailed logging.

### 6.8 Casual Events
- Create events with date/time/location/capacity/tables.
- RSVP states: going/maybe/not going.
- Optional seat/table claiming up to capacity.

## 7) User Journeys
### Organizer happy path
Sign up → create org → configure payments → create tournament → publish → entrants book/pay → generate pairings → collect availability → confirm schedule → run matches.

### Player happy path
Sign up/join org → create roster → join/pay tournament → submit availability → confirm proposed slot → play/log match → view stats.

### Casual path
RSVP club event → claim spot (if available) → optionally log casual matches.

## 8) Data Model (High-Level)
Core entities:
- Users
- Organizations
- OrgMemberships
- Invitations
- GameSystems
- GameTemplates
- Rosters
- Events
- Tournaments
- Entrants
- AvailabilityWindows
- Matches
- MatchLogs
- TurnLogs
- Payments / Transactions

### Extensibility strategy
- Store game-specific data in `payloadJSON` keyed by `schemaVersion` from `GameTemplates`.
- Duplicate universal analytics fields at top level for query speed (result, score).

## 9) Analytics (MVP)
### Player
- Overall win/loss
- Win/loss by roster
- Win/loss by opponent (org scope)
- Tac Ops frequency + success flag (template-dependent)

### Organizer
- Registrations over time
- Capacity fill rate
- Payment completion rate
- No-show rate (manual status)

## 10) Permissions & Safety
- Org-level RBAC enforced on every write.
- Members can access only authorized events/tournaments and their own private roster notes.
- Tournament visibility defaults to org-only in MVP.

## 11) Non-Functional Requirements
- **Performance:** p95 < 500ms for key tournament/scheduling APIs.
- **Reliability:** idempotent payment webhooks + resilient booking confirmation.
- **Security:** invite token security + OWASP baseline.
- **Auditability:** log organizer actions (refunds, schedule overrides).
- **Compliance:** GDPR basics (export/delete policies).

## 12) MVP Delivery Sequence
A. Auth + org system
B. Organizer onboarding wizard
C. Tournament + booking + payments
D. Scheduling (league first)
E. Player roster library
F. Match + turn logging + basic stats
G. Casual events

## 13) Open Defaults (Unblocking Decisions)
- Turn count from game template (Kill Team = 4), with per-tournament override.
- MVP scoring stores winner + optional numeric score.
- Disputes handled by organizer manual edits.
- Refunds handled manually with transaction notes/status.

## 14) Minimum Acceptance Tests
1. Organizer can create org, set payouts, publish paid tournament.
2. Player can join/pay and be marked confirmed.
3. Organizer can generate pairings (league + swiss).
4. Availability overlap proposals can be created/confirmed.
5. Capacity constraints prevent overbooking.
6. Player can create match logs with turn-by-turn typed entries.
7. Player W/L stats update from logs.
8. Casual event RSVP and capacity enforcement work.
