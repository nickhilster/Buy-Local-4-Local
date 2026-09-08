# Public Data

This directory holds the shared, non-personal provenance dataset.

## Rules

1. Public data must be reusable by an unrelated future user.
2. Personal shopping context does not belong here.
3. Claims must be atomic and evidence-backed.
4. New agent findings begin as candidates; they do not overwrite canonical facts automatically.
5. Historical/conflicting claims may coexist when properly scoped and status-marked.

## Planned structure

```text
data/
├── entities/
│   ├── products/
│   ├── brands/
│   ├── companies/
│   ├── retailers/
│   ├── stores/
│   └── trade-measures/
├── claims/
│   └── <entity-id>.jsonl
└── contributions/
    └── YYYY/MM/<contribution-id>.json
```

Directories are created as real records arrive; empty placeholder trees are intentionally avoided.

## Entity records

Entity files establish identity and aliases. They should avoid duplicating provenance assertions that belong in claims.

Example product identity:

```json
{
  "entity_type": "product",
  "product_id": "gtin:00000000000000",
  "name": "Example Product",
  "brand_id": "brand:example",
  "identifiers": {
    "gtin": "00000000000000"
  }
}
```

## Claims

Claims are individually refreshable facts.

Example:

```json
{
  "claim_id": "claim:example:ultimate-parent:2026-09-08",
  "subject": {
    "entity_type": "brand",
    "entity_id": "brand:example"
  },
  "property": "ultimate_parent",
  "value": "company:example-holdings",
  "status": "verified",
  "confidence": "high",
  "observed_at": "2026-09-08",
  "refresh_after": "2027-03-07",
  "evidence": [
    {
      "source": "https://example.com/source",
      "source_type": "official_company",
      "retrieved_at": "2026-09-08",
      "supports": true
    }
  ]
}
```

## Contributions

Contributions are research packages that may contain new entities and one or more claims. They must conform to `schemas/contribution.schema.json` and include a privacy attestation.

## Indexes

Indexes will be added after real records reveal which lookup paths matter most. Likely first indexes:

- GTIN/UPC/EAN → product ID
- normalized brand name → brand ID
- normalized company name → company ID
- retailer/store aliases → entity ID

Do not duplicate the full truth record into indexes; indexes should point to canonical entities/claims.
