# Bachelor Point — AI Coding Agent Rules

## Before coding

Inspect:
1. repository structure
2. Flutter/Dart version
3. router
4. theme/design system
5. Firebase setup
6. models
7. repositories
8. existing screens/components

Reuse existing components.

## Build real features

A screen is not complete if it only renders mock data. Implement state, persistence, authorization, errors and tests.

## Code rules

- UI calls ViewModels/controllers.
- ViewModels call repositories/use cases.
- Repositories call Firebase/API.
- Business logic never lives in widgets.
- Use immutable typed models.
- Avoid raw maps across layers.
- Use dependency injection.
- Do not introduce unrelated rewrites.

## Mutations

Every mutation has: `idle → submitting → success/failure`

Disable duplicate submission.

Use idempotency keys/mutation IDs where duplicate writes would be harmful.

## Finance

Never trust client totals. Server is authoritative. Closed-period records are immutable. Use adjustments for post-close corrections. All material finance changes get audit events.

## Security

Never trust client roles or mess IDs. Never ship secrets. Never weaken Firestore rules for convenience. Never expose private profiles, exact addresses, phone numbers or anonymous reviewers.

## Testing

Unit-test:
- calculations
- permissions
- eligibility
- state transitions

Integration-test:
- create mess
- join
- accept
- meals
- bazar
- expenses
- payments
- closing
- review
- listing

UI-test critical flows and state rendering.

## Do not invent features

If unspecified:
1. inspect current implementation
2. inspect this spec
3. choose smallest consistent behavior
4. document assumptions
5. do not silently add product concepts

## Definition of done

UI + navigation + repository + persistence + authorization + states + audit + tests + no fake production data.
