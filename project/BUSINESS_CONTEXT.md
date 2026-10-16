# MTL-XF-035 — Business context and practical use case

## Organisation and accountable decision

Confidential Manufacturing Operator is the simulated sponsor. The Plant Maintenance Manager owns the weekly maintenance planning review and must decide: **Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning.**

## The operational problem

The plant maintenance manager has limited inspection slots and needs to decide which operating observations deserve attention first. A simple tool-wear trigger is understandable but may miss failure patterns associated with temperature, speed and torque; a model may capture more failures but create unnecessary inspections. The synthetic dataset supports this inspection-allocation comparison, not proof of advance warning, actual downtime reduction or remaining useful life.

## How the finished product will be used

In weekly maintenance planning, the manager compares the tool-wear baseline with risk-ranked inspection lists at 2%, 5% and 10% capacity, reviews missed failures and false inspections, and approves a supervised plant-data validation plan.

**Current approach:** Prioritise inspections from a single wear rule without a common capacity/error comparison.

**Required future approach:** Review equal-population risk lists with explicit inspection workload, missed-event trade-offs and sensor-evidence limitations.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| Plant Maintenance Manager | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| Reliability and Maintenance Analyst | Interpret sensor units, design a ten-case inspection worklist and specify condition-check, maintenance deferral and escalation actions. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Operational Model Assurance Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Operating-condition and failure-mode ledger** to support the stated decision, with this evidence: All source UDI records, six operational predictors, Machine failure and five separate mode flags; units, overlap counts and quality exceptions.
2. Can the sponsor use **Leakage-controlled failure classification** to support the stated decision, with this evidence: Ordered holdout baseline/model report, predictor allowlist, class counts, recall/precision and stratified sensitivity appendix.
3. Can the sponsor use **Inspection capacity and assumed cost workbook** to support the stated decision, with this evidence: Tool wear≥200 baseline and ranked lists at 2/5/10% capacity; captured/missed failures, inspection count, precision and cost ratios 10:1/50:1.
4. Can the sponsor use **Maintenance planning dashboard** to support the stated decision, with this evidence: Type/condition overview, capacity trade-off, worklist and data/model limitations.
5. Can the sponsor use **Maintenance operating and validation pack** to support the stated decision, with this evidence: Ten-case inspection procedure, review/escalation/deferral rules and real-plant collection plan including timestamps, machine IDs, downtime and repair cost.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Operating-condition and failure-mode ledger | All source UDI records, six operational predictors, Machine failure and five separate mode flags; units, overlap counts and quality exceptions. |
| D6 | Leakage-controlled failure classification | Ordered holdout baseline/model report, predictor allowlist, class counts, recall/precision and stratified sensitivity appendix. |
| D7 | Inspection capacity and assumed cost workbook | Tool wear≥200 baseline and ranked lists at 2/5/10% capacity; captured/missed failures, inspection count, precision and cost ratios 10:1/50:1. |
| D8 | Maintenance planning dashboard | Type/condition overview, capacity trade-off, worklist and data/model limitations. |
| D11 | Maintenance operating and validation pack | Ten-case inspection procedure, review/escalation/deferral rules and real-plant collection plan including timestamps, machine IDs, downtime and repair cost. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Operating-condition and failure-mode ledger | 10,000 source observations accounted for; overlapping modes never inflate unique machine-failure count; Kelvin/rpm/Nm/min retained correctly. |
| SC2 | D6 — Leakage-controlled failure classification | No IDs or TWF/HDF/PWF/OSF/RNF predictors; no invented future horizon; undefined recall in single-class holdouts blocks a model recommendation. |
| SC3 | D7 — Inspection capacity and assumed cost workbook | List sizes floor(capacity×eligible N), deterministic UDI ties; costs reproducible and synthetic; top-ten case register includes sensor signals and review action. |
| SC4 | D8 — Maintenance planning dashboard | Reviewer locates a flagged failure, a false inspection and a missed failure, and explains how the list changes when capacity moves from 5% to 10%. |
| SC5 | D11 — Maintenance operating and validation pack | Every case has accountable maintenance role and next check; no claimed lead time/savings; specify pilot comparator, observation window and safety review before plant action. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

All 10,000 rows from ai4i2020.csv. Preserve UDI/UID and Product ID for lineage; six operational predictors plus machine/failure-mode outcomes.

Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

**Failure to prevent:** Failure-mode leakage or an invented time-to-failure horizon would make apparent predictive performance unusable.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
