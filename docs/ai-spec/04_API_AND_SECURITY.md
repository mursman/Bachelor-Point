# Bachelor Point — API, Security and Authorization

## Core rule

UI hiding is not authorization. Every sensitive operation is server-authorized.

Never trust client-provided:
- role
- userId
- messId
- balances
- totals
- reputation
- review eligibility
- membership state

## API shape

Use Firebase callable/server functions initially, while keeping commands REST-compatible.

Examples:

```
POST /v1/messes
GET /v1/messes/{messId}
PATCH /v1/messes/{messId}
POST /v1/messes/{messId}/join-requests
POST /v1/join-requests/{id}/accept
POST /v1/join-requests/{id}/decline
POST /v1/messes/{messId}/meals
POST /v1/mess-meal-corrections
POST /v1/messes/{messId}/bazar
POST /v1/bazar/{id}/approve
POST /v1/messes/{messId}/expenses
POST /v1/expenses/{id}/approve
POST /v1/messes/{messId}/payments
POST /v1/messes/{messId}/adjustments
POST /v1/messes/{messId}/cycles/{cycleId}/close
```

## Authorization

Any verified user can discover public messes, create a mess, save messes, request joining, manage own profile, request contact and report content.

Members can manage their own meals, guest meals, bazar submissions, corrections, payments, leave requests and eligible reviews.

Manager can manage members, approvals, settings, expenses, meal rate, announcements, governance and closing.

Assistant Manager permissions are explicit/configurable.

## Financial security

- No arbitrary client writes to authoritative totals.
- Server calculates balances.
- Server checks membership.
- Server checks cycle state.
- Server checks approval authority.
- Server prevents edits after closing.
- Adjustments require reason.

## Idempotency

Use mutation IDs/idempotency keys for:
- payments
- approvals
- closing
- role changes
- join acceptance
- meal mutations

Retries must not duplicate financial events.

## Concurrency

Use server transactions for last-seat acceptance, manager changes, approvals and closing.

## Privacy

Do not expose:
- exact DOB
- exact address without permission
- phone without permission
- private finances
- anonymous reviewer identity
- private ballots

Public location may use area/approximate coordinates.

## Rate limits

OTP, authentication, join requests, contact requests, messages, reviews, reports, invites and discovery queries need abuse controls.

## Firestore

Use least-privilege rules. Never use production-wide authenticated read/write rules.

## Secrets

No service credentials or admin keys in Flutter.

## Notifications

Avoid sensitive lock-screen details. Notifications must deep-link to the relevant entity.

## Deletion

Anonymize identity where required while retaining records necessary for accounting, audits and review integrity.
