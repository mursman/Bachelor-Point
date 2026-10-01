# Bachelor Point — State and Permission Matrix

## User

`Unknown, Authenticated, PhoneUnverified, PhoneVerified, Deleted`

## Mess

`NoMess, ActiveMess, LeavingMess, FormerMember, MessClosed`

## Membership

`Requested, Invited, Active, Leaving, Former`

## Join request

`Pending, Accepted, Declined, Cancelled`

## Financial item

`Draft, Pending, Approved, ChangesRequested, Declined, Locked`

## To-Let

`Draft, Published, Paused, Filled, Expired, Removed`

## Network

`Online, Offline, Reconnecting`

## Permission principles

UI should hide irrelevant controls, but server independently enforces permissions.

## Core permissions

Visitor:
- public discovery

Verified user:
- create mess
- save
- request join
- profile
- contact request
- report

Member:
- own meals
- own guest meals
- bazar
- corrections
- own payments
- leave
- eligible reviews
- mess reads

Assistant Manager:
- only explicitly granted management operations

Manager:
- membership approvals
- member management
- settings
- approvals
- rate finalization
- adjustments
- governance
- monthly closing

## Screen state contract

Every screen should support:
`Loading, Loaded, Empty, Error, Unauthorized, Offline`

Every mutation:
`Idle, Submitting, Success, Failure`

## Conflict handling

Last-seat conflict, second-manager conflict, closed-cycle conflict and duplicate mutation must refresh authoritative state and show a meaningful message.

Never trust cached roles or balances as authorization.
