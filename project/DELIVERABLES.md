# MTL-XF-035 — Deliverables and metric contracts

**Decision:** Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning.

Required team outputs follow; this master does not claim they are complete. Each item needs a named author, distinct reviewer, version, evidence link and status.

## D1 — Discovery and requirements

**Due:** Week 2 · **Owner:** Business Analyst / Delivery Lead · **Team location:** docs/01-discovery/

Eight user requirements, prioritised by decision value, each with owner and measurable test; stakeholder map and as-is/to-be workflow for weekly maintenance planning review.

**Pass evidence:** All eight link source support, D/AC/DT and Plant Maintenance Manager approval.

## D2 — Governed source and freeze

**Due:** Week 2 · **Owner:** Data Governance Analyst · **Team location:** docs/02-data-governance/

S1 provenance, rights, dictionary, storage/restore path and immutable byte manifest. All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

**Pass evidence:** Every required file/field is verified and approved; unsupported requirements explicitly block G1.

## D3 — Engineering pipeline and model

**Due:** Week 4 · **Owner:** Data Engineer · **Team location:** src/ and docs/03-data-model/

Versioned ingestion/transformation and curated model. Grain: One synthetic operating observation, not an observed machine lifetime or future failure event. Preserve file/sheet/row lineage and all exclusion reasons.

**Pass evidence:** Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist.

## D4 — Quality and exceptions

**Due:** Week 4 · **Owner:** Data Engineer + independent reviewer · **Team location:** docs/04-data-quality/

Profile types, nulls, duplicates, sentinels, labels, units and source support. Address Failure-mode leakage or an invented time-to-failure horizon would make apparent predictive performance unusable.

**Pass evidence:** Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion.

## D5 — KPI catalogue and lineage

**Due:** Week 4 · **Owner:** Reliability and Maintenance Analyst · **Team location:** docs/05-kpi-catalogue/

Implement K1–K7 below with actual source fields, code, valid population, denominator, units, grain, exclusions, owner and worked examples.

**Pass evidence:** All seven reviewed; K1–K5 reconcile independently and in BI on full cohort and one filtered slice.

## D6 — Analysis and evaluation

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Team location:** docs/06-analysis/

First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results.

**Pass evidence:** Baseline and alternative results, population/class counts, uncertainty, negative findings and feature/timing audit retained; no test-driven tuning.

## D7 — Decision policy and action register

**Due:** Week 6 · **Owner:** Reliability and Maintenance Analyst · **Team location:** docs/07-decision-framework/

Compare a tool-wear rule (Tool wear≥200 min, project baseline) against model top 5% inspection risk ranking. Show top 2%, 5%, 10% capacity scenarios; threshold/capacity is chosen on validation only. Missed-failure:inspection cost ratios 10:1 and 50:1 are assumptions.

**Pass evidence:** Both policies and sensitivity outputs supplied; every action has evidence, eligibility, owner, next review and uncertainty. Include a defer case.

## D8 — Dashboard / decision prototype

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Team location:** dashboard/

Four linked views: K1–K7 executive overview, source-supported diagnostics, policy/action comparison and quality/limitations for Plant Maintenance Manager.

**Pass evidence:** Five metric/filter checks pass; frozen scope and limitations survive export; static copy/user guide require no paid access.

## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Operational Model Assurance Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Executive recommendation

**Due:** Week 8 · **Owner:** Delivery Lead + domain specialist · **Team location:** deliverables/

8–12 slides and a 5–10-minute demo answering Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning. Include five evidence-linked findings, three next actions, comparison and a defer case.

**Pass evidence:** Every numeric claim links tested evidence; costs/benefits and operational targets are labelled assumptions unless measured.

## D12 — Contribution and final submission

**Due:** Weekly; final week 8 · **Owner:** Delivery Lead · **Team location:** CONTRIBUTIONS.md and submission/FINAL_SUBMISSION.md

Named D owners/reviewers, authored work, issues/PRs/commits, substantive reviews and demo/handover contribution for each member.

**Pass evidence:** All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count.

## K1–K7 — Authoritative contracts

| ID | Metric | Definition and population | Grain |
| --- | --- | --- | --- |
| K1 | Observation failure share | count(Machine failure=1)/valid observations; synthetic prevalence only. | cohort/type |
| K2 | Failure-mode frequency | count(each mode=1)/observations; modes may overlap and must not be summed as distinct events. | each of five modes |
| K3 | Failure recall at capacity | flagged actual failures / all failures. | test at 2/5/10% review capacity |
| K4 | Inspection precision | flagged actual failures / inspected observations. | test |
| K5 | Inspection share | inspected observations / eligible observations. | test |
| K6 | Temperature differential | Process temperature−Air temperature in K, with median and tails. | Type |
| K7 | Assumed inspection cost | inspection_count×unit inspection cost + missed_failures×assumed missed-failure cost. | two assumed cost ratios |

Extend each contract with actual S1 raw fields and curated columns, code lineage, population/exclusions, numerator/denominator, units/grain, aggregation, missing/zero/undefined policy, owner/reviewer, freeze ID and tests. Reliability and Maintenance Analyst owns interpretation; Engineer implements; Operational Model Assurance Analyst reviews.

Zero denominators produce unavailable values with reasons. Do not average subgroup rates when compatible summed numerators/denominators are required. Show class/segment counts beside rates and uncertainty. Counts reconcile exactly; arithmetic reconciles unrounded or to a documented tolerance no wider than 0.01 displayed unit. No source field can silently be replaced by an assumption.

## Evaluation and decision policy

First 60%, next 20%, last 20% of original UDI order to expose sequential structure; document class counts and any single-class split limitation. Train-only preprocessing; exclude identifiers and all five failure-mode flags. Add stratified seed-35 split as sensitivity only, not a replacement for weak ordered results.

Compare a tool-wear rule (Tool wear≥200 min, project baseline) against model top 5% inspection risk ranking. Show top 2%, 5%, 10% capacity scenarios; threshold/capacity is chosen on validation only. Missed-failure:inspection cost ratios 10:1 and 50:1 are assumptions.

**Interpretation boundary:** Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

See [acceptance](ACCEPTANCE_CRITERIA.md) for tests and [governance](GOVERNANCE.md) for release decisions.
