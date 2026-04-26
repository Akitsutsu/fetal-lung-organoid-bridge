# MCMR-FL Boundary and Future Morphology Path

- date: 2026-04-26
- status: non-authoritative analysis synthesis (per D-0011)
- type: pointer + boundary, not evidence promotion
- claim impact: none (P-0001 / P-0002 unchanged)

## Purpose

Pointer to the satellite repository hosting the
Morphology-Constrained Molecular Reconstruction of Fetal Lung
(MCMR-FL) exploratory methodology track, and explicit boundary
statement that this track does not modify any claim status,
evidence registry row, or contract in this repository.

## Satellite repository

[`Akitsutsu/fetal-lung-mcmr`](https://github.com/Akitsutsu/fetal-lung-mcmr)
(private, exploratory).

The satellite hosts 6 sealed pilots (5 manifest-anchored + 1
light pre-registration) developed on n=2 public Quach-Farrell
fetal lung Xenium samples (GW15 GSM8217893, GW18 GSM8217894):

| pilot | manifest body sha256 |
|---|---|
| Pilot 1 (linear LR + 9 morph+topo features) | `a9edb40e0285008d3ede1c694324633f97a42a2b713a0bf85ed60ad3d0a75af8` |
| Pilot 1.5 (HGB + 19 morph+topo+polygon) | `1fb3d90e02193bd3ba09df29df1a841e68648c065d5714e6f04cf6184363dce3` |
| Pilot 1.5 polygon-only diagnostic | `ddce93d8bb46830641c9822b88f4d8543e40e75e0b67cd13ff1d945993b2fe28` |
| Pilot 1.5 DAPI texture probe | (light pre-registration, no manifest) |
| Pilot 2 regression reframe | `fe81972203b45e4b51e5a83f592e95e536877cb9112da510643c315724f0f0b4` |
| Pilot 2 all-bin mask-metric sensitivity | `3c9b7dee63ae110702353706ff21e135b167e7337c5fcede0ed3e7db2f1e94a6` |

## Boundary

This pointer is not:

- a claim memo edit
- an evidence registry row
- a contract YAML edit
- a `decision_log.md` entry
- a hold / promote decision for any P-0001 / P-0002 support unit

The MCMR-FL satellite repository does not have an evidence
registry, does not host claim memos, and does not modify any
contract in this repository. Its README and `docs/boundary.md`
restate this.

If any future analysis in the satellite turns out to be claim-
relevant (e.g. additional fetal-organoid bridge evidence under
P-0002 morphology gap), the path is: sealed satellite pilot →
human review → human authoring of bridge-repo PR (claim memo
edit, evidence row, or `docs/analysis/` synthesis). Never
automated promotion.

## Headline reading from MCMR-FL pilots

For context only. The actual reads are in the satellite's
`docs/current_status.md`.

- **Classification framing capped** at +0.014 to +0.018 absolute
  Δ AUROC vs marker-only baseline across all feature classes
  attempted (linear LR, HGB, polygon, DAPI texture). Anchor
  markers are the structural binding constraint under the v1
  held-out marker design; feature engineering alone cannot clear
  the +0.03 PASS / FAIL threshold.
- **Regression reframe** revealed previously-invisible
  per-marker structural predictability: Pearson r ≥ 0.30 in
  8/12 (GW15) and 9/12 (GW18) markers from structure alone.
  Largest structure_increment (combined − anchor_only) is
  **GW15 PDPN +0.069**, with PDPN, AGER, and SOX2 as the highest-
  leverage AT1-related and proximal-axis markers in both stages.
  No marker reaches the descriptive "strong" cutoff (+0.10).
- The cheap Pilot 3 path (all-bin mask-metric re-extraction)
  was tested and ruled out (22/24 markers no change after
  removing the 47-48% NaN budget; bin layer was at its
  ceiling, not at a coverage gap).

## Relation to P-0002 morphology gap

P-0002 (`docs/claims/P-0002_current_status_v1.md`) currently
admits a partial multimodal alignment with explicit caveats on
morphology fidelity, mesenchymal niche resolution, and AT1
maturity (via `EV-0011` / `EV-0014` morphology QC at
artifact-exclusion / tissue-embeddedness scope only). The MCMR-FL
satellite quantifies the morphology channel under the public-data
n=2 boundary:

- Cell-local segmentation geometry + single-z DAPI texture +
  bin-level mask architecture have been **exhausted as a
  classification-vs-marker booster** (cannot move +0.018 cap).
- The same features support **per-marker regression of
  log1p(expression)** with biologically interpretable structure
  for AT1-related markers.
- Stronger structural channels (multi-z DAPI, paired same-section
  H&E, serial sections) remain future work, conditional on
  dataset acquisition (Hsu-Spence Zenodo when unrestricted, HDCA,
  GSE280880, or other paired-imaging fetal lung sources).

This does not change P-0002's bottom line. It quantifies the
morphology gap rather than closing or weakening it.

## Future Pilot 3 axes (deferred)

When MCMR-FL resumes, the remaining axes per priority order:

1. Multi-z DAPI texture + GLCM directional panel + larger
   window — feature-engineering continuation
2. Held-out marker strengthening — structural fix to anchor
   saturation, requires new amendment because it changes v1 §4
3. Tissue-context distance maps — derived from
   `morphology_axis_v1` niche labels with leakage care
4. Phase 4 cross-stage in regression framing — descriptive
5. Same-section H&E or serial-section dataset triage —
   dataset-bottlenecked

Detailed rumination: satellite `docs/pilot3_design_options.md`.

## Why this pointer is in `docs/analysis/`

D-0011 established `docs/analysis/` as the repository-visible,
non-authoritative analysis synthesis layer. This pointer is the
correct location for a methodology-track summary that:

- references external (satellite) work without copying it here
- is paper-supporting context, not claim-bearing material
- can be reviewed by collaborators in the bridge repo without
  cluttering the authoritative semantic stack

This document follows the existing `docs/analysis/` documents
in style: dated filename, brief summary, explicit non-claim
status, no contract or registry edits.
