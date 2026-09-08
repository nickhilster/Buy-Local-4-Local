# Buy Local 4 Local

**Buy Local 4 Local** is an open purchasing-intelligence project for Canadians and the LLM agents they already use.

The project helps an agent answer a practical question:

> What should I buy, and where should I buy it, if I want to keep more economic value in Canada and reduce unnecessary U.S. dependence?

It is not a maple-leaf-label directory and it is not a boycott list. The system separates ownership, manufacturing, inputs, retailer economics, current trade policy, local availability, evidence quality, and user preference.

## Core idea

A user can give `BUY_LOCAL_4_LOCAL.md` to a capable LLM agent. The agent should:

1. Check this repository before doing new research.
2. Reuse fresh, evidence-backed public knowledge.
3. Use the user's existing private context to understand what they actually buy.
4. Research only missing or stale claims that matter to the current purchase.
5. Prefer Canadian options where credible, then practical non-U.S. alternatives.
6. Explain meaningful trade-offs instead of reducing products to a flag.
7. Keep personal context private.
8. Package newly discovered public provenance as a structured candidate contribution.
9. Contribute only through a supported, authorized mechanism.

The first user may pay the research cost. The next user should mostly pay the lookup cost.

## Repository architecture

```text
.
├── BUY_LOCAL_4_LOCAL.md          # Portable agent protocol / dogfood entry point
├── README.md                     # Project overview
├── ARCHITECTURE.md               # System boundaries and data-flow model
├── CONTRIBUTING.md               # Human + agent contribution rules
├── GOVERNANCE.md                 # Truth, disputes, privacy and stewardship
├── ROADMAP.md                    # Sequenced build plan
├── manifest.json                 # Machine-readable protocol entry point
├── schemas/
│   ├── claim.schema.json         # Atomic evidence-backed fact
│   ├── product.schema.json       # Product identity + references to claims
│   ├── contribution.schema.json  # Candidate research package
│   └── user-profile.schema.json  # PRIVATE profile format; never shared upstream
├── data/
│   ├── README.md                 # Public dataset conventions
│   ├── entities/                 # Canonical entity records
│   ├── claims/                   # Canonical public claims
│   └── contributions/            # Accepted/proposed structured contributions
├── methodology/
│   ├── evidence.md               # Evidence hierarchy and confidence
│   ├── freshness.md              # Claim-specific refresh policy
│   ├── purchasing-policy.md      # Default Canadian-first decision logic
│   └── privacy.md                # Public/private boundary
└── examples/
    └── product-research.example.json
```

## Four layers

### 1. Protocol

The portable instructions that teach an LLM how to operate. `BUY_LOCAL_4_LOCAL.md` is the canonical user-facing bootstrap file.

### 2. Personal context

Private information the user's primary assistant may already know: recurring groceries, recipes, accepted substitutions, usual stores, budget constraints, household needs and purchase patterns.

This information is used to decide **what deserves research**. It is never part of the public dataset by default.

### 3. Shared provenance

Reusable public facts about products, brands, companies, manufacturing, major inputs, retailers, tariffs and evidence. Shared knowledge is treated as a cache of evidence, not unquestionable truth.

### 4. Research and contribution

When a relevant claim is missing or stale, the agent researches only that gap, answers the user, strips personal information, then prepares a candidate contribution using the repository schema.

## Economic provenance model

The project keeps corporate and physical value flow separate.

```text
PRODUCT
  ↓
BRAND
  ↓
OPERATING COMPANY
  ↓
PARENT COMPANY
  ↓
ULTIMATE CONTROLLING ENTITY
  ↓
JURISDICTION OF CONTROL
```

In parallel:

```text
INPUTS / INGREDIENTS
  ↓
PROCESSING
  ↓
MANUFACTURING
  ↓
PACKAGING
  ↓
DISTRIBUTION
  ↓
RETAILER
  ↓
LOCAL STORE
```

The project does **not** claim to trace every dollar of profit from a retail purchase. Where exact economic flows are unknowable, it records defensible proxies such as ultimate corporate control, manufacturing location and retailer ownership with evidence and confidence.

## Default purchasing hierarchy

The default policy is a preference, not a statement of product quality:

1. Canadian-owned + Canadian-made
2. Canadian-made
3. Canadian-owned with foreign manufacturing/imports
4. Credible non-U.S. alternative
5. U.S.-controlled product where necessary or clearly preferable

International products and immigrant-owned Canadian retailers are first-class parts of the model. A product made abroad and sold through a Canadian independent business can still keep meaningful economic activity in the local economy.

## Current status

`v0.1.0-foundation` — protocol and schema formation, intended for real-world dogfooding before application development.

The immediate test is simple: install the protocol in a primary LLM assistant, use it during real shopping decisions, and record where the workflow wastes work, lacks evidence, overreaches, or fails to reuse existing knowledge.
