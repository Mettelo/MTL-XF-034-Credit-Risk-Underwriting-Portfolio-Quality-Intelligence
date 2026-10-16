# MTL-XF-034 — Business context and practical use case

## Organisation and accountable decision

Confidential Consumer Lender is the simulated sponsor. The Head of Credit Risk owns the credit model risk and policy review and must decide: **Recommend a human-reviewed risk-screening prototype and identify evidence required before any modern lending pilot.**

## The operational problem

The lender's risk team must compare a conservative referral policy with a policy that sends fewer low-risk cases for manual review. Missed bad-credit cases and unnecessary referrals have different consequences, so accuracy alone cannot decide the policy. The historical sample is intentionally enriched with bad credits and uses corrected coding; treating it as today's applicant population would produce an unjustified lending policy.

## How the finished product will be used

At model-risk review, the Head of Credit Risk compares transparent screening thresholds under three assumed error-cost ratios, examines bad-credit recall and good-credit referral burden, and decides whether to retain a manual baseline or commission modern validation.

**Current approach:** Discuss one accuracy figure without a corrected-label audit or explicit trade-off between missed risk and review burden.

**Required future approach:** Compare a human-review prototype using verified labels, cost scenarios, subgroup evidence and explicit modern-data gaps.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| Head of Credit Risk | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| Credit Risk Analyst | Own corrected outcome coding, cost-matrix scenarios and a policy card showing review capacity and missing modern validation evidence. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Credit Model Risk Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Corrected credit data and outcome audit** to support the stated decision, with this evidence: Original-to-English dictionary, kredit mapping, sample class counts, transformed-amount notice and sensitive-field/availability register.
2. Can the sponsor use **Explainable risk-screening comparison** to support the stated decision, with this evidence: Constant baseline and regularised logistic candidate; train/validation/test manifest; bad-event precision/recall, balanced accuracy, false referrals and coefficient/explanation report.
3. Can the sponsor use **Three cost-sensitive referral policies** to support the stated decision, with this evidence: Threshold comparison for FN:FP=1:1, 3:1 and 5:1; confusion matrices, review share, cost and policy recommendation for each.
4. Can the sponsor use **Credit-risk review dashboard** to support the stated decision, with this evidence: Sample quality, model/cost comparison, review burden and supported subgroup diagnostics with uncertainty.
5. Can the sponsor use **Model-risk recommendation and validation plan** to support the stated decision, with this evidence: Recommend retain baseline, revise prototype or seek modern pilot; identify modern representative data, fairness/legal review, calibration and operational controls required.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Corrected credit data and outcome audit | Original-to-English dictionary, kredit mapping, sample class counts, transformed-amount notice and sensitive-field/availability register. |
| D6 | Explainable risk-screening comparison | Constant baseline and regularised logistic candidate; train/validation/test manifest; bad-event precision/recall, balanced accuracy, false referrals and coefficient/explanation report. |
| D7 | Three cost-sensitive referral policies | Threshold comparison for FN:FP=1:1, 3:1 and 5:1; confusion matrices, review share, cost and policy recommendation for each. |
| D8 | Credit-risk review dashboard | Sample quality, model/cost comparison, review burden and supported subgroup diagnostics with uncertainty. |
| D11 | Model-risk recommendation and validation plan | Recommend retain baseline, revise prototype or seek modern pilot; identify modern representative data, fairness/legal review, calibration and operational controls required. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Corrected credit data and outcome audit | kredit=0 maps to bad_event=1; totals show 300 bad/700 good before any exclusions; no sex reconstructed from famges and no current monetary exposure invented. |
| SC2 | D6 — Explainable risk-screening comparison | Holdout is untouched until threshold lock; all classes/counts visible; no sampled probability is presented as current population default risk. |
| SC3 | D7 — Three cost-sensitive referral policies | FN=2/FP=3 at 5:1 costs 13 assumed units; threshold selection uses validation; adverse scores route to human review with override, never automatic denial. |
| SC4 | D8 — Credit-risk review dashboard | Every subgroup below 30 is labelled insufficient evidence; reviewer finds a missed-bad case and an unnecessary-referral case and traces their policy outcomes. |
| SC5 | D11 — Model-risk recommendation and validation plan | No regulatory compliance/fairness certification; three next actions each have owner, required evidence and acceptance gate before any real lending use. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

**Failure to prevent:** Wrong target coding or interpreting oversampled historical outcomes as current default probabilities would invalidate underwriting conclusions.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
