# MTL-XF-034 — Source register

## S1 — South German Credit

| Field | Approved definition |
| --- | --- |
| Provider | UCI Machine Learning Repository; preserve original creator attribution |
| Documentation | https://archive.ics.uci.edu/dataset/573 |
| Exact download | https://archive.ics.uci.edu/static/public/573/south+german+credit+update.zip |
| Required inputs | SouthGermanCredit.asc, codetable.txt, read_SouthGermanCredit.R |
| Source population | 1,000 records, 700 good and 300 bad credits |
| Decision owner | Head of Credit Risk |
| Status | Official archive/feed retrieved and inspected; team freeze/sign-off and analysis remain to be completed. No raw data uploaded. |

Persistent citation: https://doi.org/10.24432/C5QG88

## Checked byte reference

Official archive retrieved and inspected on **2026-10-16**. Archive size **13130 bytes**; SHA-256 **0b40d40eb7321693d559e247a556f88a6cc8df8489c3cb2ae084db7592584551**.

| Archive member | Bytes | SHA-256 |
| --- | --- | --- |
| codetable.txt | 3154 | 0040e7a173a06d1167447b2bbc4315ee1380fa3c25db321b9fd7d97ada0721bf |
| read_SouthGermanCredit.R | 7550 | 92340012c6387dcc0fea9dcf47e2cc9659cda93c21bd688f3f694f0f0229ed68 |
| SouthGermanCredit.asc | 47940 | 5f363343f356ca38a0236baab849e472846399b2176ccc5bd686483dd8a7562f |

Member names and byte hashes were inspected; CSV record counts were checked where present. Actual cohort transformations and business analysis remain team delivery work.

The official ZIP has BZip2-compressed entries; use a compatible reader such as Python zipfile. Verified corrected code table: kredit=0 bad, 1 good; derive bad_event=1−kredit.

## Cohort and field support

All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

**Grain:** One historical credit record identified by original row number; not a modern applicant population.

**Required mapping:** All original German-coded columns, with kredit target mapped using codetable.txt/read_SouthGermanCredit.R; preserve original→English mapping; verified kredit=0 bad, 1 good; model positive event=1−kredit..

**Interpretation limits:** Do not use Statlog coding. Sex cannot be reliably recovered from famges. Monetary amounts are transformed historical DM and are not actual current exposure. Sample prevalence is not a population default estimate. Audit age and foreign_worker implications; no automated approval/denial or compliance certification.

## Rights and attribution

Publisher page declares [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite original creators, UCI and [dataset DOI](https://doi.org/10.24432/C5QG88); preserve notices and state transformations.

## Team acquisition record required at G1

Record source/freeze ID, requested/resolved URL, retrieval UTC, release/feed timestamp, archive/member filename, actual bytes/checksum, encoding/delimiter/worksheet/schema, row count, date bounds, included/excluded scope, licence/citation evidence, storage/access and retention owner, verification checks, analyst and reviewer approval/date. Unknown or unexecuted fields remain explicitly pending.

## Raw-data durability

Preserve original archive, required members and documentation in a read-only S1-v1 snapshot in approved durable storage outside Git with a second recoverable copy. Record reviewer access and restore instructions without credentials. Provider/DOI URLs locate the source; retained checksum-addressed bytes define reproducibility. Stable URLs do not guarantee immutable contents or perpetual availability.

No raw data are committed by this master update. Restore verified retained bytes if the provider becomes unavailable. If no approved copy exists, block G1; do not substitute an unofficial mirror, another variant or guessed schema. A new official version requires rights/schema/scope review, new freeze ID and rerun of affected tests.

## Refresh and supplementary inputs

Do not stack overlapping UCI samples/variants. Required publisher codebooks remain source references. Business costs, capacities and pilot outcomes absent from S1 are synthetic assumptions, not measured facts.

Every added reference/supplement needs ID, official source/version/URL, rights, grain/coverage, purpose, join key/cardinality, effect on K/D/AC/DT and reviewer approval. Optional extensions cannot replace core requirements silently.
