# MTL-XF-034 — Data acquisition and engineering

## Approved S1

[South German Credit](https://archive.ics.uci.edu/dataset/573); required files: **SouthGermanCredit.asc, codetable.txt, read_SouthGermanCredit.R**. Expected source population: 1,000 records, 700 good and 300 bad credits.

Exact official download:

https://archive.ics.uci.edu/static/public/573/south+german+credit+update.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

**Grain:** One historical credit record identified by original row number; not a modern applicant population.

**Required fields:** All original German-coded columns, with kredit target mapped using codetable.txt/read_SouthGermanCredit.R; preserve original→English mapping; verified kredit=0 bad, 1 good; model positive event=1−kredit..

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. The official ZIP has BZip2-compressed entries; use a compatible reader such as Python zipfile. Verified corrected code table: kredit=0 bad, 1 good; derive bad_event=1−kredit.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

Stratified 60/20/20 split seed 34 with duplicate feature groups together; fit encoder, imputation and scaling only on train. Target risk event=bad credit, explicitly verified from original code table. Exclude kredit and identity fields; compare sensitive-field exclusions without asserting fairness from sparse groups. Verified mapping: kredit=0 bad and kredit=1 good; derive bad_event=1−kredit.

## Interpretation and quality

Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
