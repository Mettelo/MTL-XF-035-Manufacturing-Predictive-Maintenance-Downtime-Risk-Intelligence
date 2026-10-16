# MTL-XF-035 — Data acquisition and engineering

## Approved S1

[AI4I 2020 Predictive Maintenance](https://archive.ics.uci.edu/dataset/601); required files: **ai4i2020.csv**. Expected source population: 10,000 synthetic operating observations.

Exact official download:

https://archive.ics.uci.edu/static/public/601/ai4i+2020+predictive+maintenance+dataset.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

**Grain:** One synthetic operating observation, not an observed machine lifetime or future failure event.

**Required fields:** Type, Air temperature [K], Process temperature [K], Rotational speed [rpm], Torque [Nm], Tool wear [min], Machine failure, TWF, HDF, PWF, OSF, RNF; actual identifier header is UDI.

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results.

## Interpretation and quality

Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
