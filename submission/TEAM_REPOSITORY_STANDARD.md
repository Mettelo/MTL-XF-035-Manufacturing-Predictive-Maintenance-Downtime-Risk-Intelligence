# MTL-XF-035 — Team repository standard

Create **MTL-XF-035-<team-name>** under **Mettelo** and add individual member accounts. Record [master URL](https://github.com/Mettelo/MTL-XF-035-Manufacturing-Predictive-Maintenance-Downtime-Risk-Intelligence), reviewed master specification commit and final team commit/tag.

## Required areas

- README.md and CONTRIBUTIONS.md
- data/SOURCE_REGISTER.md; data/raw/README.md; data/reference/; data/metadata/; data/curated/
- docs/01-discovery/; docs/02-data-governance/; docs/03-data-model/; docs/04-data-quality/
- docs/05-kpi-catalogue/; docs/06-analysis/; docs/07-decision-framework/
- docs/08-assurance-uat/; docs/09-technical-handover/
- src/; tests/; dashboard/; deliverables/; submission/FINAL_SUBMISSION.md

Use sql/notebooks/analysis folders where useful; explain unused areas and avoid duplicate implementations. Pin free toolchain/dependencies and one documented run entry point. Keep raw payloads in approved storage outside Git, with verified manifest and reviewer access; never embed credentials.

## README and contribution evidence

State Select a sensor-risk inspection policy and specify the real plant data needed to validate advance warning. Name Plant Maintenance Manager as simulated sponsor. Include cohort, acquisition/restore, environment/run instructions, five findings, baseline/alternative, assumptions, UAT/rerun and evidence links. Preserve the simulated-client declaration and this limit: Failure-mode flags are outcomes and cannot be features for predicting Machine failure. Product IDs and row IDs are excluded from predictors. The data do not prove predictive lead time, remaining useful life or realised maintenance savings.

Assign named people to all seven [brief roles](../project/PROJECT_BRIEF.md). Every member links authored artefacts, at least one substantive review, and demo/handover contribution. Issues, commits, PRs and review records support evidence; commit count or one person's bulk upload is insufficient.

## Project-specific handover

Interpret sensor units, design a ten-case inspection worklist and specify condition-check, maintenance deferral and escalation actions.

Maintain D1–D12/AC1–AC12/DT1–DT10 evidence index with owner, distinct reviewer, state and final-commit path. Connect numeric claims to frozen source and code/configuration. Record all manual adjustments, excluded cases and limitations; preserve an insufficient-evidence case.

## Required business-output artefacts

- **D5 Operating-condition and failure-mode ledger:** data/curated/operating-condition-and-failure-mode-ledger.csv and docs/05-kpi-catalogue/operating-condition-and-failure-mode-ledger.md.
- **D6 Leakage-controlled failure classification:** docs/06-analysis/leakage-controlled-failure-classification.md plus machine-readable evaluation_results.csv.
- **D7 Inspection capacity and assumed cost workbook:** docs/07-decision-framework/inspection-capacity-and-assumed-cost-workbook.csv plus policy.md.
- **D8 Maintenance planning dashboard:** dashboard/README.md, runnable dashboard/prototype and static review export.
- **D11 Maintenance operating and validation pack:** deliverables/maintenance-operating-and-validation-pack.pdf plus editable slides and supporting cards/runbook.

Index these under SC1–SC5 with author, distinct reviewer, executed result and final commit. Treat these paths as the default delivery contract; an equivalent tool-specific format requires an explicit documented mapping.
