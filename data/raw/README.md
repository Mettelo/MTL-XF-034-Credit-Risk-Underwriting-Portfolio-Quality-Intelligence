# MTL-XF-034 — Raw-data preservation

**No raw data are uploaded by this update.** This directory documents the strategy; it does not assert that input payloads are in Git.

Acquire SouthGermanCredit.asc, codetable.txt, read_SouthGermanCredit.R from [S1 exact URL and checked-byte reference](../SOURCE_REGISTER.md). Retain original archive/members/codebooks outside Git in an immutable S1-v1 snapshot; record retrieval UTC, URL, filename, bytes and SHA-256. Keep a recoverable copy with retention owner and reviewer access.

**Frozen scope:** All 1,000 original SouthGermanCredit.asc records with the corrected code table and reader; preserve source sampling and coding. Historical 1973–1975 data; bad credits are oversampled.

The official ZIP has BZip2-compressed entries; use a compatible reader such as Python zipfile. Verified corrected code table: kredit=0 bad, 1 good; derive bad_event=1−kredit.

Never overwrite, edit, re-encode or deduplicate originals. Extract into a separate working area; transformations, exclusions and parsed labels belong in code and curated outputs with source-row lineage. Check original and extracted byte hashes before analysis. A mismatch or missing approved snapshot blocks processing until resolved.

Team repositories should ignore local raw payloads while tracking this guidance and metadata. Do not remove any previously supplied raw data without explicit approval. Store access instructions without credentials and document restoration from retained bytes if upstream changes.
