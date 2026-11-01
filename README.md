# spec-katas

[ภาษาไทย](README.th.md) · Part of the katas series with [staff-katas](https://github.com/nuttakulsv/staff-katas), [em-katas](https://github.com/nuttakulsv/em-katas) and [review-katas](https://github.com/nuttakulsv/review-katas)

"Make checkout faster." "Add an export button." "We need SSO." "Make it work offline. All of it."

Most features go wrong before the first line of code: someone builds what was said instead of what was needed. And now that a coding agent can build the literal request in an afternoon, asking the right questions first is the most valuable thing an engineer does.

spec-katas lets you practise it. Your AI agent plays a stakeholder with a vague request and facts they won't mention unless you ask the right question. You interview them, write a short spec, and get a debrief: which facts you found, which you missed and the question that would have found them, the assumptions you made, and what would actually have been built from your spec.

## What a session looks like

An abridged example from Request 01:

```
Agent:  > Ploy (Head of Growth): Checkout is too slow and we're losing sales.
        > Can the team make it faster this sprint? Mobile especially.

You:    How much have sales dropped, and since when?
Ploy:   Checkout conversion went from 62% to 51%. Started about six weeks ago.
You:    Which step are people dropping at?
Ploy:   ...I'd have to check. Hang on. Payment step, mostly card payments. Why?
You:    Did anything change six weeks ago? A release, a payment provider update?
Ploy:   The payments team said the bank updated something with 3-D Secure.
You:    spec
  ...
Agent:  Hidden facts uncovered: 4 of 6
        ✅ The drop is at the payment step: "Which step are people dropping at?"
        ❌ The real deadline is the 11.11 sale. "Why this sprint?" would have found it.
        What would have been built from your spec: a fix for the 3DS session
        expiry, which is the right problem. Without the date, it might have
        shipped after 11.11.
```

## The requests

| # | Request | Domain | Difficulty | Practises |
|---|---|---|---|---|
| 01 | [Make checkout faster](skills/spec-katas/requests/01-make-checkout-faster.md) | E-commerce | Easy | The goal behind a solution, asking for data |
| 02 | [Export to CSV](skills/spec-katas/requests/02-export-to-csv.md) | B2B SaaS | Easy | The job behind a feature, personal data, smallest useful thing |
| 03 | [We need SSO](skills/spec-katas/requests/03-we-need-sso.md) | B2B SaaS | Medium | A deal's real requirements, deadlines, must vs. nice |
| 04 | [Notify them](skills/spec-katas/requests/04-notify-them.md) | Consumer app (Thailand) | Medium | Channels, consent (PDPA), frequency, measuring impact |
| 05 | [Make it work offline](skills/spec-katas/requests/05-make-it-work-offline.md) | Field sales | Hard | Narrowing a huge ask, conflicts, real devices |
| 06 | [We want an AI chatbot](skills/spec-katas/requests/06-we-want-an-ai-chatbot.md) | Support (Thailand) | Medium | Whether AI is the answer, what it must never do, handover |

Each file contains the hidden facts and a model spec. Don't open one before you play it.

## Install

Claude Code:

```
/plugin marketplace add nuttakulsv/spec-katas
/plugin install spec-katas@spec-katas
```

Codex, Cursor, or anything else that reads SKILL.md:

```
npx skills add nuttakulsv/spec-katas
```

Then ask: "run a spec kata", "request 5", or "help me think through this request from my boss: ...".

**No coding agent?** Paste [`SKILL.md`](skills/spec-katas/SKILL.md) and a request file into any chat assistant and say "start".

## How the stakeholder behaves

- Answers what you ask, briefly, like a busy person. Precise questions get precise answers.
- Believes in their own solution and pushes back, until you show a better way to reach their goal.
- Says "yes, exactly" to leading questions ("so you just need a CSV button, right?"), even when that's wrong.
- Runs out of time after about 15 questions and leaves after 20: "Send me something in writing."

## Use it with a team

- **Juniors and new hires:** play 01 and 02 together, then compare the specs you wrote.
- **Before you prompt an agent:** the same questions make better prompts. A spec from a kata is a good brief for a coding agent.
- **Interviews:** a 20-minute spec kata shows product sense better than "tell me about a time you disagreed with a PM".
- **Your own requests:** describe a real ask you've received, and the agent builds a scenario with plausible hidden facts.

## License

MIT
