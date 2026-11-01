# Request 02: Export to CSV

**Domain:** B2B SaaS · **Difficulty:** Easy · **Practises:** finding the job behind a feature, data sensitivity, scoping the smallest useful thing

## The request

> **Nok (Finance Lead):** Can we get an "Export to CSV" button on the transactions page? Should be quick, right?

## What you know

A B2B invoicing product. Customers are small businesses; each has between a few hundred and 200,000 transactions a year. The transactions page shows date, customer name, amount, status and payment method. There's no export today.

## Stakeholder

**Nok, Finance Lead (internal, not a customer).** Practical and busy, a little tired of asking. She thinks a button is trivial. She cares about getting her month-end done, not about the product.

## Hidden facts

1. **The real job is month-end reconciliation** for the company's own finance team, comparing payouts against bank deposits. Unlocked by: asking what she'll do with the file, or why she needs it.
2. **She needs fields the page doesn't show:** payout ID, fee, net amount, settlement date. Unlocked by: asking what columns she needs or what she matches against.
3. **She does it on the first working day of each month, for the previous month,** and currently spends a day copying data from the admin database by asking an engineer. Unlocked by: asking how often or how it's done today.
4. **The data includes customers' personal data** (names, emails, phone numbers). Finance only needs the business name and IDs. Unlocked by: asking who will see the file or about personal data. Nok hadn't thought about it.
5. **Customers have also asked for exports**, and support has twelve open tickets. Unlocked by: asking if anyone else wants this.
6. **Excel opens the file:** Thai text must display correctly (UTF-8 with BOM) and amounts must stay numbers. Unlocked by: asking what tool opens the file.

## Traps

- A button that exports the five visible columns: useless for reconciliation.
- Including personal data that finance doesn't need.
- Thai names showing as garbled characters in Excel.
- Mixing the internal finance need with the customer-facing feature without noticing they're different.

## A good spec

**Problem:** finance spends a day each month reconciling payouts against bank deposits, with data pulled by an engineer.
**Users:** internal finance team (first); customers (separate, later: 12 support tickets).
**Must have:** monthly reconciliation export (CSV, UTF-8 with BOM for Excel) with payout ID, settlement date, gross, fee, net, status, business name, customer ID. No emails or phone numbers.
**Measure:** month-end reconciliation done without engineering help, in under two hours.
**Out of scope for now:** customer-facing export (different columns, permissions, big accounts need async generation).
**Open question:** should the file be emailed on the first of each month instead of downloaded?
**First step:** generate last month's file with the agreed columns and have Nok reconcile with it.

## Rubric

1. Asked what the file is for.
2. Found the missing columns.
3. Found how often and how it's done today.
4. Raised personal data and limited the columns.
5. Noticed customers want exports too, and kept it as a separate scope.
6. Thought about Excel and Thai text.
7. Spec has a measurable outcome.
8. Spec names a smallest first version.
