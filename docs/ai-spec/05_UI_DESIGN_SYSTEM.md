# Bachelor Point — UI Design System

## Name

**Luminous Glass / Liquid Glass**

The design must feel premium, calm, airy, modern and trustworthy. It is functional glass, not decorative glassmorphism.

## Visual source

Existing:
- Mess Hub
- Meals And Bazar
- Bills And Split
- To Let Portal
- Luminous Glass component library

## Background

Icy/slate atmospheric background with subtle ambient gradients and depth. Avoid loud gradients.

## Glass levels

### Level 1

Major cards/hero surfaces:
- blur around 36px
- high translucency/saturation
- translucent light surface
- subtle bright border
- inset sheen
- soft shadow
- 24–28px radius

### Level 2

Nested cards/lists:
- blur around 28px
- slightly stronger contrast
- same border/highlight system

### Level 3

Controls/chips/inputs:
- lighter visual weight
- same surface language

## Typography

- Plus Jakarta Sans for UI/body/headings
- Space Grotesk for prominent numbers and financial data

## Color semantics

Emerald = primary/success/active/positive
Amber = pending/warning/cutoff
Red = destructive/error
Slate = neutral/inactive

Never communicate state through color alone.

## Spacing

Use a 4px/8px rhythm. Typical page padding: 16px. Avoid dense tables.

## Navigation

Bottom nav:
- Mess Hub
- Meals/Bazar
- Bills/Split
- To-Let

Do not add a fifth tab.

## FAB

Use existing Quick Log FAB where relevant:
- Meal
- Bazar
- Expense
- Payment
- Guest Meal
- Invite

## Buttons

Primary = existing emerald treatment. Secondary = subtle glass. Destructive = restrained danger treatment.

## Sheets

Glass bottom sheets for filters, confirmations, selectors and short edits.

## Cards

Use hierarchy, not card overload. Nested surfaces use Level 2.

## Financial display

Always make meaning explicit:

```
+৳1,240
You are owed
```

or

```
-৳380
You owe
```

Important calculations should show: `input → calculation → final`

## States

Every screen should have appropriate:
- loading
- loaded
- empty
- error
- unauthorized
- offline

Mutation screens also need:
- submitting
- success
- failure

## Accessibility

Readable contrast, adequate touch targets, semantic labels, scalable text and state labels.

## Motion

Subtle transitions only. Avoid excessive animation on financial screens.

## Golden rule

New screens must look as if the same designer built them beside the existing four screens.
