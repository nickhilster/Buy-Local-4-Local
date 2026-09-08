# Contributing

Buy Local 4 Local accepts human and agent-assisted contributions, but canonical data is evidence-reviewed rather than automatically trusted.

## Contribution types

Contributions may add or improve:

- entities;
- atomic provenance claims;
- evidence sources;
- manufacturing information;
- corporate-control relationships;
- trade-policy facts;
- retailer/store facts;
- schemas, methodology and protocol documentation;
- tooling that validates or indexes the public dataset.

## Required standard for data contributions

A reusable fact should be represented as an atomic claim with evidence.

Do not submit prose such as:

> This is basically a Canadian company.

Prefer:

- Brand X `owned_by` Company Y
- Company Y `ultimate_parent` Company Z
- Company Z `jurisdiction_of_control` Canada

with evidence attached to each material relationship.

## Agent-generated contributions

Agent assistance is welcome when:

1. the agent checked existing shared data first;
2. it researched only missing/stale/disputed claims;
3. source references are real and inspectable;
4. uncertainty is preserved;
5. personal/private context has been removed;
6. the payload validates against the current schema.

An LLM answer without evidence is not a valid provenance contribution.

## Privacy

Never contribute a user's private profile or assistant memory. Follow `methodology/privacy.md`.

The contribution schema requires an explicit privacy attestation. If private context cannot be reliably separated, do not submit the contribution.

## Current submission routes

During foundation/dogfood stage:

### Pull request
Best for contributors who can work directly with GitHub.

### Structured GitHub issue
Acceptable for agents/users that can create an issue but cannot safely modify repository data. The issue should contain a schema-compatible contribution payload and evidence.

### Local export
When the environment cannot interact with GitHub, generate a `contribution.json` package for later submission. Do not claim it was submitted.

A dedicated contribution API is intentionally deferred until the schema and moderation model survive dogfooding.

## Review states

Candidate facts should move through explicit states:

- `candidate`
- `verified`
- `disputed`
- `stale`
- `rejected`

Newer does not automatically mean better. A conflicting contribution can create a dispute rather than overwrite an established claim.

## Pull request guidance

Keep PRs narrow enough to review. For data contributions, explain:

- what entity/product is affected;
- which claims are new or changed;
- why existing data was insufficient/stale;
- what evidence supports the change;
- whether any conflict remains unresolved.

## No manufactured consensus

Do not generate bulk synthetic contributions merely to populate the repository. Early dataset quality matters more than apparent size.

A small graph with traceable evidence is more useful than a large graph of LLM guesses.
