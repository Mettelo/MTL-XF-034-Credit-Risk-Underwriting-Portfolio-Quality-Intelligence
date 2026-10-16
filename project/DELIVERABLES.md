# MTL-XF-034 — Deliverables and metric contracts

**Decision:** Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot.

Required team outputs follow; this master does not claim they are complete. Each item needs a named author, distinct reviewer, version, evidence link and status.

## D1 — Discovery and requirements

**Due:** Week 2 · **Owner:** Business Analyst / Delivery Lead · **Team location:** docs/01-discovery/

Eight user requirements, prioritised by decision value, each with owner and measurable test; stakeholder map and as-is/to-be workflow for credit model risk and policy review.

**Pass evidence:** All eight link source support, D/AC/DT and Head of Credit Risk approval.

## D2 — Governed source and freeze

**Due:** Week 2 · **Owner:** Data Governance Analyst · **Team location:** docs/02-data-governance/

S1 provenance, rights, dictionary, storage/restore path and immutable byte manifest. All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

**Pass evidence:** Every required file/field is verified and approved; unsupported requirements explicitly block G1.

## D3 — Engineering pipeline and model

**Due:** Week 4 · **Owner:** Data Engineer · **Team location:** src/ and docs/03-data-model/

Versioned ingestion/transformation and curated model. Grain: One historical credit record identified by original row number; not a modern applicant population. Preserve file/sheet/row lineage and all exclusion reasons.

**Pass evidence:** Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist.

## D4 — Quality and exceptions

**Due:** Week 4 · **Owner:** Data Engineer + independent reviewer · **Team location:** docs/04-data-quality/

Profile types, nulls, duplicates, sentinels, labels, units and source support. Address Wrong target coding or interpreting oversampled historical outcomes as current default probabilities would invalidate underwriting conclusions.

**Pass evidence:** Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion.

## D5 — Corrected credit data and outcome audit

**Due:** Week 4 · **Owner:** Credit Risk Analyst · **Business reviewer:** Head of Credit Risk · **Independent reviewer:** Credit Model Risk Analyst

**Required artefact:** data/curated/corrected-credit-data-and-outcome-audit.csv and docs/05-kpi-catalogue/corrected-credit-data-and-outcome-audit.md.

Original-to-English dictionary, kredit mapping, sample class counts, transformed-amount notice and sensitive-field/availability register.

**Mandatory pass condition (SC1):** kredit=0 maps to bad_event=1; totals show 300 bad/700 good before any exclusions; no sex reconstructed from famges and no current monetary exposure invented.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D6 — Explainable risk-screening comparison

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Business reviewer:** Head of Credit Risk · **Independent reviewer:** Credit Model Risk Analyst

**Required artefact:** docs/06-analysis/explainable-risk-screening-comparison.md plus machine-readable evaluation_results.csv.

Constant baseline and regularised logistic candidate; train/validation/test manifest; bad-event precision/recall, balanced accuracy, false referrals and coefficient/explanation report.

**Mandatory pass condition (SC2):** Holdout is untouched until threshold lock; all classes/counts visible; no sampled probability is presented as current population default risk.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D7 — Three cost-sensitive referral policies

**Due:** Week 6 · **Owner:** Credit Risk Analyst · **Business reviewer:** Head of Credit Risk · **Independent reviewer:** Credit Model Risk Analyst

**Required artefact:** docs/07-decision-framework/three-cost-sensitive-referral-policies.csv plus policy.md.

Threshold comparison for FN:FP=1:1, 3:1 and 5:1; confusion matrices, review share, cost and policy recommendation for each.

**Mandatory pass condition (SC3):** FN=2/FP=3 at 5:1 costs 13 assumed units; threshold selection uses validation; adverse scores route to human review with override, never automatic denial.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D8 — Credit-risk review dashboard

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Business reviewer:** Head of Credit Risk · **Independent reviewer:** Credit Model Risk Analyst

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

Sample quality, model/cost comparison, review burden and supported subgroup diagnostics with uncertainty.

**Mandatory pass condition (SC4):** Every subgroup below 30 is labelled insufficient evidence; reviewer finds a missed-bad case and an unnecessary-referral case and traces their policy outcomes.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Credit Model Risk Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Model-risk recommendation and validation plan

**Due:** Week 8 · **Owner:** Business Analyst / Delivery Lead with domain specialist · **Business reviewer:** Head of Credit Risk · **Independent reviewer:** Credit Model Risk Analyst

**Required artefact:** deliverables/model-risk-recommendation-and-validation-plan.pdf plus editable slides and supporting cards/runbook.

Recommend retain baseline, revise prototype or seek modern pilot; identify modern representative data, fairness/legal review, calibration and operational controls required.

**Mandatory pass condition (SC5):** No regulatory compliance/fairness certification; three next actions each have owner, required evidence and acceptance gate before any real lending use.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D12 — Contribution and final submission

**Due:** Weekly; final week 8 · **Owner:** Delivery Lead · **Team location:** CONTRIBUTIONS.md and submission/FINAL_SUBMISSION.md

Named D owners/reviewers, authored work, issues/PRs/commits, substantive reviews and demo/handover contribution for each member.

**Pass evidence:** All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count.

## K1–K7 — Authoritative contracts

| ID | Metric | Definition and population | Grain |
| --- | --- | --- | --- |
| K1 | Sample bad-credit share | bad records / valid labelled records; label sample-only, not population default rate. | full historical cohort |
| K2 | Bad-credit recall | TP/(TP+FN), positive=bad credit. | test |
| K3 | Bad-credit precision | TP/(TP+FP), positive=bad credit. | test |
| K4 | False referral rate | FP/(FP+TN), denominator=good credits. | test |
| K5 | Balanced accuracy | (bad recall + good recall)/2. | test |
| K6 | Review share | flagged high-risk records / evaluated records at locked threshold. | test |
| K7 | Scenario classification cost | cost_FN×FN + cost_FP×FP; cost ratios are assumed units, not currency. | test cost scenarios |

Extend each contract with actual S1 raw fields and curated columns, code lineage, population/exclusions, numerator/denominator, units/grain, aggregation, missing/zero/undefined policy, owner/reviewer, freeze ID and tests. Credit Risk Analyst owns interpretation; Engineer implements; Credit Model Risk Analyst reviews.

Zero denominators produce unavailable values with reasons. Do not average subgroup rates when compatible summed numerators/denominators are required. Show class/segment counts beside rates and uncertainty. Counts reconcile exactly; arithmetic reconciles unrounded or to a documented tolerance no wider than 0.01 displayed unit. No source field can silently be replaced by an assumption.

## Evaluation and decision policy

Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit.

Baseline constant-majority prediction and transparent logistic model; compare validation-selected thresholds under false-negative:false-positive cost ratios 1:1, 3:1 and 5:1. Lock threshold before test. Keep all outcomes as simulated review/referral, not loan approvals.

**Interpretation boundary:** Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

See [acceptance](ACCEPTANCE_CRITERIA.md) for tests and [governance](GOVERNANCE.md) for release decisions.
