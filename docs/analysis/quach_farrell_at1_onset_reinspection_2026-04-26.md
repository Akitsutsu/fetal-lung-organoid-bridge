# Quach-Farrell AT1-Onset Reinspection, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `docs/claims/P-0002_current_status_v1.md`
  - `gsm8217893_class_sensitivity_check_v1.md`
  - `gsm8217893_cell_level_niche_assignment_v1.md`
  - `xenium_targeted_neighborhood_reviewer1_summary_v1.md`
  - `mcmr_pilot1_pre_registration_qc_v1.md`
- local feature inputs used descriptively:
  - `gsm8217893_per_cell_features_v1.tsv.gz`
  - `gsm8217894_per_cell_features_v1.tsv.gz`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

Quach-Farrell Xenium remains a **Tier 2** anchor for AT1-onset / early
alveolar commitment, not a Tier 3 mature-AT1 closure layer.

The bridge-side reinspection supports four points:

1. The registered GW15 broad `SOX2lowCFTR+` class is too mixed to carry a
   durable AT1-facing interpretation on its own.
2. The registered stricter GW15 variants (`SFTPC`-positive and/or
   proximal-excluded) rescue distal epithelial specificity and remain usable as
   tissue-context anchors.
3. A descriptive re-read of the same Xenium sections shows that
   `AGER` / `PDPN` positivity within strict distal epithelial compartments is
   reproducibly higher at GW18 than at GW15.
4. The same re-read still shows strong developmental continuity with
   `SOX9`-positive distal cells, especially at GW15, so the result should be
   framed as **AT1-onset within a distal developmental field**, not as mature
   AT1 equivalence.

## Registered-Class Side: What The Existing Bridge Already Establishes

The registered support rows already make the main specificity point.

- At GW15, the broad base `SOX2lowCFTR+` class is distal-associated but also
  proximal-associated:
  - Pearson versus distal epithelial bins: `0.811`
  - Pearson versus proximal-airway bins: `0.623`
- The durable GW15 interpretation therefore depends on stricter variants:
  - `base_plus_sftpc`: Pearson distal `0.723`, proximal `0.090`
  - `base_exclude_proximal_plus_sftpc`: Pearson distal `0.636`, proximal
    `-0.039`
- The stricter GW15 variants remain developmental rather than mature:
  - `base_plus_sftpc` budtip-priority fraction within variant: `0.364`
  - `base_exclude_proximal_plus_sftpc` budtip-priority fraction within
    variant: `0.373`
- At GW18, the same stricter variants remain fully distal-positive and less
  budtip-weighted:
  - `base_plus_sftpc` budtip-priority fraction within variant: `0.157`
  - `base_exclude_proximal_plus_sftpc` budtip-priority fraction within
    variant: `0.154`

This is the key bridge-side specificity result: the fetal tissue-context anchor
is real, but at GW15 it must be read through strict distal variants and an
explicit distal/budtip continuity caveat.

## Descriptive AT1-Onset Read Within Strict Distal Compartments

To ask a narrower biological question, the same sections were re-read
descriptively using the per-cell epithelial feature tables generated for Pilot
1 QC. This is not a registered pilot result and is not used as a claim-closing
analysis here.

The descriptive strict distal gate was:

- epithelial inclusion: `NKX2-1 > 0 OR EPCAM > 0`
- distal restriction: `SOX2 = 0 AND SFTPC > 0 AND KRT5 = 0 AND TP63 = 0`

Under that gate, AT1-onset markers rise strongly with stage.

### Cell-level positivity under the strict distal gate

| Stage | Strict distal cells | `AGER+` | `PDPN+` | `AGER+ or PDPN+` | `SOX9+` |
|---|---:|---:|---:|---:|---:|
| GW15 | 92,401 | 0.123 | 0.247 | 0.324 | 0.680 |
| GW18 | 232,579 | 0.267 | 0.382 | 0.495 | 0.419 |

Two biological readings follow:

- `AGER` and `PDPN` are not absent from the distal field at GW15, so AT1-like
  onset is already compatible with the fetal distal epithelial compartment.
- The higher GW18 `AGER` / `PDPN` fractions, together with the lower `SOX9`
  carryover, fit a later and more committed distal-alveolar state rather than
  a fully mature AT1 state.
- Because GW15 and GW18 come from two same-series donor samples, this
  cross-stage read should still be treated as stage-aligned descriptive support
  rather than donor-resolved generalization.

### Block-level stability across spatial scales

The same strict distal read was summarized across 0.5-3.0 mm spatial blocks.
The stage difference is stable across block sizes rather than driven by one
grid choice.

| Descriptive metric within strict distal blocks | GW15 mean range | GW18 mean range |
|---|---:|---:|
| `AGER+` within distal | 0.105-0.116 | 0.263-0.268 |
| `AGER+ or PDPN+` within distal | 0.300-0.313 | 0.491-0.497 |

This stability is useful because it shows that the AT1-onset read is not
appearing only in a small number of unusually chosen bins.

## Relation To Morphology And Neighborhood Context

The morphology-linked support stays conservative.

- The registered morphology axis (`EV-0011`, `EV-0014`) supports
  tissue-embeddedness and artifact exclusion, not histology-grade alveolar
  geometry.
- In the targeted GW15 lower-field neighborhood review, all 10 reviewed tiles
  were tissue-present, distal-like, and non-proximal, with zero artifact calls.
  Four of the 10 were budtip-like and 2 of the 10 had
  mesenchymal/vascular-prominent context.

That targeted review should be used only as a local continuity check around
selected distal seeds. It is not an unbiased global QC rate and it does not
close AT1 maturity or mesenchymal niche support.

## What This Reinspection Supports

This reinspection strengthens one specific statement:

- Quach-Farrell can support **AT1-onset / early alveolar commitment within a
  distal fetal epithelial tissue context**, especially by showing a GW15 ->
  GW18 rise in `AGER` / `PDPN` positivity inside strict distal compartments.

It does not support:

- mature AT1 equivalence,
- full `alveolar_epithelial_maturation` closure,
- mesenchymal E1-E3 positive-support adjudication,
- independent cross-donor replication,
- or morphology-led alveolar geometry claims.

The main limiting reason remains the same as in the claim memo: the 339-gene
panel lacks `HOPX` and `AQP5`, so `AGER` / `PDPN` can only function as partial
AT1-onset anchors.

## Bridge Use

The bridge should use this document as a Tier 2 clarification only.

- It sharpens the line between distal tissue-context support and mature AT1
  closure.
- It helps the paper say that AT1-relevant onset is biologically visible in
  fetal tissue context.
- It also keeps the stronger honesty line: the same tissue context still does
  not close full AT1 maturity.
