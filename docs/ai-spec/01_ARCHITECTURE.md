# Bachelor Point — Architecture

Use layered, feature-oriented Flutter architecture.

```
UI/View
  ↓
ViewModel / Controller
  ↓
Domain / Use Case where complexity warrants it
  ↓
Repository Interface
  ↓
Firebase/API implementation
```

## Project structure

```
lib/
  app/
    app.dart
    router/
    bootstrap/
    theme/
    config/
  core/
    errors/
    result/
    network/
    auth/
    permissions/
    logging/
    storage/
    notifications/
    location/
    media/
  design_system/
    tokens/
    theme/
    glass/
    typography/
    buttons/
    inputs/
    cards/
    sheets/
    navigation/
    status/
  features/
    auth/
    onboarding/
    home/
    discovery/
    mess/
    membership/
    meals/
    bazar/
    expenses/
    accounting/
    governance/
    announcements/
    profile/
    reputation/
    reviews/
    messaging/
    notifications/
    to_let/
    safety/
  data/
    firebase/
    repositories/
    dto/
    mappers/
  domain/
    entities/
    value_objects/
    services/
    use_cases/
```

## Rules

- UI never calls Firebase directly.
- Business logic never lives in widgets.
- Use immutable models.
- Use repositories as the single source of truth.
- Use dependency injection.
- Use unidirectional data flow.
- Keep Firebase behind repository interfaces so REST/PostgreSQL can replace it later.
- Use typed domain errors.
- Use server-authoritative logic for permissions, membership, finance, closing, reputation and reviews.

## Initial infrastructure

- Firebase Authentication
- Firestore
- Firebase Storage
- FCM
- Firebase Functions and/or Cloud Run for trusted server operations
- Firestore-based chat

## Future architecture

```
Flutter
→ application/domain layer
→ REST API
→ Node.js/TypeScript
→ PostgreSQL
→ object storage
```

Do not scatter Firebase calls through the UI.

## Offline

Cache reads where useful. Do not pretend financial, membership, approval, voting or closing mutations succeeded while offline unless explicitly queued and server-confirmed.
