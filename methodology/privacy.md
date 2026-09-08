# Privacy Boundary

The project deliberately separates **private personalization** from **public provenance**.

## Private by default

The following must not be contributed to the public dataset through the standard agent workflow:

- user name or account identity;
- home address or precise personal location;
- shopping history;
- recipes tied to an identifiable user;
- dietary, medical or health information;
- household composition;
- pet ownership tied to the user;
- financial information or budget details tied to the user;
- private conversation content;
- private assistant memories;
- credentials, tokens or connected-account data;
- personal preference profiles.

The agent may use relevant private context locally to determine what to research and recommend.

## Publicly contributable

After sanitization, the following may be proposed when supported by evidence:

- product identity and identifiers;
- brand/company relationships;
- ultimate corporate control;
- manufacturing/processing locations;
- public ingredient/material provenance claims;
- public tariff/trade-measure information;
- retailer/company ownership;
- public store/business information;
- non-personal product availability observations;
- evidence sources and retrieval dates.

## The transformation rule

Private prompt:

> I buy Brand X every week from the No Frills near my apartment. Find me a better option.

Potential public contribution:

> Brand X is controlled by Company Y in jurisdiction Z, supported by sources A/B.

The first sentence is private context. The second can be public provenance.

## Contribution sanitation checklist

Before creating a contribution:

1. Remove names, user IDs and account references.
2. Remove personal addresses/coordinates and habitual-location descriptions.
3. Remove private conversation excerpts.
4. Remove reasons that reveal health, financial or other sensitive personal context.
5. Keep only facts that remain useful to an unrelated future user.
6. Set the contribution privacy attestation accurately.

If sanitization is uncertain, do not submit automatically.

## Public store data

A store's public address, hours, business name and public catalog information are not considered the user's personal information merely because the user shops there. However, the contribution must not say that a particular user frequents that store or reveal their home/work proximity.
