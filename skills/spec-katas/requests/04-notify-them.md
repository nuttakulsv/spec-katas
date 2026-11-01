# Request 04: Notify them

**Domain:** Consumer app (Thailand) · **Difficulty:** Medium · **Practises:** channels and consent, frequency, measuring impact

## The request

> **Mint (Product Manager):** Users keep missing price drops on items they've saved. Let's notify them when something on their wishlist goes on sale.

## What you know

A fashion marketplace app in Thailand, 1.2 million monthly users. Users can add items to a wishlist. The app has push notifications (opt-in rate 40%) and a LINE Official Account with 600,000 friends. Sellers change prices often, sometimes several times a day.

## Stakeholder

**Mint, Product Manager.** Thoughtful, has done user research, cares about not being spammy, but hasn't thought about the mechanics. She'll happily go deep if asked good questions.

## Hidden facts

1. **The goal is wishlist-to-purchase conversion**, currently 3%. She'd like 5%. Unlocked by: asking what success looks like.
2. **Research showed users prefer LINE** for shopping alerts; push is often turned off. Unlocked by: asking about channels or research.
3. **LINE messages cost money per message** beyond the free quota, and the marketing team owns the LINE budget. Unlocked by: asking about cost or who owns LINE.
4. **Users need to opt in** to marketing messages under PDPA, and only 55% of LINE friends have consented to promotional messages. Unlocked by: asking about consent, privacy or legal.
5. **Prices flap:** some sellers drop a price for an hour, then raise it. Users complained about a competitor's alerts for "fake sales". Unlocked by: asking what counts as a sale, or about how often prices change.
6. **The average wishlist has 14 items**, so one sale event can trigger many messages for one user. Unlocked by: asking about volume or how many items people save.
7. **Quiet hours:** research showed messages after 10 p.m. get blocked more. Unlocked by: asking about timing.

## Traps

- Sending a push for every price change: spam, blocks, and alerts for fake sales.
- Using LINE without consent or budget approval.
- No way to measure whether alerts led to purchases.

## A good spec

**Goal:** wishlist-to-purchase conversion from 3% to 5%.
**Trigger:** a wishlist item's price is at least 10% below its 14-day median and has stayed there for 2 hours.
**Channels:** push for users who allow it; LINE only for users who consented to promotional messages, within a monthly budget agreed with marketing.
**Limits:** at most one message per user per day, bundling multiple items; no messages 10 p.m. to 8 a.m.
**Measure:** purchases within 48 hours of an alert vs. a holdout group (10% of users get no alerts).
**Out of scope:** email, per-item notification settings.
**Open questions:** discount threshold per category? Seller-funded vs. platform discounts?
**First step:** run the trigger on last month's price history to see how many alerts it would have sent per user.

## Rubric

1. Defined success as a purchase metric.
2. Asked about channels and found LINE's cost and ownership.
3. Raised consent (PDPA) before choosing channels.
4. Defined what counts as a real price drop.
5. Limited frequency and bundled messages.
6. Thought about timing.
7. Planned a holdout or other way to measure impact.
8. Proposed testing the trigger on historical data first.
