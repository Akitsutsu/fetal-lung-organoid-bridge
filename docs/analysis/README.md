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
- `at1_at2_alignment_tiers_2026-04-26.md`
  - Three-tier AT1 / AT2 bridge interpretation: AT2-related distal alignment,
    AT1-onset / early commitment, and open full AT1 maturity.
- `quach_farrell_at1_onset_reinspection_2026-04-26.md`
  - Quach-Farrell Tier 2 clarification: strict GW15/GW18 distal variants,
    descriptive `AGER` / `PDPN` stage enrichment, and explicit non-closure of
    mature AT1.
- `gse237359_tier1_at2_bridge_2026-04-26.md`
  - GSE237359 Tier 1 clarification: fetal-primary AT2 bridge, D-0008
    system-boundary support for `AQP5`, and explicit E4 mesenchymal caveat.
- `e_mtab_11435_tier1_tier2_bridge_2026-04-26.md`
  - E-MTAB-11435 Tier 1-2 clarification: alveolar-fated fetal-primary
    self-renewing state, internal early-commitment contrast, and explicit
    non-use as a clean C1 anchor.
- `yap_taz_at1_inventory_2026-04-26.md`
  - YAP/TAZ inventory rethink: direct perturbation versus commitment-ordering
    versus fetal-compatibility layers for adding a mechanobiology interpretation
    to the current AT1 / AT2 bridge.
- `yap_taz_at1_directionality_2026-04-26.md`
  - Direct sample-wide YAP/TAZ-positive-arm read across `GSE221344`,
    `GSE221343`, and `GSE289846`, including the recurring split between
    AT1-directional gains and unresolved `AQP5` / mature-AT1 closure.
- `pdgfa_pdgfra_septation_gap_2026-04-26.md`
  - Mechanism-level septation gap read, now explicitly bounded at the level of
    the currently distributed scRNA objects: native fetal `PDGFA` ligand plus
    `PDGFRA` / `FGF10` / `WNT2` / elastic-fiber mesenchymal coupling versus
    current organoid-side non-capture of the receptor / ECM half in public
    bridge derivatives.
- `culture_profiling_object_triage_2026-04-26.md`
  - Dataset-level triage separating culture design, profiling design, and
    distributed object composition for the six septation-gap-relevant organoid
    datasets, including the `GSE221342` / `GSE221344` accession sanity check.
- `organoid_axis_e_adjudication_2026-04-26.md`
  - Organoid-side Axis E clarification: epithelial support versus niche
    support, `GSE237359` as E4 caveat, and no positive Axis E closure from the
    current `E-MTAB-11435` or `EV-0009` bridge objects.
- `gse280880_mesenchyme_author_label_context_2026-04-26.md`
  - GSE280880 mesenchyme-side clarification: author-label native context for
    E1/E2-rich fetal lung, explicit marker-level block, and relation to the
    open organoid-side Axis E gap.
- `axis_e_native_to_organoid_gap_2026-04-26.md`
  - Higher-order Axis E synthesis: native positive-support bar, independent
    OHRI stromal-rich context, Visium anti-correlation interpretation, and the
    current organoid-side non-closure of positive E1-E3 support.
- `he_visium_axis_e_neighborhood_2026-04-26.md`
  - Coordinate-level He Visium follow-up: immediate spot-neighborhood analysis
    for `E1` / `E2` / `E3` versus `Late_tip` / `AT1` / `AT2`, including the
    same-spot-to-neighborhood sign flip for `E1` and the more selective
    boundary-context behavior of `E3`.
