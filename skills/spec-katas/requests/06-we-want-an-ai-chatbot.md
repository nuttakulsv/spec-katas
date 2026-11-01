# Request 06: We want an AI chatbot

**Domain:** Customer support (Thailand) · **Difficulty:** Medium · **Practises:** checking that AI is the answer, risks of a model that can make things up, measuring support outcomes

## The request

> **Khun Wichai (COO):** Everyone has an AI chatbot now. I want one on our LINE OA to handle customer support. Can we launch next month?

## What you know

An online electronics retailer. Customer support has 12 agents handling about 3,000 messages a day, mostly through the LINE Official Account. Orders are tracked in an internal system with an API. The company has never shipped an AI feature.

## Stakeholder

**Khun Wichai, COO.** Senior, decisive, impatient with technical caveats, but very sensitive to risk to the brand and to money. He saw a demo at a conference. He changes his mind when shown numbers or a concrete risk to customers.

## Hidden facts

1. **The real goal is response time:** customers wait 4 hours on average for a reply, and complaints about slow support doubled this quarter. Unlocked by: asking what problem he wants to solve, or what success looks like.
2. **About 60% of messages are "where is my order"** and another 15% are about returns. Unlocked by: asking what customers ask about, or for support data.
3. **Refunds and compensation must be approved by a human:** last year an agent promised a refund by mistake and it went viral. Unlocked by: asking what the bot may or may not do, or about risks.
4. **Many customers write in Thai with slang and typos,** and some send photos of broken items. Unlocked by: asking about language or message types.
5. **The order system API can return status by order number or phone number.** Unlocked by: asking where order data lives.
6. **Support agents fear losing their jobs;** the plan is to move them to handle complex cases, not to cut headcount. Unlocked by: asking about the support team or change management.
7. **Messages can include personal data** (addresses, phone numbers, ID card photos for warranty claims). Unlocked by: asking about privacy or PDPA.

## Traps

- A general-purpose chatbot that answers anything, invents delivery dates and refund promises.
- No handover to a human, so angry customers loop with a bot.
- Sending ID card photos to a third-party model without thinking about PDPA.
- Measuring "messages handled by the bot" instead of customer wait time.

## A good spec

**Problem:** customers wait 4 hours for replies; 60% of messages are order status questions that an agent answers by looking up the order system.
**Goal:** median first response under 5 minutes; complaints about slow support back to last quarter's level.
**First version:** on LINE, answer order status (by order number or phone number, verified) from the order API, and explain the return process. Everything else, including refunds, damaged items and anything the bot isn't sure about, goes to a human with the conversation summary.
**Rules:** the bot never promises refunds, compensation or delivery dates beyond what the API says. Answers come from the API and approved help articles only.
**Privacy:** don't send images or ID documents to the model; mask phone numbers and addresses in logs; check where the model provider stores data (PDPA).
**Measure:** first response time, share of order-status questions resolved without an agent, customer satisfaction, rate of wrong answers in a weekly sample.
**People:** agents review a sample of bot conversations weekly and handle escalations.
**Out of scope:** returns processing, product recommendations.
**First step:** label 500 recent messages by type to confirm the 60% and find the top five intents.

## Rubric

1. Asked what problem the chatbot should solve and how to measure it.
2. Found that most messages are order status, and scoped the first version to that.
3. Set rules on what the bot must never do (refunds, made-up dates).
4. Designed a handover to humans.
5. Raised personal data and images (PDPA).
6. Asked about the support team.
7. Spec measures customer outcomes, not bot activity.
8. Proposed checking the data before building.
