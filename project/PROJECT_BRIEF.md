# MTL-XF-035 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Manufacturing Operator · **Sponsor:** Plant Maintenance Manager · **Team:** 3–5 · **Duration:** 8 weeks · **Cycle:** weekly maintenance planning review

## Problem and commission

The plant maintenance manager has limited inspection slots and needs to decide which operating observations deserve attention first. A simple tool-wear trigger is understandable but may miss failure patterns associated with temperature, speed and torque; a model may capture more failures but create unnecessary inspections. The synthetic dataset supports this inspection-allocation comparison, not proof of advance warning, actual downtime reduction or remaining useful life.

> Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning.

## Practical use case and business outputs

In weekly maintenance planning, the manager compares the tool-wear baseline with risk-ranked inspection lists at 2%, 5% and 10% capacity, reviews missed failures and false inspections, and approves a supervised plant-data validation plan.

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Operating-condition and failure-mode ledger | All source UDI records, six operational predictors, Machine failure and five separate mode flags; units, overlap counts and quality exceptions. |
| D6 | Leakage-controlled failure classification | Ordered holdout baseline/model report, predictor allowlist, class counts, recall/precision and stratified sensitivity appendix. |
| D7 | Inspection capacity and assumed cost workbook | Tool wear≥200 baseline and ranked lists at 2/5/10% capacity; captured/missed failures, inspection count, precision and cost ratios 10:1/50:1. |
| D8 | Maintenance planning dashboard | Type/condition overview, capacity trade-off, worklist and data/model limitations. |
| D11 | Maintenance operating and validation pack | Ten-case inspection procedure, review/escalation/deferral rules and real-plant collection plan including timestamps, machine IDs, downtime and repair cost. |

## Required success contract

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Operating-condition and failure-mode ledger | 10,000 source observations accounted for; overlapping modes never inflate unique machine-failure count; Kelvin/rpm/Nm/min retained correctly. |
| SC2 | D6 — Leakage-controlled failure classification | No IDs or TWF/HDF/PWF/OSF/RNF predictors; no invented future horizon; undefined recall in single-class holdouts blocks a model recommendation. |
| SC3 | D7 — Inspection capacity and assumed cost workbook | List sizes floor(capacity×eligible N), deterministic UDI ties; costs reproducible and synthetic; top-ten case register includes sensor signals and review action. |
| SC4 | D8 — Maintenance planning dashboard | Reviewer locates a flagged failure, a false inspection and a missed failure, and explains how the list changes when capacity moves from 5% to 10%. |
| SC5 | D11 — Maintenance operating and validation pack | Every case has accountable maintenance role and next check; no claimed lead time/savings; specify pilot comparator, observation window and safety review before plant action. |

[Detailed acceptance](ACCEPTANCE_CRITERIA.md) defines executed evidence; [deliverables](DELIVERABLES.md) defines exact artefacts and ownership. G1 records simulated sponsor approval, not invented real-client agreement.

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

## Team organisation

The recommended team size is **3–5 people**. Delivery roles describe responsibilities, not separate positions: members can combine complementary business analysis, governance, engineering, analysis/modelling, BI and domain responsibilities. Assign a named owner to each deliverable and use a different team member to review critical calculations and perform the final clean rerun.
