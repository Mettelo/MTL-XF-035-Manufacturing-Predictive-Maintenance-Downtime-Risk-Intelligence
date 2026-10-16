# MTL-XF-035 — Manufacturing Predictive Maintenance Downtime Risk Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 6–8 · **Duration:** 8 weeks

## The business problem

The plant maintenance manager has limited inspection slots and needs to decide which operating observations deserve attention first. A simple tool-wear trigger is understandable but may miss failure patterns associated with temperature, speed and torque; a model may capture more failures but create unnecessary inspections. The synthetic dataset supports this inspection-allocation comparison, not proof of advance warning, actual downtime reduction or remaining useful life.

**Simulated organisation:** Confidential Manufacturing Operator. **Accountable decision owner:** Plant Maintenance Manager.

## Practical use case

In weekly maintenance planning, the manager compares the tool-wear baseline with risk-ranked inspection lists at 2%, 5% and 10% capacity, reviews missed failures and false inspections, and approves a supervised plant-data validation plan.

**Decision the project must enable:** Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning.

**Current approach:** Prioritise inspections from a single wear rule without a common capacity/error comparison.

**Required future approach:** Review equal-population risk lists with explicit inspection workload, missed-event trade-offs and sensor-evidence limitations.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Operating-condition and failure-mode ledger | All source UDI records, six operational predictors, Machine failure and five separate mode flags; units, overlap counts and quality exceptions. |
| D6 | Leakage-controlled failure classification | Ordered holdout baseline/model report, predictor allowlist, class counts, recall/precision and stratified sensitivity appendix. |
| D7 | Inspection capacity and assumed cost workbook | Tool wear≥200 baseline and ranked lists at 2/5/10% capacity; captured/missed failures, inspection count, precision and cost ratios 10:1/50:1. |
| D8 | Maintenance planning dashboard | Type/condition overview, capacity trade-off, worklist and data/model limitations. |
| D11 | Maintenance operating and validation pack | Ten-case inspection procedure, review/escalation/deferral rules and real-plant collection plan including timestamps, machine IDs, downtime and repair cost. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Operating-condition and failure-mode ledger | 10,000 source observations accounted for; overlapping modes never inflate unique machine-failure count; Kelvin/rpm/Nm/min retained correctly. |
| SC2 | D6 — Leakage-controlled failure classification | No IDs or TWF/HDF/PWF/OSF/RNF predictors; no invented future horizon; undefined recall in single-class holdouts blocks a model recommendation. |
| SC3 | D7 — Inspection capacity and assumed cost workbook | List sizes floor(capacity×eligible N), deterministic UDI ties; costs reproducible and synthetic; top-ten case register includes sensor signals and review action. |
| SC4 | D8 — Maintenance planning dashboard | Reviewer locates a flagged failure, a false inspection and a missed failure, and explains how the list changes when capacity moves from 5% to 10%. |
| SC5 | D11 — Maintenance operating and validation pack | Every case has accountable maintenance role and next check; no claimed lead time/savings; specify pilot comparator, observation window and safety review before plant action. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [AI4I 2020 Predictive Maintenance](https://archive.ics.uci.edu/dataset/601). **Required input:** ai4i2020.csv. **Expected source population:** 10,000 synthetic operating observations.

All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

**Download:** https://archive.ics.uci.edu/static/public/601/ai4i+2020+predictive+maintenance+dataset.zip

Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results.

Compare a tool-wear rule (Tool wear≥200 min, project baseline) against model top 5% inspection risk ranking. Show top 2%, 5%, 10% capacity scenarios; threshold/capacity is chosen on validation only. Missed-failure:inspection cost ratios 10:1 and 50:1 are assumptions.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- Reliability and Maintenance Analyst: Interpret sensor units, design a ten-case inspection worklist and specify condition-check, maintenance deferral and escalation actions.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Operational Model Assurance Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Plant Maintenance Manager, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Reliability and Maintenance Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Plant Maintenance Manager reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Operational Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
