# Request 03: We need SSO

**Domain:** B2B SaaS · **Difficulty:** Medium · **Practises:** separating a deal's real requirements from a buzzword, deadlines, minimum viable scope

## The request

> **Tee (Sales Director):** Big deal on the line. They need SSO or they won't sign. How fast can we ship it?

## What you know

A project management SaaS. Login is email and password, plus "Sign in with Google". No enterprise features yet. The team has four engineers. Nobody has built SAML before.

## Stakeholder

**Tee, Sales Director.** Excited, impatient, and vague on technical details because the customer's IT team talked to him in acronyms. He thinks "SSO" is one thing. He'll answer technical questions with "whatever they need" until pushed for specifics, then offers to forward the customer's security questionnaire.

## Hidden facts

1. **The customer is a bank with 1,200 users** and the deal is worth 3.2 million baht a year. Unlocked by: asking about the customer, size or deal value.
2. **They use Microsoft Entra ID (Azure AD)** and require SAML 2.0. Google sign-in doesn't count. Unlocked by: asking which identity provider or protocol, or asking for the security questionnaire.
3. **They also require automatic deprovisioning** (SCIM or equivalent): when someone leaves the bank, their access must end within 24 hours. Unlocked by: asking about user lifecycle, offboarding, or reading the questionnaire.
4. **The contract can be signed with SSO on the roadmap**, as long as it's live before their rollout on 1 March (ten weeks away). Unlocked by: asking what "or they won't sign" means exactly, or about dates.
5. **Their security team also asked for an audit log** of logins, but marked it "nice to have". Unlocked by: the questionnaire.
6. **Two other prospects** have asked about SSO in the last quarter, both on Okta. Unlocked by: asking if anyone else wants it.

## Traps

- Building a custom SAML integration only for Entra ID in a panic, when a standard implementation (or an auth provider) would serve Okta prospects too.
- Missing deprovisioning and failing the bank's security review in week nine.
- Promising "two weeks" because it sounded easy.

## A good spec

**Problem:** a 3.2M baht/year bank deal requires SAML SSO with Entra ID and automatic deprovisioning before their 1 March rollout. Two Okta prospects want SSO too.
**Must have by 1 March:** SAML 2.0 login for one customer org, tested with Entra ID; SCIM 2.0 deprovisioning (or a documented equivalent agreed with their security team); admins can enforce SSO for their org.
**Nice to have:** login audit log.
**Decision needed this week:** build on a standard library or use an auth provider (cost vs. time; two other prospects on Okta).
**Out of scope:** multiple IdPs per org, just-in-time role mapping.
**Open questions:** does the bank need on-prem or IP allowlisting? Test environment access to their Entra tenant?
**First step:** get the security questionnaire and a test Entra tenant from the bank.

## Rubric

1. Asked about the customer and what's at stake.
2. Pinned down protocol and identity provider.
3. Found the deprovisioning requirement.
4. Clarified the real deadline and that signing doesn't need SSO live.
5. Asked whether other customers need it (build once, not for one deal).
6. Asked for the security questionnaire or written requirements.
7. Spec separates must-have from nice-to-have.
8. Didn't commit to a date before knowing the scope.
