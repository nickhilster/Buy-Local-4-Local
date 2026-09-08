# v0.1 Dogfood Protocol

The first goal is not to prove the concept with a polished demo. It is to expose where the protocol wastes work, makes unsupported assumptions, fails to reuse shared knowledge, or cannot turn research into a practical purchase.

## Test environment

Use Buy Local 4 Local inside the user's primary LLM assistant during ordinary purchase decisions.

Prefer real prompts such as:

> I'm running low on chole masala, rice and eggs. What should I buy?

rather than artificial benchmark prompts.

## Before each test

The agent should:

1. read/sync `manifest.json` and the current protocol;
2. inspect only relevant shared records;
3. use legitimately available private user context to identify likely needs/preferences;
4. explicitly distinguish shared-known, private-known, inferred and unknown information.

## During each test

Track internally:

- which shared claims were reused;
- which claims were missing;
- which claims were stale;
- which research steps were unnecessary;
- which candidate products were discarded before deep research;
- whether local availability could be established;
- whether the recommendation changed because of retailer economics;
- whether tariff information materially affected priority;
- any unsupported inference the protocol tempted the agent to make.

## After each test

Produce two outputs.

### A. User recommendation

Keep this practical and concise:

- what to buy;
- why it ranks well;
- important compromise;
- where to get it when knowable.

### B. Sanitized public learning

Only if new reusable facts were established:

- generate schema-compatible contribution payload;
- strip all personal context;
- deduplicate against current shared data;
- preserve evidence and uncertainty;
- submit only through an authorized route.

## Failure log

For each meaningful workflow failure, capture:

```text
Date:
Purchase task:
Failure type:
What the agent did:
Why it was inefficient/wrong:
Protocol/schema change suggested:
Did this expose a general problem or a one-off edge case?
```

Suggested failure types:

- redundant research
- bad entity match
- weak evidence
- stale data not detected
- unnecessary user question
- privacy boundary risk
- retailer availability ambiguity
- tariff/policy ambiguity
- international-product edge case
- corporate-control ambiguity
- recommendation not actionable
- schema insufficient

## v0.1 success metrics

We are looking for directional evidence, not vanity metrics.

Track:

- percentage of needed claims reused from shared data;
- number of live research actions per purchase decision;
- number of new reusable claims created;
- number of claims later disputed/corrected;
- proportion of recommendations with actionable local availability;
- number of privacy boundary violations (target: zero);
- number of times a whole product was re-researched when only one claim was stale (target: zero).

## Foundation rule

Do not add complexity to solve imagined future scale problems until a dogfood session exposes the need.

Do fix structural problems early when they affect provenance, privacy, repeat research, or contribution integrity.
