# MTL-XF-034 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Credit Model Risk Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Head of Credit Risk approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | kredit=0 maps to bad_event=1; totals show 300 bad/700 good before any exclusions; no sex reconstructed from famges and no current monetary exposure invented. |
| AC6 | D6 / SC2 | Holdout is untouched until threshold lock; all classes/counts visible; no sampled probability is presented as current population default risk. |
| AC7 | D7 / SC3 | FN=2/FP=3 at 5:1 costs 13 assumed units; threshold selection uses validation; adverse scores route to human review with override, never automatic denial. |
| AC8 | D8 / SC4 | Every subgroup below 30 is labelled insufficient evidence; reviewer finds a missed-bad case and an unnecessary-referral case and traces their policy outcomes. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | No regulatory compliance/fairness certification; three next actions each have owner, required evidence and acceptance gate before any real lending use. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Corrected credit data and outcome audit

**Accountable delivery role:** Credit Risk Analyst. **Business reviewer:** Head of Credit Risk. **Independent assurance:** Credit Model Risk Analyst.

**Required artefact:** data/curated/corrected-credit-data-and-outcome-audit.csv and docs/05-kpi-catalogue/corrected-credit-data-and-outcome-audit.md.

**Content:** Original-to-English dictionary, kredit mapping, sample class counts, transformed-amount notice and sensitive-field/availability register.

**Pass condition:** kredit=0 maps to bad_event=1; totals show 300 bad/700 good before any exclusions; no sex reconstructed from famges and no current monetary exposure invented.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Explainable risk-screening comparison

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** Head of Credit Risk. **Independent assurance:** Credit Model Risk Analyst.

**Required artefact:** docs/06-analysis/explainable-risk-screening-comparison.md plus machine-readable evaluation_results.csv.

**Content:** Constant baseline and regularised logistic candidate; train/validation/test manifest; bad-event precision/recall, balanced accuracy, false referrals and coefficient/explanation report.

**Pass condition:** Holdout is untouched until threshold lock; all classes/counts visible; no sampled probability is presented as current population default risk.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Three cost-sensitive referral policies

**Accountable delivery role:** Credit Risk Analyst. **Business reviewer:** Head of Credit Risk. **Independent assurance:** Credit Model Risk Analyst.

**Required artefact:** docs/07-decision-framework/three-cost-sensitive-referral-policies.csv plus policy.md.

**Content:** Threshold comparison for FN:FP=1:1, 3:1 and 5:1; confusion matrices, review share, cost and policy recommendation for each.

**Pass condition:** FN=2/FP=3 at 5:1 costs 13 assumed units; threshold selection uses validation; adverse scores route to human review with override, never automatic denial.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Credit-risk review dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** Head of Credit Risk. **Independent assurance:** Credit Model Risk Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** Sample quality, model/cost comparison, review burden and supported subgroup diagnostics with uncertainty.

**Pass condition:** Every subgroup below 30 is labelled insufficient evidence; reviewer finds a missed-bad case and an unnecessary-referral case and traces their policy outcomes.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Model-risk recommendation and validation plan

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** Head of Credit Risk. **Independent assurance:** Credit Model Risk Analyst.

**Required artefact:** deliverables/model-risk-recommendation-and-validation-plan.pdf plus editable slides and supporting cards/runbook.

**Content:** Recommend retain baseline, revise prototype or seek modern pilot; identify modern representative data, fairness/legal review, calibration and operational controls required.

**Pass condition:** No regulatory compliance/fairness certification; three next actions each have owner, required evidence and acceptance gate before any real lending use.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | Corrected labels | Code-table verified good/bad examples produce documented target mapping; reversed labels fail. |
| DT2 | No sex reconstruction | famges is not converted into a binary sex variable. |
| DT3 | Cost arithmetic | FN=2, FP=3 at 5:1 yields cost 13 assumed units. |
| DT4 | Sparse subgroup | A subgroup below 30 records shows counts and insufficient evidence, not a fairness assurance claim. |
| DT5 | Oversampling notice | Every probability or bad-rate display includes the historical sampled-population caveat. |
| DT6 | Human decision | An adverse model score generates a review recommendation only, with named reviewer and override reason. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three project-specific UAT tasks

1. **Business review:** At model-risk review, the Head of Credit Risk compares transparent screening thresholds under three assumed error-cost ratios, examines bad-credit recall and good-credit referral burden, and decides whether to retain a manual baseline or commission modern validation. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** Every subgroup below 30 is labelled insufficient evidence; reviewer finds a missed-bad case and an unnecessary-referral case and traces their policy outcomes. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
