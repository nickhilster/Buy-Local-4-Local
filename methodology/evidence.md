# Evidence Methodology

Buy Local 4 Local is evidence-first. A confident-sounding LLM answer is not evidence.

## Evidence hierarchy

Use the strongest source reasonably available for the specific claim.

### Tier 1 — authoritative primary

Examples:

- government records and tariff schedules;
- securities/corporate filings;
- official registries;
- official company investor/ownership disclosures;
- direct manufacturer statements tied to a specific product/SKU.

Best for ownership, jurisdiction, policy, corporate structure and manufacturing claims.

### Tier 2 — direct commercial source

Examples:

- official product page;
- official retailer listing;
- official brand FAQ;
- packaging or label observed directly.

Useful for product attributes, manufacturing claims, price and availability. Retailer copy is not automatically authoritative about corporate ownership or ingredient provenance.

### Tier 3 — reputable secondary / open dataset

Examples:

- established business databases;
- Open Food Facts/Open Products Facts;
- reputable reporting;
- maintained industry directories.

Useful for discovery and corroboration. Prefer primary verification for material ownership/provenance claims when available.

### Tier 4 — community observation

Examples:

- user-submitted packaging observation;
- local-store observation;
- community-maintained listing.

Potentially valuable, especially for local availability, but should be timestamped and independently corroborated for high-impact claims.

### Tier 5 — agent inference

Inference can guide research but should rarely become canonical evidence by itself.

Examples:

- inferring ownership from a website footer;
- inferring manufacturing from a barcode prefix;
- inferring Canadian control from branding.

These are discovery signals, not verified facts.

## Confidence

Confidence describes the strength of the claim given the available evidence, not how certain the agent feels.

- `very_high`: direct authoritative evidence with little ambiguity;
- `high`: strong primary/direct evidence, possibly corroborated;
- `medium`: credible but incomplete/indirect evidence;
- `low`: weak, conflicting, inferred or community-only evidence.

## Conflict rules

When sources disagree:

1. Preserve the disagreement.
2. Check dates and whether they refer to the same SKU/entity/jurisdiction.
3. Prefer direct authoritative evidence when scope matches.
4. Do not erase older evidence if it explains a historical ownership/manufacturing state.
5. Mark the active claim `disputed` when the conflict cannot be resolved reliably.

## Claim scope

Evidence must match the scope of the claim.

A company-level statement does not prove every SKU is made in Canada. A retailer listing does not prove the manufacturer is Canadian-owned. A national chain listing does not prove stock at a particular store.

Prefer narrower accurate claims over broad convenient ones.

## Provenance language

Use language that matches the evidence:

- `Canadian-controlled` when ultimate control is supported;
- `manufactured in Canada` when manufacturing is supported;
- `made in Canada claim on packaging` when only the packaging claim is observed;
- `listed by retailer` when availability is only a listing;
- `likely` or `unverified` when evidence does not justify certainty.

Never convert ambiguous evidence into a patriotic binary.
