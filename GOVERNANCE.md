# Governance

Buy Local 4 Local is intended to become a public evidence graph used by humans and LLM agents. Governance therefore focuses on traceability, dispute handling, privacy and resistance to low-quality automated contributions.

## Core principles

### Evidence over assertion
Canonical claims must be supported by inspectable evidence.

### Facts separate from preferences
The project may store provenance facts and default purchasing logic, but factual records must remain useful even to someone with different political or purchasing preferences.

### Atomic claims over narrative truth
Ownership, manufacturing, retailer control and tariff status are separate claims with separate evidence and refresh cycles.

### Public provenance, private personalization
User-specific context must not be required to participate in the public dataset.

### No automatic canonical writes from arbitrary agents
Agents may propose. Review/validation determines canonical state.

## Canonical truth model

The repository may contain multiple claims about the same property when history or disagreement requires it.

A claim's status communicates its standing:

- `candidate`: submitted but not yet accepted as canonical;
- `verified`: evidence currently supports the claim strongly enough for reuse;
- `disputed`: credible conflicting evidence exists;
- `stale`: refresh policy or contradictory signals require revalidation;
- `rejected`: reviewed and found unsupported, invalid, duplicated, or out of scope.

## Disputes

When two credible claims conflict:

1. preserve both evidence trails;
2. confirm the entities/SKUs/time periods actually match;
3. prefer stronger and more directly scoped evidence where justified;
4. document the resolution rather than silently replacing history;
5. leave the claim disputed when uncertainty remains material.

## Agent contribution safeguards

Automated or agent-generated contribution tooling should eventually enforce:

- schema validation;
- URL/source validation where technically possible;
- duplicate detection;
- personal-data screening;
- rate limits;
- source-domain reputation signals;
- conflict detection;
- human review for sensitive or high-impact changes.

## Neutral infrastructure

The consumer-facing objective is Canadian-first purchasing, but the provenance layer should remain descriptively neutral.

For example, the graph should record:

> Company X is U.S.-controlled and Product Y is manufactured in Ontario.

The preference layer decides how much those facts matter to a particular purchase.

This separation makes the dataset useful to researchers, journalists, other Buy Canadian projects, retailers and developers beyond the initial workflow.

## Versioning

The protocol, schema and dataset version independently.

Breaking schema changes require a schema-version increment and migration guidance.

Protocol changes should preserve backward compatibility where practical and clearly state when an older agent installation should refresh its instructions.

## Project stewardship

During the foundation stage, maintainer judgment may be required while formal moderation processes are still being tested. Governance should become more explicit as contribution volume grows rather than pretending a mature community process already exists.
