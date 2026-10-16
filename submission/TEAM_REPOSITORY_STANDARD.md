# MTL-XF-034 — Team repository standard

Create **MTL-XF-034-<team-name>** under **Mettelo** and add individual member accounts. Record [master URL](https://github.com/Mettelo/MTL-XF-034-Credit-Risk-Underwriting-Portfolio-Quality-Intelligence), reviewed master specification commit and final team commit/tag.

## Required areas

- README.md and CONTRIBUTIONS.md
- data/SOURCE_REGISTER.md; data/raw/README.md; data/reference/; data/metadata/; data/curated/
- docs/01-discovery/; docs/02-data-governance/; docs/03-data-model/; docs/04-data-quality/
- docs/05-kpi-catalogue/; docs/06-analysis/; docs/07-decision-framework/
- docs/08-assurance-uat/; docs/09-technical-handover/
- src/; tests/; dashboard/; deliverables/; submission/FINAL_SUBMISSION.md

Use sql/notebooks/analysis folders where useful; explain unused areas and avoid duplicate implementations. Pin free toolchain/dependencies and one documented run entry point. Keep raw payloads in approved storage outside Git, with verified manifest and reviewer access; never embed credentials.

## README and contribution evidence

State Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot. Name Head of Credit Risk as simulated sponsor. Include cohort, acquisition/restore, environment/run instructions, five findings, baseline/alternative, assumptions, UAT/rerun and evidence links. Preserve the simulated-client declaration and this limit: Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

Assign named people to all seven [brief roles](../project/PROJECT_BRIEF.md). Every member links authored artefacts, at least one substantive review, and demo/handover contribution. Issues, commits, PRs and review records support evidence; commit count or one person's bulk upload is insufficient.

## Project-specific handover

Own corrected outcome coding, cost-matrix scenarios and a policy card showing review capacity and missing modern validation evidence.

Maintain D1–D12/AC1–AC12/DT1–DT10 evidence index with owner, distinct reviewer, state and final-commit path. Connect numeric claims to frozen source and code/configuration. Record all manual adjustments, excluded cases and limitations; preserve an insufficient-evidence case.

## Required business-output artefacts

- **D5 Corrected credit data and outcome audit:** data/curated/corrected-credit-data-and-outcome-audit.csv and docs/05-kpi-catalogue/corrected-credit-data-and-outcome-audit.md.
- **D6 Explainable risk-screening comparison:** docs/06-analysis/explainable-risk-screening-comparison.md plus machine-readable evaluation_results.csv.
- **D7 Three cost-sensitive referral policies:** docs/07-decision-framework/three-cost-sensitive-referral-policies.csv plus policy.md.
- **D8 Credit-risk review dashboard:** dashboard/README.md, runnable dashboard/prototype and static review export.
- **D11 Model-risk recommendation and validation plan:** deliverables/model-risk-recommendation-and-validation-plan.pdf plus editable slides and supporting cards/runbook.

Index these under SC1–SC5 with author, distinct reviewer, executed result and final commit. Treat these paths as the default delivery contract; an equivalent tool-specific format requires an explicit documented mapping.
