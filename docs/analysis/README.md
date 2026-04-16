# Analysis Synthesis Layer

- date: 2026-04-16
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: this README
- source memos: local notes under
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/research_overview_and_data_summary_ja_v1.md`

## Purpose

`docs/analysis/` is a repository-visible synthesis layer for local analyses
that are important for paper drafting, review, and reproducibility but are not
registered evidence units, claim-status changes, or biological-contract edits.

This layer exists because the repository needs a durable, reviewable trace of
major local findings without turning `EVIDENCE_REGISTRY.tsv` into a dataset
census or turning claim memos into analysis notebooks.

## Authority Boundary

This directory is below the authoritative repository semantics:

- `BIOLOGICAL_CONTRACT.yaml`
- `REFERENCE_CONTRACT.yaml`
- `WORKFLOW_STATE_MACHINE.yaml`
- `EVIDENCE_REGISTRY.tsv`
- `docs/EVIDENCE_REGISTRY_RULES.yaml`
- `docs/claims/*`
- `decision_log.md`

Documents in this directory may summarize, interpret, and cross-reference local
findings. They do not promote evidence, close claims, alter workflow state, or
change contract semantics.

## What Belongs Here

- Analysis syntheses that connect multiple local notes.
- Dataset landscape maps and census summaries used for paper planning.
- Axis-reference findings that help interpret organoid-to-fetal comparisons.
- Method-validation summaries that justify quantitative analysis choices.
- Non-promotion rationale for local findings that are useful but not eligible
  for registered evidence use.
- Paper-supporting figures / table planning, when they summarize analysis
  rather than define claims.

## What Does Not Belong Here

- New evidence registry rows.
- Claim bottom-line edits.
- Contract or workflow rule changes.
- Raw prompt transcripts.
- Full raw dataset tables or generated count matrices.
- Scratch execution logs that are better kept in local notes.
- Local findings presented as claim-linked evidence without registry review.

## Relationship To Local Notes

Local notes under `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/` remain the
detailed execution and inspection layer. `docs/analysis/` summarizes stable
findings from those notes in English for repository review.

When a `docs/analysis/` document cites a local note, the local note remains the
source of detailed calculations. The synthesis document records why the result
matters and how it should or should not be used.

## Current Documents

- `public_data_landscape_2026-04-16.md`
  - Census and dataset-landscape synthesis.
- `axis_reference_findings_2026-04-16.md`
  - Axis C1 / C2 / A / E reference findings and status.
- `nonpromotion_rationale_2026-04-16.md`
  - Why major local findings remain non-evidence.
- `method_validation_findings_2026-04-16.md`
  - R-SPONDIN perturbation, strict C1 gating, and cross-modal spatial method
    validation.

