# MTL-XF-035 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Operational Model Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Plant Maintenance Manager approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | 10,000 source observations accounted for; overlapping modes never inflate unique machine-failure count; Kelvin/rpm/Nm/min retained correctly. |
| AC6 | D6 / SC2 | No IDs or TWF/HDF/PWF/OSF/RNF predictors; no invented future horizon; undefined recall in single-class holdouts blocks a model recommendation. |
| AC7 | D7 / SC3 | List sizes floor(capacity×eligible N), deterministic UDI ties; costs reproducible and synthetic; top-ten case register includes sensor signals and review action. |
| AC8 | D8 / SC4 | Reviewer locates a flagged failure, a false inspection and a missed failure, and explains how the list changes when capacity moves from 5% to 10%. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | Every case has accountable maintenance role and next check; no claimed lead time/savings; specify pilot comparator, observation window and safety review before plant action. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Operating-condition and failure-mode ledger

**Accountable delivery role:** Reliability and Maintenance Analyst. **Business reviewer:** Plant Maintenance Manager. **Independent assurance:** Operational Model Assurance Analyst.

**Required artefact:** data/curated/operating-condition-and-failure-mode-ledger.csv and docs/05-kpi-catalogue/operating-condition-and-failure-mode-ledger.md.

**Content:** All source UDI records, six operational predictors, Machine failure and five separate mode flags; units, overlap counts and quality exceptions.

**Pass condition:** 10,000 source observations accounted for; overlapping modes never inflate unique machine-failure count; Kelvin/rpm/Nm/min retained correctly.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Leakage-controlled failure classification

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** Plant Maintenance Manager. **Independent assurance:** Operational Model Assurance Analyst.

**Required artefact:** docs/06-analysis/leakage-controlled-failure-classification.md plus machine-readable evaluation_results.csv.

**Content:** Ordered holdout baseline/model report, predictor allowlist, class counts, recall/precision and stratified sensitivity appendix.

**Pass condition:** No IDs or TWF/HDF/PWF/OSF/RNF predictors; no invented future horizon; undefined recall in single-class holdouts blocks a model recommendation.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Inspection capacity and assumed cost workbook

**Accountable delivery role:** Reliability and Maintenance Analyst. **Business reviewer:** Plant Maintenance Manager. **Independent assurance:** Operational Model Assurance Analyst.

**Required artefact:** docs/07-decision-framework/inspection-capacity-and-assumed-cost-workbook.csv plus policy.md.

**Content:** Tool wear≥200 baseline and ranked lists at 2/5/10% capacity; captured/missed failures, inspection count, precision and cost ratios 10:1/50:1.

**Pass condition:** List sizes floor(capacity×eligible N), deterministic UDI ties; costs reproducible and synthetic; top-ten case register includes sensor signals and review action.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Maintenance planning dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** Plant Maintenance Manager. **Independent assurance:** Operational Model Assurance Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** Type/condition overview, capacity trade-off, worklist and data/model limitations.

**Pass condition:** Reviewer locates a flagged failure, a false inspection and a missed failure, and explains how the list changes when capacity moves from 5% to 10%.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Maintenance operating and validation pack

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** Plant Maintenance Manager. **Independent assurance:** Operational Model Assurance Analyst.

**Required artefact:** deliverables/maintenance-operating-and-validation-pack.pdf plus editable slides and supporting cards/runbook.

**Content:** Ten-case inspection procedure, review/escalation/deferral rules and real-plant collection plan including timestamps, machine IDs, downtime and repair cost.

**Pass condition:** Every case has accountable maintenance role and next check; no claimed lead time/savings; specify pilot comparator, observation window and safety review before plant action.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | Leakage columns | Presence of TWF/HDF/PWF/OSF/RNF or Machine failure in predictors fails. |
| DT2 | Overlapping modes | One row with two mode flags counts as one machine-failure observation and two mode occurrences. |
| DT3 | Temperature units | 310 K minus 300 K produces differential 10 K; do not confuse absolute Kelvin and Celsius. |
| DT4 | Capacity floor | For N=101, 5% capacity returns floor(5.05)=5 observations using a stable tie rule. |
| DT5 | No horizon | An output claiming a failure will occur within 24 hours fails because no validated horizon exists. |
| DT6 | Single-class split | An ordered test with no positives reports undefined recall and blocks model recommendation rather than showing perfect recall. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three project-specific UAT tasks

1. **Business review:** In weekly maintenance planning, the manager compares the tool-wear baseline with risk-ranked inspection lists at 2%, 5% and 10% capacity, reviews missed failures and false inspections, and approves a supervised plant-data validation plan. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** Reviewer locates a flagged failure, a false inspection and a missed failure, and explains how the list changes when capacity moves from 5% to 10%. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
