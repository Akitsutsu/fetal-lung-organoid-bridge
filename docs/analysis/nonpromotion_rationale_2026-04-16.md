# Non-Promotion Rationale, 2026-04-16

- date: 2026-04-16
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `user_directional_decisions_2026-04-16.md`
  - `research_overview_and_data_summary_ja_v1.md`
  - `he_organoid_subset_axis_fit_v1.md`
  - `gse237359_inspect_v1.md`
  - `e_mtab_10662_axis_fit_v1.md`
  - `qf_he_stage_paired_v1.md`
  - `gse280880_initial_inspection_v1.md`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/research_overview_and_data_summary_ja_v1.md`

## Summary

Several 2026-04-16 local findings are biologically important but remain outside
`EVIDENCE_REGISTRY.tsv`. This is intentional. The registry is an evidence-unit
index, not a complete analysis catalog or dataset census.

The local findings below can support paper framing, methods validation,
boundary interpretation, and future prioritization. They should not be treated
as claim-linked evidence without separate registry review.

## Current Local Findings And Why They Are Not Promoted

| Source | Local value | Current non-promotion rationale |
|---|---|---|
| `E-MTAB-11278` He scRNA atlas | Native fetal reference for C1, C2, Axis A, and Axis E | Reference / bridge analysis, not a registered P-0002 evidence unit; source-bank independence is informative but does not by itself create claim-linked support |
| `E-MTAB-11265` He Visium | Full-transcriptome spatial gap-fill for HOPX, AQP5, ID2, and stromal markers | Visium spot-level geometry differs from Xenium per-cell evidence; D-2 independent-replication question remains deferred |
| `GSE237359` | HDBR fetal AT2 organoid with AQP5 signal | Useful C2 / AQP5 bridge, but not registered claim support; small fibroblast-labeled component is E4 caveat, not positive E1 niche |
| `E-MTAB-10662` | R-SPONDIN perturbation validates C1 biology and scoring direction | Method / biology validation, not an organoid-to-fetal claim evidence row; source / workflow overlap caveats remain |
| `GSE280880` | Independent OHRI fetal snRNA author-label trend | Marker scoring blocked by missing feature symbols / gene IDs in the public matrix |
| `E-MTAB-8221` Day_0 | Primary fetal BTO C1 local anchor | Bridge-layer local reference with UW LDB / Spence workflow overlap caveat |
| `E-MTAB-11435` | HDBR fetal late-tip organoid C2 context | Condition-pooled exposure and local bridge status limit evidence use |
| Frum/Spence fetal snRNA | CFTR / FMO5 fetal AT2 heterogeneity and AT1 AQP5 emergence | UW LDB / Spence source-overlap risk; local ontology and cross-bank comparison only |
| `GSE310610` | Candidate fetal Visium directional signal | Sample-file mapping unresolved; barcode-level author labels not available |
| `GSE297945` | Candidate fetal-window Xenium records | Mixed disease / viability context and specimen mapping unresolved |
| He "Organoid" subset | Negative control for non-lung endoderm false positives | Not a lung organoid dataset; should not be used as Rawlins lung organoid comparison |

## General Rules Used Here

1. Local analysis value does not imply evidence registration.
2. Bridge-layer interpretation should remain in analysis documents unless
   evidence-unit criteria, source unit boundaries, and claim relevance are
   explicitly reviewed.
3. Source-bank independence, by itself, does not promote a local analysis to
   registered evidence.
4. Same-study or same-workflow support can help biological interpretation but
   should not be called independent corroboration.
5. Whole-tissue Visium gap filling should not be equated with Xenium-equivalent
   independent single-cell spatial replication.
6. Method-validation findings should support methods sections unless the
   evidence registry explicitly creates a claim-linked role.

## Relationship To Future Registry Work

This document does not decide whether any local finding should later become an
evidence row. It records why the findings remain outside the registry now.

Future bridge-layer EV registration would require a separate decision about:

- whether bridge-layer evidence rows are allowed;
- how source units are cut;
- how non-claim-linked EV rows differ from census rows;
- whether local recomputation values belong in the registry or in
  `docs/analysis/`; and
- how reviewers should distinguish registered support from contextual analysis.

