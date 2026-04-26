# PDGFA-PDGFRA Septation Gap, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos and local notes:
  - `at1_at2_alignment_tiers_2026-04-26.md`
  - `organoid_axis_e_adjudication_2026-04-26.md`
  - `axis_e_native_to_organoid_gap_2026-04-26.md`
  - `yap_taz_at1_directionality_2026-04-26.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/he_fibroblast_axis_e_reference_v1.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/he_fibroblast_axis_e_marker_fractions_v1.tsv`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/he_epithelium_marker_fractions_v1.tsv`
- local data objects used descriptively:
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/data/snrna/E-MTAB-11278/epithelium_no_cilium.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/data/snrna/E-MTAB-11278/fibroblast_and_smooth_muscle.h5ad`
  - `/tmp/GSM8229877_AT2_organoid_filtered.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/data/external/e_mtab_11435/late_tip_organoid.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse221343/GSM6858856_L_DCI.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse221344/GSM6858858_YAP5SA.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse289846/GSE289846_3i_LATS_Day14.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse246243/GSM7865486_iAT1_72hr.h5ad`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

The current bridge can now state a more specific mechanism-level gap for
alveolar septation, but that statement must be bounded at the level of the
**publicly distributed scRNA derivatives** used in the bridge:

- native fetal lung shows **epithelial-side `PDGFA` / `VEGFA` support**
  together with **mesenchymal-side `PDGFRA` / `FGF10` / `WNT2`** and
  **elastic-fiber-associated `ELN` / `FBLN5` / `LOXL1` support**;
- current organoid-side bridge datasets retain the epithelial side of that
  story far better than the mesenchymal side **within the distributed scRNA
  objects**;
- the dominant observed failure mode is not "no alveolar-like epithelial
  program," but rather **non-capture of the receptor-side / mesenchymal
  coupling layer that would be needed for septation-like tissue
  organization**.

This sharpens the current Axis E non-closure. The organoid-side gap is not
just a generic lack of stromal support. It is specifically consistent with
failure of the current bridge scRNA objects to recover the
**`PDGFA -> PDGFRA` septation coupling axis** and the associated
**elastic-fiber program**.

At the same time, this analysis does **not** adjudicate the full composition
of the underlying culture systems. Several bridge datasets are epithelial
organoid systems by design, and several are profiled as epithelial scRNA
objects. The most accurate reading is therefore:

- native fetal reference contains a coupled epithelial-plus-mesenchymal
  septation context;
- the current distributed organoid scRNA derivatives do not capture the
  receptor-side / septation-ECM half of that context in a bridge-usable way;
- whether a given underlying culture system contained feeder, support, or
  transient non-profiled stromal components is a separate question.

Dataset-level separation of **culture design**, **profiling design**, and
**distributed object composition** is recorded in
`culture_profiling_object_triage_2026-04-26.md`.

## Scope Caveat: Object Composition Versus Culture Composition

This note describes the composition and limits of the **publicly distributed
scRNA objects** currently used in the bridge. It does not by itself prove that
the underlying culture systems never contained any stromal or support
components.

Three layers must be kept distinct:

1. **Culture level**: whether the experimental system was epithelial-only,
   feeder-supported, or explicitly co-cultured.
2. **Profiling level**: whether the scRNA dataset was generated from an
   unsorted whole culture, a live-cell-enriched suspension, or an
   epithelial/reporter-enriched compartment.
3. **Distributed object level**: what cell types are actually recoverable from
   the released count matrix / h5ad used in the bridge.

The present document directly demonstrates the third layer and infers a bridge
usable consequence: the released objects are much more informative about the
epithelial ligand side than the receptor-side mesenchymal / septation-ECM
side. It does **not** by itself show that every underlying culture lacked all
mesenchymal potential under all conditions.

## Why This Axis Was Chosen

Among septation-related mechanisms, `PDGFA -> PDGFRA` is one of the most
load-bearing candidates for a cheap re-read because it directly connects:

- epithelial alveolar-fated cells,
- septation-relevant fibroblast / myofibroblast populations,
- the existing bridge distinction between epithelial success and Axis E
  non-closure.

This axis is therefore a good test of whether the organoid-side gap can be
described more specifically than "mostly epithelial."

## Native Fetal Baseline

### Epithelial side: `PDGFA` and `VEGFA` are present in distal / alveolar-fated cells

Using He `epithelium_no_cilium`, the main epithelial groups all carry
`PDGFA`, while `VEGFA` is strongest in `AT1`.

