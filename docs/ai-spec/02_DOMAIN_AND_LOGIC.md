# Bachelor Point — Domain Rules and Logic

## Identity

User has: immutable ID, real name, verified phone, optional Google identity, gender, home district, emergency contact, occupation, optional monthly budget range, preferences, food preferences and privacy settings.

Do not collect/display exact DOB as a product field.

## Authentication

Phone OTP + Google. Phone verification is mandatory.

## Mess creation

Any authenticated user can create a mess. Creation creates the Mess, an Active Membership, Manager role, default settings/constitution and audit event. Creator becomes Manager.

## Membership

States: `Requested → Invited → Active → Leaving → Former`

One active mess per user.

Leaving never deletes historical financial records.

## Roles

Exactly one Manager. Roles: Manager, Assistant Manager, Member.

Assistant Manager permissions must be explicit/configurable; never assume full Manager authority.

## Joining

Public mess: `request → manager review → accept/decline → rule acknowledgement → Active`

Private mess: normally invitation-based.

## Vacancy

`available seats = maximum seats - active members`, additionally constrained by Manager's temporary availability setting and public vacancy setting.

## Meals

Breakfast, lunch and dinner are independent. Each is one unit. Member selection is 0 or 1. Guest meals use the same unit model. Staff/cook meals are excluded from member calculation. Cancellation cutoff is configurable. Late changes use correction requests and audit history.

## Meal rate

`calculated rate = approved meal-related expenses / counted member meals`

Show calculated and finalized rates separately. Example: `৳18,450 / 316 = ৳58.39`, finalized `৳58.50`.

## Bazar

Any member may submit: amount, date, category, payer, description, vendor, payment method, receipt. Approval can be required. Before closing, edits/deletes follow mess policy. After closing, use correction/adjustment rather than rewriting history.

## Expenses

Categories include rent, cook salary, WiFi, DESCO, WASA, waste, repairs, household and other. Every expense records creator, payer, amount, date, category, method and approval state.

## Payments

Payments are records only. Methods can be Cash, bKash, Nagad, Bank or Other. Never imply Bachelor Point transferred money.

## Balances

Conceptually:
`member balance = credits/payments/advances - allocated obligations`

Positive = owed to member. Negative = member owes.

Authoritative ledger calculations happen server-side.

## Fixed costs

Rent can be equal, individual or manager-defined. Utilities can be equal or custom.

## Mid-month join/leave

Apply configured prorating for fixed costs plus actual meals. Manager adjustments must be explicit.

## Monthly closing

`Open → Review → Resolve pending items → Finalize rate → Manager closes → Closed`

Closed cycles:
- remain readable
- original financial events become immutable
- corrections use adjustments
- audit history remains

## Mess fund

Positive closing remainder carries forward.

## Deficit

A closing deficit is allocated according to configured mess policy and shown to affected members.

## Audit

Material finance, membership, governance, rules and reputation mutations record actor, action, target, timestamp, before/after where relevant and reason where required.

## Constitution

Rules cover living conduct, meals, money and governance. Operational changes can be manager-controlled. Changes affecting member financial obligations or major rights require a vote. New members acknowledge the current version.

## Voting

Secret ballots. Eligible members have lived in the mess for at least 30 days. Default election duration 24h. Ties require another round. Never expose individual ballots.

## Reviews

Verified current/former members after at least 30 days. Categories include cleanliness, transparency, meal management, communication, fairness and overall. Reviewer identity is anonymous publicly. Manager can reply but cannot delete negative reviews.

## Reputation

Member categories: meal discipline, bazar participation, cleanliness, cooperation, rule adherence, attendance/verified activity. Manager categories: transparency, expense management, communication, fairness, meal management, problem solving, rule enforcement. Never create an opaque trust score.

## Discovery

Search by distance, vacancy, price and preferences. Filters: area, distance, seats, gender eligibility, meal system, smoking, rating, member count. No paid promotion in MVP.

## Contact and messaging

Phone visibility is controlled by the manager/user. Contact requests may be required. Messaging is basic and purpose-oriented, not a social feed.

## To-Let

Lifecycle: `Draft → Published → Paused → Filled/Expired/Removed`. Filled listings leave active vacancy discovery.

## Safety

Private reports for incorrect listing, harassment, fraud/scam, unsafe situation, false information or other.
