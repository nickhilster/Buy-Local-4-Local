# Purchasing Policy

This file defines the default decision logic. It is a preference layer, not the truth layer.

## Default objective

Keep more economic value in Canada where practical, reduce unnecessary U.S. corporate dependence, and still respect quality, price, safety, accessibility, compatibility and user preference.

## Default ranking

1. Canadian-owned + Canadian-made
2. Canadian-made
3. Canadian-owned with foreign manufacturing/imports
4. Credible non-U.S. alternative
5. U.S.-controlled product where necessary or clearly preferable

Do not force a lower-quality, unsafe, inaccessible or materially unsuitable choice merely to satisfy nationality preference.

## Dimensions to consider

Evaluate candidates across separable dimensions:

- ultimate corporate control;
- manufacturing/processing location;
- major input origin when meaningful and knowable;
- retailer ownership/control;
- Canadian employment/local economic activity where defensibly supported;
- current tariff/trade exposure;
- availability near the user;
- price/value;
- product suitability and quality;
- user-stated constraints.

## Tariff prioritization

Current Canadian trade measures should increase research priority for affected categories, but tariff status is not the definition of whether a product is Canadian.

A useful prioritization heuristic is:

`research priority ≈ purchase frequency × policy exposure × realistic substitutability`

High-frequency repeat purchases with meaningful U.S. exposure deserve attention before rare purchases with no practical alternative.

## International foods

International foods are first-class candidates.

When no sensible Canadian-made substitute exists, distinguish between:

- foreign-made product sold by a Canadian independent retailer;
- foreign-made product sold by a Canadian-controlled chain;
- foreign-made product sold by a U.S.-controlled retailer;
- U.S.-made/U.S.-controlled product.

Retail economics can change the recommendation even when product provenance is identical.

## Availability rule

Do not recommend theoretical alternatives as though they are actionable.

Use these availability labels where useful:

- `store_verified`
- `chain_listed`
- `online_listed`
- `likely_local`
- `unknown`

## Explanation rule

Avoid opaque scores as the only answer. A score may eventually summarize the model, but the user should be able to see why a recommendation ranked well.

Prefer explanations such as:

> Canadian-controlled company; manufactured in Ontario; available at your usual retailer.

or:

> Imported from India and not Canadian-made, but sold through a Canadian independent grocer with no identified U.S. parent.

## Exception rule

The user may explicitly choose a U.S.-controlled product because it is materially better, required for compatibility, medically/dietarily necessary, substantially cheaper, or simply preferred.

Record that as a user decision in private context. Do not reinterpret the exception as a failure of the protocol.
