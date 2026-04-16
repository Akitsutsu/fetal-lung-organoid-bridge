# Method Validation Findings, 2026-04-16

- date: 2026-04-16
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `e_mtab_10662_axis_fit_v1.md`
  - `he_organoid_subset_axis_fit_v1.md`
  - `qf_he_stage_paired_v1.md`
  - `he_visium_spot_metrics_v1.md`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/research_overview_and_data_summary_ja_v1.md`

## Summary

Three local analyses validate method choices used in the paper skeleton:

1. R-SPONDIN pathway inhibition reduces the C1 budtip signature in the expected
   direction.
2. Strict C1 gating requires SOX9+ NKX2-1+ lung identity to avoid non-lung
   endoderm false positives.
3. Xenium per-cell and Visium spot-level spatial metrics should be compared
   through deconvolution-aware or geometry-aware framing, not raw marker
   fractions alone.

These findings support methods and interpretation. They do not create new
evidence rows or change claim bottom lines.

## R-SPONDIN Perturbation Validates C1 Directionality

Source: `E-MTAB-10662`, fetal lung explant ALI with LGR5 ECD adenovirus.

Local comparison:

| Condition | Interpretation |
|---|---|
| Control adenovirus | Perturbation control |
| LGR5 ECD adenovirus | R-SPONDIN pathway inhibition |

Observed direction:

- `frac_budtip_fit`: about 36% reduction.
- `sox9_nkx21+`: about 37% reduction.
- `c2_commitment`: about 36% reduction.

Interpretation:

- The C1 score responds to a known budtip-disrupting perturbation in the
  expected direction.
- This supports the use of the C1 score as a budtip-identity measurement
  rather than generic distal or proliferation signal.
- The result is method validation and biological bridge context, not
  claim-linked P-0002 evidence by itself.

## Strict C1 Gating Avoids Non-Lung Endoderm False Positives

Source: He atlas "Organoid" subset in `E-MTAB-11278`.

Initial expectation:

- The subset might contain a Rawlins lung organoid comparison.

Inspection result:

- The object contains native fetal cells plus a foregut endoderm transcription
  factor induction screen.
- Transgene labels include deltaNp63a, RFX6, PAX9, TFAP2A, NEUROG3, NEUROD1,
  ASCL1, and Ctrl.
- Across transgene conditions, `sox9_nkx21_positive = 0.000`.

Method implication:

- TESC / ID2 / CA2-like signal without SOX9+ NKX2-1+ lung identity can inflate
  loose budtip scores in non-lung endoderm contexts.
- Paper methods should require SOX9+ NKX2-1+ grounding for strict C1 scoring.
- This is an operational scoring rule for analysis methods, not a sidecar
  semantic rule.

## Xenium And Visium Need Geometry-Aware Comparison

Sources:

- Quach-Farrell Xenium: per-cell 339-gene spatial panel.
- He Visium: full-transcriptome spot-level spatial data with cell2location
  weights.

Local observation:

- Raw marker fraction directions can diverge when a Xenium per-cell classifier
  is compared directly to a Visium spot-level marker rule.
- In He Visium, whole-tissue spot fractions are affected by region sampling and
  stromal / proximal airway mixture.
- Deconvolution-aware cell2location trends are more directionally concordant
  with the expected fetal distal / alveolar progression.

Interpretation:

- Raw spot-level marker fractions should not be used as direct replication of
  Xenium per-cell fractions.
- Full-transcriptome Visium can gap-fill missing markers such as HOPX, AQP5,
  ID2, VIM, COL1A1, and COL3A1.
- Visium does not close the independent single-cell fetal spatial replication
  gap under the current D-2-deferred frame.

## Paper Methods Consequence

The paper methods should explicitly distinguish:

- marker panel availability;
- per-cell versus spot-level spatial geometry;
- raw marker fractions versus deconvolution weights;
- strict C1 gating versus loose marker co-detection; and
- method validation versus evidence promotion.

