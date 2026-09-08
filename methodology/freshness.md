# Freshness Policy

Freshness is evaluated per claim, not per product.

A stale tariff claim should not force re-research of ownership. A recent retailer listing should not make an old ownership claim fresh.

## Default review intervals

These are starting defaults for dogfooding, not permanent law.

| Claim type | Default review interval | Notes |
|---|---:|---|
| Ultimate corporate control | 180 days | Recheck sooner after mergers, acquisitions, restructurings or credible conflict |
| Brand ownership | 180 days | Same exception as corporate control |
| Company jurisdiction/control | 180 days | Recheck when corporate structure changes |
| Manufacturing location | 90 days | Product-specific where possible |
| Processing/packaging location | 90 days | Product-specific |
| Major ingredient/material origin | 60 days | Use only when relevant and evidence supports it |
| Government tariff/countermeasure | 7 days | Recheck immediately when policy news indicates change |
| Remission/exemption | 7 days | Effective dates matter |
| Chain-level product listing | 7 days | Listing is not store-level inventory |
| Retail price | 24 hours | Treat as approximate unless live/current |
| Store-level availability | 24 hours | Prefer live store verification when important |
| Store hours | 7 days | Holiday hours can change faster |
| User preference | Event-driven | Private context only |

## Rules

1. `refresh_after` may override the default when there is a clear reason.
2. A claim can become stale before its nominal date when credible contradictory evidence appears.
3. A claim is not automatically true merely because it is fresh.
4. Strong primary evidence can justify a longer interval for slow-changing facts.
5. Volatile fields should be checked near decision time when they materially affect the recommendation.
6. When the exact SKU matters, do not substitute brand-level freshness for product-level evidence.

## Revalidation order

When a claim is stale:

1. Check whether a newer canonical claim already exists.
2. Revisit the strongest previously cited primary source.
3. Search for authoritative evidence of change.
4. Update only the affected claim and dependent conclusions.

The goal is selective revalidation, not wholesale re-research.
