# MTL-XF-035 — Source register

## S1 — AI4I 2020 Predictive Maintenance

| Field | Approved definition |
| --- | --- |
| Provider | UCI Machine Learning Repository; preserve original creator attribution |
| Documentation | https://archive.ics.uci.edu/dataset/601 |
| Exact download | https://archive.ics.uci.edu/static/public/601/ai4i+2020+predictive+maintenance+dataset.zip |
| Required inputs | ai4i2020.csv |
| Source population | 10,000 synthetic operating observations |
| Decision owner | Plant Maintenance Manager |
| Status | Official archive/feed retrieved and inspected; team freeze/sign-off and analysis remain to be completed. No raw data uploaded. |

Persistent citation: https://doi.org/10.24432/C5HS5C

## Checked byte reference

Official archive retrieved and inspected on **2026-10-16**. Archive size **522170 bytes**; SHA-256 **f601f14294bcf190f9d720676b7f0aea46a26cde9ab8ebc7b4f8174d9d26b252**.

| Archive member | Bytes | SHA-256 |
| --- | --- | --- |
| ai4i2020.csv | 522048 | dc6630cd9b1f0f853922fad78a1b6436570d3f1ec863f1dd5c4340ac56bc8a8e |

Member names and byte hashes were inspected; CSV record counts were checked where present. Actual cohort transformations and business analysis remain team delivery work.

Preserve actual header spellings, field types and original row order; distinguish identifiers, predictors and outcomes.

## Cohort and field support

All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

**Grain:** One synthetic operating observation, not an observed machine lifetime or future failure event.

**Required mapping:** Type, Air temperature [K], Process temperature [K], Rotational speed [rpm], Torque [Nm], Tool wear [min], Machine failure, TWF, HDF, PWF, OSF, RNF; actual identifier header is UDI.

**Interpretation limits:** Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

## Rights and attribution

Publisher page declares [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite original creators, UCI and [dataset DOI](https://doi.org/10.24432/C5HS5C); preserve notices and state transformations.

## Team acquisition record required at G1

Record source/freeze ID, requested/resolved URL, retrieval UTC, release/feed timestamp, archive/member filename, actual bytes/checksum, encoding/delimiter/worksheet/schema, row count, date bounds, included/excluded scope, licence/citation evidence, storage/access and retention owner, verification checks, analyst and reviewer approval/date. Unknown or unexecuted fields remain explicitly pending.

## Raw-data durability

Preserve original archive, required members and documentation in a read-only S1-v1 snapshot in approved durable storage outside Git with a second recoverable copy. Record reviewer access and restore instructions without credentials. Provider/DOI URLs locate the source; retained checksum-addressed bytes define reproducibility. Stable URLs do not guarantee immutable contents or perpetual availability.

No raw data are committed by this master update. Restore verified retained bytes if the provider becomes unavailable. If no approved copy exists, block G1; do not substitute an unofficial mirror, another variant or guessed schema. A new official version requires rights/schema/scope review, new freeze ID and rerun of affected tests.

## Refresh and supplementary inputs

Do not stack overlapping UCI samples/variants. Required publisher codebooks remain source references. Business costs, capacities and pilot outcomes absent from S1 are synthetic assumptions, not measured facts.

Every added reference/supplement needs ID, official source/version/URL, rights, grain/coverage, purpose, join key/cardinality, effect on K/D/AC/DT and reviewer approval. Optional extensions cannot replace core requirements silently.