| He epithelial group | `PDGFA` frac+ | `VEGFA` frac+ | `SFTPC` frac+ | `AGER` frac+ | `PDPN` frac+ | `HOPX` frac+ | `AQP5` frac+ |
|---|---:|---:|---:|---:|---:|---:|---:|
| `Late tip` | 0.596 | 0.551 | 0.998 | 0.515 | 0.333 | 0.489 | 0.100 |
| `AT2` | 0.560 | 0.545 | 0.966 | 0.764 | 0.560 | 0.652 | 0.068 |
| `AT1` | 0.555 | 0.717 | 0.633 | 0.968 | 0.816 | 0.883 | 0.459 |

Three biological points follow.

1. Native fetal epithelial compartments do not treat `PDGFA` as an external
   mesenchymal-only signal; it is already present in distal / alveolar-fated
   epithelial cells.
2. `VEGFA` is strongest in `AT1`, fitting the known vascular-coupling side of
   alveolar maturation.
3. This means the native fetal baseline already contains the **epithelial
   ligand side** of septation-relevant signaling.

### Mesenchymal side: `PDGFRA`, `FGF10`, `WNT2`, and elastic-fiber genes are native-positive

Using He `fibroblast_and_smooth_muscle` together with the existing local fibro
reference tables, the native mesenchymal side is clearly populated.

Selected native examples:

| He mesenchymal group | `PDGFRA` frac+ | `FGF10` frac+ | `WNT2` frac+ | `ELN` frac+ | `FBLN5` frac+ | `LOXL1` frac+ |
|---|---:|---:|---:|---:|---:|---:|
| `Alveolar fibro` | 0.387 | 0.347 | 0.940 | 0.829 | 0.625 | 0.637 |
| `Early fibro` | 0.481 | 0.050 | 0.484 | 0.440 | 0.236 | 0.379 |
| `Interm fibro` | 0.452 | 0.329 | 0.790 | 0.868 | 0.777 | 0.531 |
| `Myofibro 1` | 0.825 | 0.045 | 0.287 | 0.727 | 0.266 | 0.383 |
| `Myofibro 2` | 0.916 | 0.039 | 0.131 | 0.881 | 0.257 | 0.322 |
| `Myofibro 3` | 0.827 | 0.041 | 0.469 | 0.827 | 0.184 | 0.367 |

This matters because native fetal lung does not show only one half of the
axis. It contains:

- a ligand-capable distal / alveolar-fated epithelium,
- a receptor-positive fibroblast / myofibroblast compartment,
- and a real elastic-fiber-associated structural program.

So the native reference already supports a **coupled epithelial-mesenchymal
septation context**, not just isolated epithelial fate markers.

## Organoid-Side Bridge Re-read

### `GSE237359`: strong epithelial Tier 1, no real receptor-side mesenchymal layer in the distributed object

`GSE237359` remains a strong epithelial AT2 bridge:

- sample-wide `SFTPC`: 1.000
- sample-wide `HOPX`: 0.897
- sample-wide `AQP5`: 0.304

But the septation-coupling layer is missing:

- sample-wide `PDGFA`: 0.038
- sample-wide `VEGFA`: 0.304
- `PDGFRA`: not detected in the object
- `FGF10`: not detected in the object
- `WNT2`: essentially absent (`0.0009`)
- `LOX`: only `0.007`

The most informative finding is the predicted-fibro subset re-read.

`Mid fibro`, `Interm fibro`, and `Adventitial fibro` labels inside this object
still show:

- `SFTPC` = 1.000 in all three groups,
- `HOPX` high,
- `PDGFRA` absent,
- `FGF10` absent,
- `WNT2` absent or effectively zero.

So these are not functioning as a true receptor-side mesenchymal compartment
**within the released scRNA object**. They behave as epithelial cells carrying
fibro-like projection labels, not as native-like `PDGFRA+` niche or
septation populations.

### `E-MTAB-11435`: fetal-primary compatibility without septation coupling

`E-MTAB-11435` is still useful for fetal-primary epithelial commitment:

- sample-wide `SFTPC`: 0.999
- sample-wide `AQP5`: 0.375
- sample-wide `HOPX`: 0.655
- sample-wide `AGER`: 0.140

But again the mesenchymal coupling layer is weak or absent in the released
object:

