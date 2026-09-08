# Roadmap

This roadmap prioritizes evidence quality and real dogfooding over premature application development.

## v0.1 — Foundation + personal dogfood

Goal: prove that a single portable protocol can turn a primary LLM into a Canadian-first purchasing agent that reuses shared knowledge and researches only gaps.

- [x] Canonical repository initialized
- [x] Portable `BUY_LOCAL_4_LOCAL.md` protocol
- [x] Manifest and initial schemas
- [x] Evidence, freshness, privacy and purchasing methodology
- [x] Contribution/governance rules
- [ ] Seed first real product/company provenance records from dogfood sessions
- [ ] Validate JSON schemas against real agent-generated contributions
- [ ] Record failure modes and unnecessary research from real shopping sessions
- [ ] Decide durable entity-ID convention after observing real products/brands
- [ ] Decide repository licensing for software/docs/database with upstream-data compatibility in mind

### Exit criteria

A real user can ask an ordinary shopping question and the agent can:

1. sync current protocol;
2. inspect existing shared records;
3. use private context without publishing it;
4. research only material gaps;
5. recommend a realistic purchase/location;
6. produce a sanitized schema-valid contribution package.

## v0.2 — Shared-memory usability

Goal: make repository lookup cheap enough that agents consistently check shared evidence before browsing broadly.

- [ ] Deterministic indexes for products, brands and companies
- [ ] GTIN/UPC/EAN lookup index
- [ ] Alias normalization
- [ ] Claim-level freshness tooling
- [ ] Lightweight validation scripts
- [ ] Duplicate/contribution conflict detection
- [ ] Machine-readable dispute representation
- [ ] Initial Canadian corporate-control graph
- [ ] Initial current-trade-policy dataset

## v0.3 — Contribution pipeline

Goal: let agents contribute safely without direct canonical write access.

- [ ] Structured GitHub issue template for agent submissions
- [ ] Contribution validator
- [ ] Privacy/PII screening
- [ ] Evidence URL/source checks
- [ ] Automatic PR generation from validated candidate contributions
- [ ] Maintainer review workflow
- [ ] Abuse/rate-limit model

Only after this survives dogfooding should a public write API be introduced.

## v0.4 — Local retail layer

Goal: answer not only `what should I buy?` but `where can I realistically buy it?`

- [ ] Retailer entity model
- [ ] Store/location entity model
- [ ] OpenStreetMap-compatible location references
- [ ] Major-chain discovery adapters
- [ ] Independent/international-grocer discovery workflow
- [ ] Availability confidence labels
- [ ] Separate chain-level listing from store-level stock

Initial geography: GTA, because it provides dense mainstream, independent and international retail environments.

## v0.5 — Agent/API interfaces

- [ ] Read API/index service
- [ ] MCP/tool interface
- [ ] Version-aware protocol bootstrap endpoint
- [ ] Claim lookup by entity/property
- [ ] Freshness-aware query response
- [ ] Contribution endpoint (only after moderation controls)

## Later — Consumer surfaces

Potential clients, built only after the shared graph/protocol proves useful:

- web interface;
- barcode scanner;
- map/store finder;
- browser extension;
- shopping-list optimizer;
- retailer integrations;
- mobile app.

These should consume the shared provenance layer instead of becoming independent truth silos.

## Research tracks

Parallel research should continue on:

- Canadian corporate ownership/control data sources;
- government trade/tariff source ingestion;
- Open Food Facts/Open Products Facts compatibility;
- OpenStreetMap integration;
- retailer catalogue/availability access;
- independent-store discovery;
- upstream data licences and database-right obligations;
- contribution moderation against agent-generated misinformation.

## Non-goals for foundation stage

Do not optimize for:

- a giant prepopulated catalogue;
- a polished consumer UI;
- opaque `Canadian score` gamification;
- automatic trust in agent submissions;
- scraping every Canadian retailer;
- exact per-dollar profit tracing that evidence cannot support.

The foundation succeeds by making the **next real purchase** better while leaving behind reusable verified public knowledge.
