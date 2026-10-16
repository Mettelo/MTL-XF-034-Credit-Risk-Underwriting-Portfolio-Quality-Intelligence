# MTL-XF-034 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Consumer Lender · **Sponsor:** Head of Credit Risk · **Team:** 6–8 · **Duration:** 8 weeks · **Cycle:** credit model risk and policy review

## Problem and commission

The lender's risk team must compare a conservative referral policy with a policy that sends fewer low-risk cases for manual review. Missed bad-credit cases and unnecessary referrals have different consequences, so accuracy alone cannot decide the policy. The historical sample is intentionally enriched with bad credits and uses corrected coding; treating it as today's applicant population would produce an unjustified lending policy.

> Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot.

## Practical use case and business outputs

At model-risk review, the Head of Credit Risk compares transparent screening thresholds under three assumed error-cost ratios, examines bad-credit recall and good-credit referral burden, and decides whether to retain a manual baseline or commission modern validation.

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Corrected credit data and outcome audit | Original-to-English dictionary, kredit mapping, sample class counts, transformed-amount notice and sensitive-field/availability register. |
| D6 | Explainable risk-screening comparison | Constant baseline and regularised logistic candidate; train/validation/test manifest; bad-event precision/recall, balanced accuracy, false referrals and coefficient/explanation report. |
| D7 | Three cost-sensitive referral policies | Threshold comparison for FN:FP=1:1, 3:1 and 5:1; confusion matrices, review share, cost and policy recommendation for each. |
| D8 | Credit-risk review dashboard | Sample quality, model/cost comparison, review burden and supported subgroup diagnostics with uncertainty. |
| D11 | Model-risk recommendation and validation plan | Recommend retain baseline, revise prototype or seek modern pilot; identify modern representative data, fairness/legal review, calibration and operational controls required. |

## Required success contract

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Corrected credit data and outcome audit | kredit=0 maps to bad_event=1; totals show 300 bad/700 good before any exclusions; no sex reconstructed from famges and no current monetary exposure invented. |
| SC2 | D6 — Explainable risk-screening comparison | Holdout is untouched until threshold lock; all classes/counts visible; no sampled probability is presented as current population default risk. |
| SC3 | D7 — Three cost-sensitive referral policies | FN=2/FP=3 at 5:1 costs 13 assumed units; threshold selection uses validation; adverse scores route to human review with override, never automatic denial. |
| SC4 | D8 — Credit-risk review dashboard | Every subgroup below 30 is labelled insufficient evidence; reviewer finds a missed-bad case and an unnecessary-referral case and traces their policy outcomes. |
| SC5 | D11 — Model-risk recommendation and validation plan | No regulatory compliance/fairness certification; three next actions each have owner, required evidence and acceptance gate before any real lending use. |

[Detailed acceptance](ACCEPTANCE_CRITERIA.md) defines executed evidence; [deliverables](DELIVERABLES.md) defines exact artefacts and ownership. G1 records simulated sponsor approval, not invented real-client agreement.

## Core scope

All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

Required source: SouthGermanCredit.asc, codetable.txt, read_SouthGermanCredit.R. Model grain: One historical credit record identified by original row number; not a modern applicant population.

Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review Wrong target coding or interpreting oversampled historical outcomes as current default probabilities would invalidate underwriting conclusions. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: One historical credit record identified by original row number; not a modern applicant population. |
| Credit Risk Analyst | Own corrected outcome coding, cost-matrix scenarios and a policy card showing review capacity and missing modern validation evidence. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit. |
| BI / Decision Product Developer | Four views for the credit model risk and policy review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Credit Model Risk Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Baseline constant-majority prediction and transparent logistic model; compare validation-selected thresholds under false-negative:false-positive cost ratios 1:1, 3:1 and 5:1. Lock threshold before test. Keep all outcomes as simulated review/referral, not loan approvals.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Credit Risk, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Credit Risk Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Credit Risk reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Credit Model Risk Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).
