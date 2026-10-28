# Release Notes

## v1.1.31
GH#1045/GH#1100 (phantom repair, ruling (B) consumer half) — wire the two stages this workflow documents and never ran. `post-exam-reflector` shipped declared and uninvoked, and it read `{{steps.Practice Question Generator.output}}` — a step no execution entry ran, so the reference could never resolve. The package was not wrong about what it wanted: it already PINNED `practice-question-generator` and simply never invoked it.

Re-pinned `practice-question-generator` 1.0.2 → 1.0.3, the version that declares a `source` context_param (checksum resolved from the live catalogue via `gen-dep-checksums.mjs`, not transcribed). Added `practice-question-design` and `post-exam-reflection` backing skills — documented Stage 4 names the `retrieval-practice-design` skill that Stage 3 already occupies and Stage 5 names `self-assessment` which Stage 1 occupies, and two entries on one skill slug share a title, so neither attribution can be honoured literally. The Stage 4 skill carries the title "Practice Question Generator", which is the step name the author's own dangling reference asked for, so the binding reads as it was written.

Stage 4 binds `source` ← Retrieval Practice Design: that step produces the active-recall session content, which is the material the questions test, and it is Stage 4's documented predecessor. Stage 5 binds `revision_plan` ← Revision Planning and `practice_questions` ← Practice Question Generator, replacing both of the orphan's positional references with declared slots.

Why this needed the shared prompt migrated first: before 1.0.3, `practice-question-generator` itself read `{{steps.Flashcard Creator.output}}`, so wiring it would have created a SECOND unresolvable reference — this package pins `flashcard-creator` but has no flashcard stage in any documented stage or output. Migrating the shared prompt removed that reference entirely, so the chain resolves without inventing a stage. Skills 3→5, total 10→12.

## v1.1.30
GH#1100 consumer wave (batch 2) — declare the data flow this workflow was resolving positionally.

Each stage below now receives its input through a declared `bindings:` entry instead of `default_from_previous`, which K-073 revoked. **The value is unchanged**: every binding names the step that immediately precedes it, which is exactly what the positional default resolved to. What changes is that the dependency is stated rather than inferred from position, so a reorder can no longer silently feed a stage the wrong artefact.

Bindings added:
  `plan-studies` ← `from_step: "Retrieval Practice Design"` (step 3)
  `polish-language` ← `from_step: "Topic Confidence Tracker Template"` (step 6)

Dependency pins moved to the published versions that declare these slots:
  `flashcard-creator` 1.0.3 → 1.0.4
  `learning-science-reference` 1.0.1 → 1.0.2
  `plan-studies` 1.0.3 → 1.0.4
  `polish-language` 1.0.1 → 1.0.7
  `practice-question-generator` 1.0.1 → 1.0.2
  `revision-timetable-template` 1.0.1 → 1.0.2

## v1.1.29
GH#1044 — document the inputs this workflow's prompts REQUIRE but its Inputs table never listed. A user supplying exactly what the table asked for was running with required parameters unsatisfied — a silent wrong run, not a documentation nicety. Renamed 1 row(s) to the name the prompt actually consumes; documented 2 input(s): syllabus_topics, topic. Every row is generated from the requiring prompt's own declared description, example and required flag — none invented. No behaviour change; documentation only.

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
