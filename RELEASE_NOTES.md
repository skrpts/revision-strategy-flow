# Release Notes

## v1.1.28
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.27
GH#745 — declare per-step `output: {name, type}` on every execution step (revision_plan/text, practice_sessions/text, study_plan/text, timetable/text, confidence_tracker/text, polished_plan/text, confidence_ratings/text). Lights up the #744 rich flow-map with named, typed outputs. Content-only; no bindings or logic changes.

## v1.1.26
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 10 inline shared-content files and declare 10 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.25
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.24
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.23
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.22
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.21
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
