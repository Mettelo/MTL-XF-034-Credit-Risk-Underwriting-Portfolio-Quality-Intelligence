# MTL-XF-034 — Credit Risk Underwriting Portfolio Quality Intelligence

**Track:** Cross-Functional · **Use case:** Commercial / private sector · **Team:** 6–8 · **Duration:** 8 weeks

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Business commission

**Client:** Confidential Consumer Lender. **Decision owner:** Head of Credit Risk. **Cadence:** credit model risk and policy review.

Credit risk leaders need a transparent way to compare risk screening policies and review burdens. An old, deliberately sampled credit dataset can support a learning exercise, but cannot establish modern population default rates, calibrated lending probabilities or a production approval policy.

**Decision:** Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot.

## End-to-end delivery

Deliver business requirements, governed source acquisition, engineering and data quality, seven defined metrics, baseline/alternative policy comparison, decision dashboard, assurance/UAT, executive recommendation and operational handover. A model alone is insufficient.

Baseline constant-majority prediction and transparent logistic model; compare validation-selected thresholds under false-negative:false-positive cost ratios 1:1, 3:1 and 5:1. Lock threshold before test. Keep all outcomes as simulated review/referral, not loan approvals.

## Core dataset and frozen cohort

**S1:** [South German Credit](https://archive.ics.uci.edu/dataset/573). **Input:** SouthGermanCredit.asc, codetable.txt, read_SouthGermanCredit.R. **Source population:** 1,000 records, 700 good and 300 bad credits.

All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

Exact official download:

https://archive.ics.uci.edu/static/public/573/south+german+credit+update.zip

Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

No raw data are uploaded by this update. Teams preserve original bytes outside Git in an approved durable snapshot, with checksums, source metadata and reviewer access. The source register records verification evidence and acquisition rules.

## Pack navigation

- [Project brief](project/PROJECT_BRIEF.md) — scope, roles and milestones.
- [Business context](project/BUSINESS_CONTEXT.md) — stakeholders and decisions.
- [Deliverables](project/DELIVERABLES.md) — D1–D12 and K1–K7.
- [Acceptance criteria](project/ACCEPTANCE_CRITERIA.md) — AC1–AC12 and DT1–DT10.
- [Governance](project/GOVERNANCE.md) — gates, assumptions and changes.
- [Data guidance](data/README.md) and [source register](data/SOURCE_REGISTER.md).
- [Submission pack](submission/README.md) — team repository and final evidence.

## Evaluation and policy boundary

Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit.

**Primary risk:** Wrong target coding or interpreting oversampled historical outcomes as current default probabilities would invalidate underwriting conclusions.

At G1 (week 2), approve requirements, source rights, actual schema and frozen bytes. At G2 (week 4), approve row accounting, all seven metrics and evaluation design. At G3 (week 6), review baseline/alternative and uncertainty. At G4 (week 8), require all twelve deliverables, ten executed domain tests, three UAT tasks, five reconciliations and a distinct-member clean rerun.

Assign named authors and review partners. Unsupported mandatory outputs remain blocked until an approved source/scope change resolves them. Record actual results in a separate Mettelo team repository; this master defines the work.
