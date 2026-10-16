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

## D5 — KPI catalogue and lineage

**Due:** Week 4 · **Owner:** Credit Risk Analyst · **Team location:** docs/05-kpi-catalogue/

Implement K1–K7 below with actual source fields, code, valid population, denominator, units, grain, exclusions, owner and worked examples.

**Pass evidence:** All seven reviewed; K1–K5 reconcile independently and in BI on full cohort and one filtered slice.

## D6 — Analysis and evaluation

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Team location:** docs/06-analysis/

Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit.

**Pass evidence:** Baseline and alternative results, population/class counts, uncertainty, negative findings and feature/timing audit retained; no test-driven tuning.

## D7 — Decision policy and action register

**Due:** Week 6 · **Owner:** Credit Risk Analyst · **Team location:** docs/07-decision-framework/

Baseline constant-majority prediction and transparent logistic model; compare validation-selected thresholds under false-negative:false-positive cost ratios 1:1, 3:1 and 5:1. Lock threshold before test. Keep all outcomes as simulated review/referral, not loan approvals.

**Pass evidence:** Both policies and sensitivity outputs supplied; every action has evidence, eligibility, owner, next review and uncertainty. Include a defer case.

## D8 — Dashboard / decision prototype

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Team location:** dashboard/

Four linked views: K1–K7 executive overview, source-supported diagnostics, policy/action comparison and quality/limitations for Head of Credit Risk.

**Pass evidence:** Five metric/filter checks pass; frozen scope and limitations survive export; static copy/user guide require no paid access.

## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Credit Model Risk Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Executive recommendation

**Due:** Week 8 · **Owner:** Delivery Lead + domain specialist · **Team location:** deliverables/

8–12 slides and a 5–10-minute demo answering Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot. Include five evidence-linked findings, three next actions, comparison and a defer case.

**Pass evidence:** Every numeric claim links tested evidence; costs/benefits and operational targets are labelled assumptions unless measured.

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
