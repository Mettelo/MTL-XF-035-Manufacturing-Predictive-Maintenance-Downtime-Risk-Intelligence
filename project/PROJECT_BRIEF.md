# MTL-XF-035 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Manufacturing Operator · **Sponsor:** Plant Maintenance Manager · **Team:** 6–8 · **Duration:** 8 weeks · **Cycle:** weekly maintenance planning review

## Problem and commission

Maintenance staff need a defensible way to allocate limited inspection capacity. A synthetic failure dataset allows comparison of sensor-based warning rules and classifiers, but has no actual downtime duration, repair cost or verified advance failure horizon.

> Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning.

## Core scope

All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

Required source: ai4i2020.csv. Model grain: One synthetic operating observation, not an observed machine lifetime or future failure event.

Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review Failure-mode leakage or an invented time-to-failure horizon would make apparent predictive performance unusable. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: One synthetic operating observation, not an observed machine lifetime or future failure event. |
| Reliability and Maintenance Analyst | Interpret sensor units, design a ten-case inspection worklist and specify condition-check, maintenance deferral and escalation actions. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results. |
| BI / Decision Product Developer | Four views for the weekly maintenance planning review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Operational Model Assurance Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Compare a tool-wear rule (Tool wear≥200 min, project baseline) against model top 5% inspection risk ranking. Show top 2%, 5%, 10% capacity scenarios; threshold/capacity is chosen on validation only. Missed-failure:inspection cost ratios 10:1 and 50:1 are assumptions.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Plant Maintenance Manager, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Reliability and Maintenance Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Plant Maintenance Manager reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Operational Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).
