# MTL-XF-034 — Credit Risk Underwriting Portfolio Quality Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 6–8 · **Duration:** 8 weeks

## The business problem

The lender's risk team must compare a conservative referral policy with a policy that sends fewer low-risk cases for manual review. Missed bad-credit cases and unnecessary referrals have different consequences, so accuracy alone cannot decide the policy. The historical sample is intentionally enriched with bad credits and uses corrected coding; treating it as today's applicant population would produce an unjustified lending policy.

**Simulated organisation:** Confidential Consumer Lender. **Accountable decision owner:** Head of Credit Risk.

## Practical use case

At model-risk review, the Head of Credit Risk compares transparent screening thresholds under three assumed error-cost ratios, examines bad-credit recall and good-credit referral burden, and decides whether to retain a manual baseline or commission modern validation.

**Decision the project must enable:** Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot.

**Current approach:** Discuss one accuracy figure without a corrected-label audit or explicit trade-off between missed risk and review burden.

**Required future approach:** Compare a human-review prototype using verified labels, cost scenarios, subgroup evidence and explicit modern-data gaps.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Corrected credit data and outcome audit | Original-to-English dictionary, kredit mapping, sample class counts, transformed-amount notice and sensitive-field/availability register. |
| D6 | Explainable risk-screening comparison | Constant baseline and regularised logistic candidate; train/validation/test manifest; bad-event precision/recall, balanced accuracy, false referrals and coefficient/explanation report. |
| D7 | Three cost-sensitive referral policies | Threshold comparison for FN:FP=1:1, 3:1 and 5:1; confusion matrices, review share, cost and policy recommendation for each. |
| D8 | Credit-risk review dashboard | Sample quality, model/cost comparison, review burden and supported subgroup diagnostics with uncertainty. |
| D11 | Model-risk recommendation and validation plan | Recommend retain baseline, revise prototype or seek modern pilot; identify modern representative data, fairness/legal review, calibration and operational controls required. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Corrected credit data and outcome audit | kredit=0 maps to bad_event=1; totals show 300 bad/700 good before any exclusions; no sex reconstructed from famges and no current monetary exposure invented. |
| SC2 | D6 — Explainable risk-screening comparison | Holdout is untouched until threshold lock; all classes/counts visible; no sampled probability is presented as current population default risk. |
| SC3 | D7 — Three cost-sensitive referral policies | FN=2/FP=3 at 5:1 costs 13 assumed units; threshold selection uses validation; adverse scores route to human review with override, never automatic denial. |
| SC4 | D8 — Credit-risk review dashboard | Every subgroup below 30 is labelled insufficient evidence; reviewer finds a missed-bad case and an unnecessary-referral case and traces their policy outcomes. |
| SC5 | D11 — Model-risk recommendation and validation plan | No regulatory compliance/fairness certification; three next actions each have owner, required evidence and acceptance gate before any real lending use. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [South German Credit](https://archive.ics.uci.edu/dataset/573). **Required input:** SouthGermanCredit.asc, codetable.txt, read_SouthGermanCredit.R. **Expected source population:** 1,000 records, 700 good and 300 bad credits.

All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

**Download:** https://archive.ics.uci.edu/static/public/573/south+german+credit+update.zip

Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit.

Baseline constant-majority prediction and transparent logistic model; compare validation-selected thresholds under false-negative:false-positive cost ratios 1:1, 3:1 and 5:1. Lock threshold before test. Keep all outcomes as simulated review/referral, not loan approvals.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- Credit Risk Analyst: Own corrected outcome coding, cost-matrix scenarios and a policy card showing review capacity and missing modern validation evidence.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Credit Model Risk Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Credit Risk, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Credit Risk Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Credit Risk reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Credit Model Risk Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
