# MTL-XF-034 — Governance

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Accountability and gates

Head of Credit Risk owns business scope, assumptions and action approval. Governance owns source/rights/freeze; Engineer owns transformations; Credit Risk Analyst owns interpretation; Credit Model Risk Analyst independently reviews. The simulated Mettelo panel owns programme acceptance. Record actual team members separately from simulated stakeholder roles.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Credit Risk, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Credit Risk Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Credit Risk reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Credit Model Risk Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Domain controls

Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

**Primary risk:** Wrong target coding or interpreting oversampled historical outcomes as current default probabilities would invalidate underwriting conclusions.

Baseline constant-majority prediction and transparent logistic model; compare validation-selected thresholds under false-negative:false-positive cost ratios 1:1, 3:1 and 5:1. Lock threshold before test. Keep all outcomes as simulated review/referral, not loan approvals.

All capacity, threshold, financial and review/remediation targets are project assumptions unless explicitly attributed. Human deferrals/overrides record reason, evidence, owner and next review. No production action is authorised by this pack.

## Source and evaluation control

All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

Follow [S1 register](../data/SOURCE_REGISTER.md); preserve original bytes outside Git, immutable snapshot, manifest and reviewer access. Checksum mismatch stops processing until investigated. Never silently replace a variant/feed. No raw data uploaded by this update.

Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit.

Lock target mapping, predictors, timing and policy configuration before test evaluation. Descriptive projects retain resample/sensitivity evidence. Record unsupported metrics and negative findings.

## Change and exception control

Record change ID, requester/date/reason, original/revised source/cohort/requirement, rights/field evidence, affected K/D/AC/DT, time/risk impact, owner, reviewer and decision. New inputs get new freeze IDs and affected checks rerun. Missing mandatory support blocks dependent work.

Each operational exception needs case, rationale, evidence, accountable owner, approval, compensating/manual control, expiry and next review; expired exceptions return to review.

Use only approved public data and fictional operational assumptions. Avoid unnecessary customer identifiers and unsupported protected-characteristic inference.

## Publication and release

Keep attribution, snapshot and limitations in every portfolio/dashboard/slide export. No secrets or private correspondence. Release after all AC/DT/UAT and rerun evidence passes with zero critical/high defects. Record final commit/tag and rollback to approved snapshot/configuration.

## Business acceptance and approval record

The specific use case is: At model-risk review, the Head of Credit Risk compares transparent screening thresholds under three assumed error-cost ratios, examines bad-credit recall and good-credit referral burden, and decides whether to retain a manual baseline or commission modern validation.

SC1–SC5 in [acceptance](ACCEPTANCE_CRITERIA.md) govern the five concrete business outputs. G1 records criterion, version, actual team approver, simulated sponsor role, date and assumptions. G3 records measured baseline/alternative, decision and trade-off. G4 records executed pass evidence for each SC; a document's existence is insufficient. Never describe simulated sign-off or unmeasured benefits as real-client agreement or adoption.
