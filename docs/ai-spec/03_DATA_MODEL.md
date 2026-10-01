# Bachelor Point — Data Model

Use stable IDs, server timestamps and immutable financial events.

## User

```
users/{userId}
id, name, phone, phoneVerified, googleLinked, gender,
homeDistrict, occupation, emergencyContact,
currentMessId, profileVisibility, currentMessVisibility,
previousMessVisibility, budgetMin, budgetMax,
preferences[], foodPreferences[], reputationSummary,
createdAt, updatedAt, deletedAt
```

## Mess

```
messes/{messId}
id, name, description, area, geoPoint, exactAddress,
exactAddressVisibility, genderEligibility, maximumSeats,
managerId, visibility, publicVacancyEnabled,
seatTemporarilyUnavailable, mealSystem,
smokingAllowed, cookingAllowed, guestFriendly,
studyFriendly, workingProfessionalFriendly,
studentFriendly, rulesVersion, status,
ratingSummary, managerRatingSummary, createdAt, updatedAt
```

## Membership

```
messes/{messId}/memberships/{membershipId}
id, userId, messId, role, status, joinedAt, leftAt,
approvedBy, approvedAt, formerBalanceSnapshot,
rulesAcknowledgedVersion
```

## Core collections

```
joinRequests
invitations
mealRecords
mealCorrections
guestMeals
bazarEntries
expenses
expenseChangeRequests
financialEvents
payments
adjustments
messes/{messId}/cycles
auditEvents
constitutionVersions
votes
ballots
announcements
reviews
users/{userId}/savedMesses
contactRequests
conversations
messages
users/{userId}/notifications
toLetListings
reports
```

## Financial event

```
financialEvents/{eventId}
id, messId, memberId?, type, amount,
effectiveDate, sourceId, createdBy, createdAt, metadata
```

Types can include:
`meal_charge, rent_charge, utility_charge, bazar_share, expense, payment, advance, adjustment, deficit_allocation, fund_carry_forward`

Do not edit historical financial events after closing.

## Monthly cycle

```
id, month, status, calculatedMealRate, finalMealRate,
totalMeals, totalExpenses, totalPayments,
messFundOpening, messFundClosing, deficit,
closedBy, closedAt
```

## Review

Store the relationship to the verified membership, but never expose reviewer identity through public review APIs.

## Ballots

Ballots must be protected so normal client reads cannot reveal individual voting choices.

## Deletion

Account deletion must preserve financial/audit integrity while anonymizing personal identity where required.
