# MTL-XF-035 — Manufacturing Predictive Maintenance Downtime Risk Intelligence

**Track:** Cross-Functional · **Use case:** Commercial / private sector · **Team:** 6–8 · **Duration:** 8 weeks

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Business commission

**Client:** Confidential Manufacturing Operator. **Decision owner:** Plant Maintenance Manager. **Cadence:** weekly maintenance planning review.

Maintenance staff need a defensible way to allocate limited inspection capacity. A synthetic failure dataset allows comparison of sensor-based warning rules and classifiers, but has no actual downtime duration, repair cost or verified advance failure horizon.

**Decision:** Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning.

## End-to-end delivery

Deliver business requirements, governed source acquisition, engineering and data quality, seven defined metrics, baseline/alternative policy comparison, decision dashboard, assurance/UAT, executive recommendation and operational handover. A model alone is insufficient.

Compare a tool-wear rule (Tool wear≥200 min, project baseline) against model top 5% inspection risk ranking. Show top 2%, 5%, 10% capacity scenarios; threshold/capacity is chosen on validation only. Missed-failure:inspection cost ratios 10:1 and 50:1 are assumptions.

## Core dataset and frozen cohort

**S1:** [AI4I 2020 Predictive Maintenance](https://archive.ics.uci.edu/dataset/601). **Input:** ai4i2020.csv. **Source population:** 10,000 synthetic operating observations.

All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

Exact official download:

https://archive.ics.uci.edu/static/public/601/ai4i+2020+predictive+maintenance+dataset.zip

Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

No raw data are uploaded by this update. Teams preserve original bytes outside Git in an approved durable snapshot, with checksums, source metadata and reviewer access. The source register records verification evidence and acquisition rules.

## Pack navigation

- [Project brief](project/PROJECT_BRIEF.md) — scope, roles and milestones.
- [Business context](project/BUSINESS_CONTEXT.md) — stakeholders and decisions.
- [Deliverables](project/DELIVERABLES.md) — D1–D12 and K1–K7.
- [Acceptance criteria](project/ACCEPTANCE_CRITERIA.md) — AC1–AC12 and DT1–DT10.
- [Governance](project/GOVERNANCE.md) — gates, assumptions and changes.
- [Data guidance](data/README.md) and [source register](data/SOURCE_REGISTER.md).
- [Submission pack](submission/README.md) — team repository and final evidence.

## Evaluation and policy boundary

First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results.

**Primary risk:** Failure-mode leakage or an invented time-to-failure horizon would make apparent predictive performance unusable.

At G1 (week 2), approve requirements, source rights, actual schema and frozen bytes. At G2 (week 4), approve row accounting, all seven metrics and evaluation design. At G3 (week 6), review baseline/alternative and uncertainty. At G4 (week 8), require all twelve deliverables, ten executed domain tests, three UAT tasks, five reconciliations and a distinct-member clean rerun.

Assign named authors and review partners. Unsupported mandatory outputs remain blocked until an approved source/scope change resolves them. Record actual results in a separate Mettelo team repository; this master defines the work.
