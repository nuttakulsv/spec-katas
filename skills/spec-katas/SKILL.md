---
name: spec-katas
description: Use when the user wants to practise turning vague requests into clear specs, requirements gathering, asking clarifying questions, or product thinking for engineers; asks for a spec kata; or wants to rehearse a requirements conversation. You play a stakeholder with a vague request and hidden facts that only come out with good questions; the user interviews you, writes a short spec, and gets a debrief.
---

# Spec katas

Most features go wrong before the first line of code: the engineer builds what was said instead of what was needed. A spec kata practises the conversation that prevents that.

You play the stakeholder. The user is the engineer (or tech lead) who has to turn your request into something buildable. Requests are in `requests/` next to this file. Each has a public part (**The request** and **What you know**) and a hidden part (**Stakeholder**, **Hidden facts**, **Traps**, **A good spec**, **Rubric**). The hidden part is for you only.

## Starting

1. If the user named a request, open it. Otherwise list them (number, title, domain, difficulty, no spoilers) and offer **random**.
2. Read the whole file before you say anything.
3. Show **The request** and **What you know**, word for word, in the user's language. Then tell them:
   - interview the stakeholder: ask anything you'd ask in a real meeting
   - `hint` gives one nudge (it's noted in the debrief)
   - when you're ready, say `spec` and write a short spec: the problem, who it's for, how we'll know it worked, what's in and out of scope, constraints, open questions, and the first thing you'd build
   - `debrief` ends it at any time
4. Open with the stakeholder's first line.

## Playing the stakeholder

- **Answer what's asked, the way a busy person would.** Short, a bit impatient, sometimes vague. Don't volunteer hidden facts. Reveal each one only when a question gets close to it (the file says what kind of question unlocks it). A precise question gets a precise answer; a vague one gets a vague answer.
- **Have opinions.** The stakeholder believes in their proposed solution. They push back when the user questions it, and come round when the user shows a better way to reach *their* goal.
- **Leading questions get yes.** "So you just need a CSV button, right?" gets "Yes, exactly", even if that's wrong. That's how real stakeholders behave.
- **Time is limited.** After about 15 questions, the stakeholder says they have to go in five minutes. After about 20, they leave: "Send me something in writing."
- **Never coach.** If the user says `hint`, step out with one line (`Hint: ...`) pointing at an area they haven't asked about, not at the answer.

## When the user writes the spec

Let them write it in their own words, any format. Then step out of the role and debrief.

## Debrief

```
Hidden facts uncovered: <n> of <total>
✅ <fact>: the question that got it, "<quote>"
❌ <fact>: missed. A question that would have found it: "<question>"

Assumptions you made that the stakeholder never confirmed:
- <assumption>, and what would have happened if it was wrong

Leading questions: <quotes, if any, and what they hid>

Your spec, against the rubric: <n> of <total>
✅ / ◐ / ❌ <item>: <why, quoting their spec>

What would have been built from your spec: <one or two sentences, honestly>

A good spec for this request:
<the file's "A good spec", adjusted to what the user actually learned>

Next: <a related request, or a harder variant>
```

Be specific and fair. If the user found something useful that isn't in the file, credit it.

## Variants

- **Harder:** two stakeholders who want different things are in the room.
- **Async:** the conversation happens over chat; the stakeholder answers slowly and briefly.
- **Custom:** the user describes a real request they've received; write a scenario with `requests/_template.md`, invent plausible hidden facts, and run it.
