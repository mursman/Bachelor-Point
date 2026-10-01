# Bachelor Point — AI Build Specification

## Purpose

Bachelor Point is a Flutter mobile app for Bangladesh with two connected products: 1. **Find a Mess** — discover, compare, contact and join a mess. 2. **Run a Mess** — manage members, meals, bazar, expenses, accounting, rules, reviews and vacancies.

## Non-negotiable principles

- Flutter mobile application.
- Firebase-first architecture.
- Phone authentication + Google authentication.
- Phone verification mandatory.
- One active mess per user at a time.
- Historical memberships retained.
- Anyone can create a mess; creator becomes Manager.
- Exactly one Manager per mess.
- Roles: Manager, Assistant Manager, Member.
- Joining requires Manager approval.
- Public/private mess visibility.
- Financial records transparent to current members within privacy boundaries.
- App records payments; it does not process money.
- No wallet or payment gateway in MVP.
- Server-authoritative financial calculations.
- Financial events become immutable after month closing.
- Corrections use explicit correction/adjustment records and audit trails.
- Reputation is transparent, never an opaque trust score.
- Reviews are from verified current/former members and anonymous publicly.
- No paid discovery promotion in MVP.
- No marketplace/Shop in MVP.

## Source-of-truth hierarchy

1. Existing backend/security constraints.
2. This specification.
3. Existing Bachelor Point screens/component library.
4. Feature specifications.
5. AI assumptions.

## UI source of truth

- Mess Hub
- Meals And Bazar
- Bills And Split
- To Let Portal
- Luminous Glass System/component library

Never redesign these while implementing missing functionality.

## Major modules

Authentication, onboarding, no-mess home, discovery, mess management, membership, meals, bazar, expenses, accounting, monthly closing, constitution/rules, governance, announcements, profiles, reputation, reviews, messaging, notifications, To-Let, safety, settings and cache/offline reads.

## Completion definition

A feature is complete only when its UI, state transitions, persistence, authorization, loading/empty/error/success states, audit requirements and tests are implemented.
