# Request 01: Make checkout faster

**Domain:** E-commerce · **Difficulty:** Easy · **Practises:** finding the goal behind a solution, asking for data, defining success

## The request

> **Ploy (Head of Growth):** Checkout is too slow and we're losing sales. Can the team make it faster this sprint? Mobile especially.

## What you know

An online shop selling cosmetics in Thailand, about 4,000 orders a day, 80% on mobile. Checkout is a four-step flow: cart, address, payment, confirm. Payment methods: card (with 3-D Secure), PromptPay QR and mobile banking. You haven't seen complaints about speed in the support queue.

## Stakeholder

**Ploy, Head of Growth.** Sharp, data-literate, under pressure from the CEO because conversion dropped. She's convinced the cause is page speed because a competitor's site "feels faster". She'll defend "speed" until shown that the data points somewhere else, then switches quickly and is pleased.

## Hidden facts

1. **The drop is real but specific:** checkout conversion fell from 62% to 51% over the last six weeks. Unlocked by: asking how much sales dropped, since when, or for numbers.
2. **The drop is almost entirely at the payment step, on card payments.** Address and cart completion are unchanged. Unlocked by: asking which step people abandon, or for the funnel.
3. **Six weeks ago the bank's 3-D Secure flow changed** to a new challenge page that opens in a new tab on some phones; customers come back to an expired session. Unlocked by: asking what changed six weeks ago, about releases, or about payment providers. Ploy doesn't know the cause; she says "the payments team mentioned something about the bank updating 3DS".
4. **Page load times are fine:** p75 under 2 seconds on all checkout pages. Unlocked by: asking if anyone measured speed.
5. **PromptPay orders are growing and complete at 85%.** Unlocked by: asking about payment mix or which methods convert.
6. **The real deadline is the 11.11 sale**, three weeks away. Unlocked by: asking why this sprint, or about deadlines.

## Traps

- Building image compression and lazy loading: the pages are already fast, conversion doesn't move.
- Not asking for the funnel, so the 3DS problem stays hidden until 11.11.

## A good spec

**Problem:** Checkout conversion dropped from 62% to 51% six weeks ago. The drop is at the payment step for card payments, which lines up with the bank's 3-D Secure change. Page speed is not the cause (p75 < 2s).
**Goal:** back to ≥ 60% checkout conversion before the 11.11 sale.
**Measure:** checkout conversion by step and payment method, daily.
**In scope:** reproduce the 3DS flow on the top phone models; keep the session alive or resume it after the 3DS redirect; make PromptPay more prominent as the default for mobile.
**Out of scope:** general page speed work.
**Open questions:** can the payment provider switch to an in-page 3DS challenge? What share of card failures are 3DS timeouts versus declines?
**First step:** session replay or logs for 50 failed card checkouts this week.

## Rubric

1. Asked for numbers: how much, since when.
2. Asked where in the funnel people drop.
3. Asked what changed around the time it started.
4. Checked whether speed was actually measured.
5. Found the 11.11 deadline.
6. Spec defines success as a conversion number, not "faster".
7. Spec puts general speed work out of scope or justifies it with data.
8. Didn't commit to a solution before understanding the problem.
