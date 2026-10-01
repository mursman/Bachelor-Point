# Bachelor Point — Implementation Roadmap

## Phase 0

Project foundation, Firebase, DI, routing, design system, errors, logging, cache.

## Phase 1

Authentication, phone verification, Google, profile, onboarding and privacy.

## Phase 2

Mess creation, membership, roles, Mess Hub, No-Mess Home, Manager Control Center.

## Phase 3

Discovery, search, filters, approximate location, Mess Detail, saved messes, join request, invitations, vacancy.

## Phase 4

Membership approval, rule acknowledgement, members, removal, leave, manager replacement.

## Phase 5

Meals, history, guest meals, corrections, settings, meal-rate calculation.

## Phase 6

Bazar, receipt upload/OCR hook, expenses, approvals, audit.

## Phase 7

Ledger, personal breakdown, payments, settlements, adjustments, fund, deficit, monthly closing.

## Phase 8

Constitution, rule changes, voting, manager election, announcements.

## Phase 9

Profiles, reputation, reviews, manager reputation, messaging, contact requests, notifications.

## Phase 10

To-Let listing, preview, publish, manage, contact, filled state.

## Phase 11

Safety/reporting, deleted-user and unavailable-content states, privacy.

## Phase 12

Hardening: concurrency, permissions, retries, offline, deletion, notifications, migration.

## Phase 13

Production: rules, indexes, backups, crash reporting, privacy policy, terms, support, release configuration.

## Vertical-slice order

Auth → Create Mess → Mess Hub → Membership → Meals → Bazar → Accounting → Discovery → Reviews → Messaging → To-Let → Governance → Hardening.

Keep the application runnable at every phase.
