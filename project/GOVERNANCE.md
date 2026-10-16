# MTL-XF-035 — Governance

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Accountability and gates

Plant Maintenance Manager owns business scope, assumptions and action approval. Governance owns source/rights/freeze; Engineer owns transformations; Reliability and Maintenance Analyst owns interpretation; Operational Model Assurance Analyst independently reviews. The simulated Mettelo panel owns programme acceptance. Record actual team members separately from simulated stakeholder roles.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Plant Maintenance Manager, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Reliability and Maintenance Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Plant Maintenance Manager reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Operational Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Domain controls

Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

**Primary risk:** Failure-mode leakage or an invented time-to-failure horizon would make apparent predictive performance unusable.

Compare a tool-wear rule (Tool wear≥200 min, project baseline) against model top 5% inspection risk ranking. Show top 2%, 5%, 10% capacity scenarios; threshold/capacity is chosen on validation only. Missed-failure:inspection cost ratios 10:1 and 50:1 are assumptions.

All capacity, threshold, financial and review/remediation targets are project assumptions unless explicitly attributed. Human deferrals/overrides record reason, evidence, owner and next review. No production action is authorised by this pack.

## Source and evaluation control

All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

Follow [S1 register](../data/SOURCE_REGISTER.md); preserve original bytes outside Git, immutable snapshot, manifest and reviewer access. Checksum mismatch stops processing until investigated. Never silently replace a variant/feed. No raw data uploaded by this update.

First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results.

Lock target mapping, predictors, timing and policy configuration before test evaluation. Descriptive projects retain resample/sensitivity evidence. Record unsupported metrics and negative findings.

## Change and exception control

Record change ID, requester/date/reason, original/revised source/cohort/requirement, rights/field evidence, affected K/D/AC/DT, time/risk impact, owner, reviewer and decision. New inputs get new freeze IDs and affected checks rerun. Missing mandatory support blocks dependent work.

Each operational exception needs case, rationale, evidence, accountable owner, approval, compensating/manual control, expiry and next review; expired exceptions return to review.

Use only approved public data and fictional operational assumptions. Avoid unnecessary customer identifiers and unsupported protected-characteristic inference.

## Publication and release

Keep attribution, snapshot and limitations in every portfolio/dashboard/slide export. No secrets or private correspondence. Release after all AC/DT/UAT and rerun evidence passes with zero critical/high defects. Record final commit/tag and rollback to approved snapshot/configuration.
