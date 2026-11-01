# Request 05: Make it work offline

**Domain:** Field sales app · **Difficulty:** Hard · **Practises:** narrowing a huge request, conflicts and edge cases, constraints on real devices

## The request

> **Ton (VP Sales):** Our reps lose signal all the time in the provinces. The app needs to work offline. All of it.

## What you know

A sales app used by 300 field reps who visit shops across Thailand to take orders and check stock. It's a React Native app talking to a REST API. Today, with no signal, the app shows an error screen.

## Stakeholder

**Ton, VP Sales.** Frustrated on behalf of his reps; he rode along with one last month and watched her lose an order. He says "all of it" because he doesn't know which parts matter. Respects people who've clearly thought about the reps' day.

## Hidden facts

1. **The painful moment is taking an order at a shop** with no signal. Reps write it on paper and re-enter it later; about 8% of paper orders get lost or mistyped. Unlocked by: asking what reps are doing when the signal drops, or what breaks.
2. **Stock levels change during the day,** and a rep can sell stock that another rep sold an hour ago. Unlocked by: asking about stock, or what happens if two reps sell the same item.
3. **Prices and promotions change weekly,** on Mondays. Unlocked by: asking about prices or how often data changes.
4. **Reps use company Android phones** from 2019 with 3 GB of RAM and 32 GB storage, often nearly full of photos. Unlocked by: asking about devices.
5. **The catalogue is 25,000 products with images,** about 4 GB in total. Unlocked by: asking about data size.
6. **Reps are usually offline for 10 to 60 minutes,** rarely a whole day. Unlocked by: asking how long they're offline.
7. **Orders above 50,000 baht need a manager's approval** before they're confirmed. Unlocked by: asking about rules, approvals or credit limits.

## Traps

- "All of it offline": syncing the whole catalogue with images to old phones, for months of work.
- Ignoring stock conflicts, so offline orders oversell.
- Forgetting the approval rule, so big offline orders are confirmed without approval.

## A good spec

**Problem:** reps lose or mistype about 8% of orders taken without signal (on paper today).
**Goal:** zero paper orders; every order taken offline reaches the system within an hour of reconnecting.
**In scope:** offline order taking for the rep's assigned shops: product list without images (or thumbnails for the top 500), this week's prices and promotions, last-known stock with a timestamp. Orders queue locally and sync when online.
**Conflicts:** orders taken offline are "pending" until synced; if stock is gone, the rep and the shop get a clear message, and the rep can substitute. Orders over 50,000 baht stay pending approval.
**Constraints:** must fit in under 200 MB on a 2019 Android phone with 3 GB RAM.
**Out of scope:** offline stock checks across all products, offline reports, full-resolution images.
**Open questions:** how should we tell the shop that an order is pending? Do reps need yesterday's order history offline?
**First step:** measure how often orders would conflict on stock, using last quarter's orders.

## Rubric

1. Narrowed "all of it" to the moment that hurts (taking orders).
2. Asked about devices and data size.
3. Found and handled stock conflicts.
4. Asked how long reps are offline.
5. Found the approval rule.
6. Asked about prices and how often data changes.
7. Spec has a measurable goal (lost orders, sync time).
8. Spec is explicit about what's out of scope.
