# Architecture

Buy Local 4 Local is designed as an open protocol, shared evidence graph, and contribution system. A consumer app may exist later, but the repository itself is the product foundation.

## Architectural invariant

**Shared public provenance is reusable. Personal context is private. New research is performed only when relevant shared claims are missing, stale, disputed, or context-specific.**

## System layers

```text
┌──────────────────────────────────────────────┐
│ USER'S PRIMARY LLM                           │
│ private recipes, shopping history, needs     │
└───────────────────┬──────────────────────────┘
                    │ decides what matters
                    ↓
┌──────────────────────────────────────────────┐
│ BUY LOCAL 4 LOCAL PROTOCOL                   │
│ bootstrap • policy • evidence • freshness    │
└───────────────────┬──────────────────────────┘
                    │ query first
                    ↓
┌──────────────────────────────────────────────┐
│ SHARED PUBLIC PROVENANCE                     │
│ entities • claims • evidence • disputes      │
└───────────────────┬──────────────────────────┘
                    │ only gaps
                    ↓
┌──────────────────────────────────────────────┐
│ LIVE RESEARCH                                │
│ web • corporate sources • government • retail│
└───────────────────┬──────────────────────────┘
                    │ sanitized candidate facts
                    ↓
┌──────────────────────────────────────────────┐
│ CONTRIBUTION PIPELINE                        │
│ validate • dedupe • review • accept/dispute  │
└───────────────────┬──────────────────────────┘
                    │
                    └──────────────→ shared provenance
```

## Core domain objects

### Entity
A real-world thing with stable identity where possible.

Initial entity types:

- `product`
- `brand`
- `company`
- `retailer`
- `store`
- `manufacturer`
- `jurisdiction`
- `trade_measure`

### Claim
An atomic assertion about an entity.

Examples:

- Brand X `ultimate_parent` Company Y
- Company Y `jurisdiction_of_control` Canada
- Product Z `manufactured_in` Ontario
- Retailer A `controlled_in` Canada

Claims are independently refreshable. This prevents one stale field from forcing a complete re-investigation.

### Evidence
A source supporting or challenging a claim. Evidence is attached to claims rather than buried in prose.

### Relationship
Corporate and product provenance are graph-shaped. Relationships such as `owned_by`, `manufactured_by`, `brand_of`, `sold_by`, and `located_at` should eventually become first-class graph edges.

### Contribution
A candidate bundle of claims and evidence produced by a human or agent. A contribution is not canonical merely because it was submitted.

## Two value-flow graphs

### Corporate control

```text
Product
  ↓
Brand
  ↓
Operating company
  ↓
Parent company
  ↓
Ultimate controlling entity
  ↓
Jurisdiction of control
```

### Physical / retail flow

```text
Inputs
  ↓
Processing
  ↓
Manufacturing
  ↓
Packaging
  ↓
Distribution
  ↓
Retailer
  ↓
Store
```

These graphs must remain separable. A Canadian-made product can be foreign-controlled. A foreign-made product can be sold by a Canadian independent retailer.

## Stable truth vs dynamic context

### Stable-ish provenance

- company ownership/control
- brand relationships
- manufacturing locations
- product identifiers

### Faster-changing policy

- tariffs
- countermeasures
- remissions
- effective dates

### Very fast retail context

- price
- stock
- store-level availability
- promotions

### Event-driven private context

- user's accepted/rejected substitutions
- recurring needs
- retailer preference
- budget sensitivity

Do not store these layers as one monolithic product record with one expiration date.

## Read path

For a purchase decision:

```text
identify need
    ↓
lookup entity/product
    ↓
fetch relevant claims
    ↓
apply freshness rules
    ↓
research only gaps
    ↓
rank realistic candidates
    ↓
verify local availability when material
    ↓
recommend
```

## Write path

```text
new public fact discovered
    ↓
strip user context
    ↓
normalize entity IDs
    ↓
create atomic claims
    ↓
attach evidence
    ↓
validate schema
    ↓
dedupe against existing claims
    ↓
accept / dispute / reject
```

## Repository-first API strategy

For v0.x, GitHub is the canonical transparent store. Files should remain human-readable and agent-readable.

A later read API can index repository data without replacing the repository as the auditable source of truth.

Likewise, a later contribution endpoint may accept structured payloads and generate reviewed repository changes automatically. Agents must not be given unrestricted canonical write access.

## Identifier strategy

Prefer durable external IDs when legitimate:

- GTIN/UPC/EAN for products when known;
- stable corporate identifiers where available;
- OpenStreetMap IDs for store/location references when appropriate;
- jurisdiction standards such as ISO country codes.

Never infer manufacturing origin from a barcode prefix alone.

When no durable external ID exists, use deterministic project IDs and record aliases.

## Data organization direction

The repository should begin file-oriented and evolve based on measured scale.

Suggested initial pattern:

```text
data/entities/<type>/<id>.json
data/claims/<entity-id>.jsonl
data/contributions/YYYY/MM/<contribution-id>.json
```

Do not prematurely introduce a database server merely to mimic a production application. Add indexing/database infrastructure when repository-scale lookup becomes measurably inadequate.

## Agent compatibility

The protocol must degrade safely across environments:

1. Full agent with web + GitHub/API write capability.
2. Agent with web + read-only repository access.
3. LLM with browsing but no repository write capability.
4. LLM with no network access using only cached/local protocol data.

An agent must never claim a sync, lookup, submission, or verification happened if its environment cannot perform it.

## Privacy boundary

The user's private profile is not part of the public graph.

The shared project may learn:

> Product X is controlled by Company Y, supported by sources A and B.

It must not learn through the contribution protocol:

> User N buys Product X every Tuesday from Store Z and prefers it because of a health condition.

The contribution layer should be designed to make accidental personal-data submission difficult.

## Application layer

Future clients may include:

- primary-LLM workflow;
- MCP/tool server;
- website;
- barcode scanner;
- map/store finder;
- shopping-list optimizer;
- browser extension;
- retailer integrations;
- public API.

All should consume the same provenance/evidence model rather than maintaining separate truth systems.