- sample-wide `PDGFA`: 0.025
- sample-wide `VEGFA`: 0.275
- `PDGFRA`: not detected in the object
- `FGF10`: 0.0018
- `FBN2`: 0.0276
- `FBLN5`: 0.0524
- `LOX`: 0.0206
- `LOXL1`: 0.0146

Group-level re-reads (`Tip`, `AT2-like`, `Differentiating AT2`, `AT1-like`)
show the same pattern:

- epithelial AT1/AT2 markers are present,
- `PDGFRA` is absent,
- `FGF10` is absent or effectively zero,
- `WNT2` is absent,
- ECM-related genes are at best low-level accessory signals.

So this object is compatible with epithelial Tier 1/Tier 2 biology, but the
distributed scRNA derivative is not carrying a native-like
`PDGFA -> PDGFRA` septation architecture.

### iPSC / hESC directed conditions: epithelial ligand side without receptor side in the current scRNA objects

The same asymmetry recurs in the organoid-side directed conditions.

Representative sample-wide examples:

| Sample | `PDGFA` frac+ | `VEGFA` frac+ | `PDGFRA` frac+ | `FGF10` frac+ | `ELN` frac+ | `SFTPC` frac+ | `AGER` frac+ | `HOPX` frac+ | `AQP5` frac+ |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| `GSM6858856_L_DCI` | 0.191 | 0.483 | 0.000 | 0.000 | 0.0002 | 0.388 | 0.513 | 0.633 | 0.117 |
| `GSM6858858_YAP5SA` | 0.178 | 0.599 | 0.0002 | 0.000 | 0.0000 | 0.915 | 0.470 | 0.665 | 0.140 |
| `GSE289846_3i_LATS_Day14` | 0.383 | 0.826 | 0.011 | 0.002 | 0.004 | 0.044 | 0.451 | 0.854 | 0.011 |
| `GSM7865486_iAT1_72hr` | 0.089 | 0.640 | 0.000 | 0.000 | 0.0000 | 0.121 | 0.213 | 0.876 | 0.034 |

This is the same repeated structure:

- ligand-compatible epithelial genes (`PDGFA`, `VEGFA`) are present,
- AT1-facing markers can rise strongly,
- receptor-side and septation-ECM genes remain absent or nearly absent.

So even when organoid systems move directionally toward AT1-like states, the
currently distributed scRNA derivatives still do not recover the
**mesenchymal receptor / structural half** of the septation program.

## Mechanistic Interpretation

This re-read suggests that the bridge-side non-closure can now be described
more specifically at the level of the distributed scRNA objects.

The current organoid object landscape does not simply lack "some stromal
support." It specifically lacks convincing evidence for:

- **`PDGFRA`-positive receptor-side mesenchymal coupling**
- **`FGF10` / `WNT2` alveolar-fibro niche support**
- **elastic-fiber-associated septation machinery at a native-like level**
  (`ELN`, `FBLN5`, `LOXL1`, and related structural genes)

At the same time, the epithelial side is much more intact:

- `PDGFA` and `VEGFA` remain compatible with distal / alveolar-fated states,
- AT2- and AT1-facing markers can be strong,
- YAP/TAZ-facing positive arms can push early AT1 directionality.

So the failure mode observed here is not absence of epithelial commitment. It
is failure of the current bridge scRNA derivatives to recover the
**coupled epithelial-plus-mesenchymal septation system** that native fetal
lung already shows.

## What This Supports

This analysis supports:

- a more specific molecular reading of Axis E non-closure,
- a more specific explanation for why Tier 2 can be positive while septation
  and Tier 3 remain open,
- the distinction between **epithelial ligand-side compatibility** and
  **mesenchymal receptor-side / ECM closure**,
- continued separation of organoid epithelial success from tissue-level
  alveolarization claims.

It does not support:

- direct adjudication of the full underlying culture composition for each
  organoid system,
- full alveolar septation closure,
- vascular-coupling closure,
- direct proof that any single organoid system entirely lacks all septation
  potential under all conditions,
- promotion of these observations into registered evidence without a separate
  review step.

## Paper Implication

This gives the paper a sharper molecular sentence than the previous generic
"mostly epithelial" wording.

The bridge can now say, in effect:

> current organoid systems can reproduce epithelial alveolar-fated states and
> early AT1-facing directionality, but they do not recover the native fetal
> `PDGFA -> PDGFRA` septation-coupling axis or the associated elastic-fiber
> mesenchymal program needed for tissue-level alveolarization claims.
