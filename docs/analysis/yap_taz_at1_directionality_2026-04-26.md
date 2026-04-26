# YAP/TAZ-AT1 Directionality Read, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos and local reports:
  - `yap_taz_at1_inventory_2026-04-26.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/tranches/gse221343_query_ready_review_v1/gse221343_query_ready_decisions_v1.tsv`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/tranches/gse221344_query_ready_review_v1/gse221344_query_ready_decisions_v1.tsv`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/gse289846_integration_v1.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/repo_state/p0002_alveolar_commitment_design_v1.md`
- local converted objects used descriptively:
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse221343/GSM6858854_CK_DCI.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse221343/GSM6858855_YAP5SA_CK_DCI.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse221343/GSM6858856_L_DCI.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse221344/GSM6858857_WT_YAP.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse221344/GSM6858858_YAP5SA.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse289846/GSE289846_3i_Day7.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse289846/GSE289846_3i_LATS_Day14.h5ad`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/queries/converted/gse289846/GSE289846_3i_PAL_Day14.h5ad`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

Three organoid-side layers now give a coherent YAP/TAZ-facing AT1 directionality
read:

1. `GSE221344` gives the cleanest **direct YAP perturbation** signal.
2. `GSE221343` shows that `YAP5SA+CK+DCI` produces a strong mechanistic shift
   but still does not fully reproduce the directed `L+DCI` endpoint.
3. `GSE289846` shows a **cross-lab pharmacologic analog** in which
   `LATS-IN-1` pushes the same AT1-facing program, whereas `PAL` does not.

Across all three layers, the most reproducible positive-arm features are:

- large `ANKRD1` activation,
- increased `TEAD1` / `TEAD4`-side signal,
- increased `AGER`, `HOPX`, and often `PDPN`,
- increased `CAV1`, `CAV2`, and `EMP2`,
- reduced `SOX9` and reduced or collapsing `SFTPC` in the stronger
  differentiation contexts.

The same data also set an important boundary:

- `AQP5` does **not** rise in parallel with the strongest YAP/TAZ-facing
  positive arms and often falls.

So these tranches strengthen a **Tier 2 mechanistic interpretation** and
clarify the **Tier 3 mature-AT1 boundary**, but they do not close mature AT1.

## Metadata Clarifications Used For This Read

This analysis depends on three metadata clarifications that should remain
explicit whenever these tranches are discussed.

1. `GSE221344` `WT-YAP` is a **lentiviral control**, not an untransduced
   baseline.
2. `GSE221343` `YAP5SA+CK+DCI` is a **maintenance-medium perturbation arm**,
   not the same object as `L+DCI` iAT1 differentiation.
3. `GSE289846` `LATS-IN-1` is a **pharmacologic Hippo/YAP analog** in a
   different iPSC line (`B2-3`), not a same-line replication of SPC2-ST-B2.

These clarifications are not cosmetic. They determine what can and cannot be
claimed biologically.

## Mechanobiology Panel Used

The descriptive panel was intentionally narrow:

- pathway-facing: `YAP1`, `WWTR1`, `TEAD1`, `TEAD4`, `ANKRD1`
- transcriptional bridge: `NKX2-1`, `KLF5`, `NFIB`
- AT1-facing: `AGER`, `PDPN`, `HOPX`, `AQP5`
- alveolar retention / exit: `SFTPC`, `SOX9`
- flattening / membrane-associated context: `CAV1`, `CAV2`, `EMP2`, `CLDN18`

Sample-wide positivity fractions (`raw_count > 0`) and sample-wide mean
expression were read descriptively from the converted `h5ad` objects. This is
not a differential-expression framework and is not used here as evidence-row
material.

## `GSE221344`: Direct YAP Perturbation

The paired SPC2-ST-B2 perturbation tranche is the strongest direct positive
arm.

### Main shifts: `WT-YAP -> YAP5SA`

| Gene | `WT-YAP` frac+ | `YAP5SA` frac+ | Biological read |
|---|---:|---:|---|
| `ANKRD1` | 0.005 | 0.588 | strong YAP/TAZ target activation |
| `TEAD1` | 0.345 | 0.547 | stronger TEAD-side program |
| `TEAD4` | 0.061 | 0.286 | stronger TEAD-side program |
| `AGER` | 0.025 | 0.470 | strong AT1-facing shift |
| `PDPN` | 0.000 | 0.051 | weak but real AT1-facing gain |
| `HOPX` | 0.559 | 0.665 | stronger AT1-associated identity |
| `SOX9` | 0.076 | 0.034 | distal progenitor carryover decreases |
| `CAV1` | 0.027 | 0.541 | strong flattening / membrane-context gain |
| `CAV2` | 0.058 | 0.486 | same direction as `CAV1` |
| `EMP2` | 0.625 | 0.765 | membrane / AT1-facing compatibility gain |

Two counterpoints remain crucial:

- `SFTPC` stays very high (`0.997 -> 0.915`), so this is not a clean
  sample-wide AT2-to-AT1 replacement.
- `AQP5` rises only weakly (`0.082 -> 0.140`), far from a mature-AT1 closure
  read.

This is therefore best read as a **direct mechanistic positive arm with
partial AT1-directional shift**, not as mature AT1 conversion.

## `GSE221343`: YAP Perturbation Versus Directed Differentiation

This same-line SPC2-ST-B2 trio is especially useful because it shows what
YAP/TAZ-like activation can and cannot reproduce relative to a stronger directed
medium.

### `CK+DCI -> YAP5SA+CK+DCI`

`YAP5SA+CK+DCI` strongly activates the mechanobiology-side panel:

- `ANKRD1`: `0.020 -> 0.740`
- `TEAD1`: `0.274 -> 0.586`
- `TEAD4`: `0.029 -> 0.268`
- `AGER`: `0.021 -> 0.530`
- `HOPX`: `0.495 -> 0.571`
- `CAV1`: `0.043 -> 0.632`
- `CAV2`: `0.086 -> 0.517`
- `EMP2`: `0.568 -> 0.787`

At the same time:

- `SFTPC` drops sharply: `0.996 -> 0.618`
- `SOX9` nearly disappears: `0.031 -> 0.003`
- `AQP5` falls: `0.273 -> 0.182`

So YAP activation in maintenance medium does not look inert. It produces a
clear AT1-facing mechanistic shift. But it still does not by itself become the
same biological object as directed iAT1 differentiation.

### `YAP5SA+CK+DCI` versus `L+DCI`

`L+DCI` remains the stronger state-resolution endpoint, while `YAP5SA+CK+DCI`
shows the sharper acute mechanistic-target signal.

Examples:

- `ANKRD1`: higher in `YAP5SA+CK+DCI` (`0.740`) than `L+DCI` (`0.241`)
- `AGER`: similar (`0.530` versus `0.513`)
- `HOPX`: higher in `L+DCI` (`0.633`) than `YAP5SA+CK+DCI` (`0.571`)
- `SFTPC`: lower in `L+DCI` (`0.388`) than `YAP5SA+CK+DCI` (`0.618`)
- `EMP2`: higher in `L+DCI` (`0.901`) than `YAP5SA+CK+DCI` (`0.787`)
- `CLDN18`: higher in `L+DCI` (`0.282`) than `YAP5SA+CK+DCI` (`0.010`)

This suggests the following interpretation:

- `YAP5SA+CK+DCI` is better at exposing a **mechanistic YAP/TAZ-positive arm**;
- `L+DCI` is better at resolving a broader **AT1-directed differentiation
  endpoint**.

That difference is biologically useful. It argues against collapsing YAP/TAZ
activation and full directed differentiation into one thing.

## `GSE289846`: Cross-Lab Pharmacologic Analog

The Kyoto / `B2-3` tranche independently points in the same direction when the
Hippo pathway is perturbed pharmacologically.

### `3i_Day7 -> LATS-IN-1_Day14`

| Gene | `3i_Day7` frac+ | `LATS_Day14` frac+ | Biological read |
|---|---:|---:|---|
| `WWTR1` | 0.734 | 0.796 | stronger Hippo/YAP-side compatibility |
| `TEAD1` | 0.762 | 0.871 | stronger TEAD-side program |
| `TEAD4` | 0.211 | 0.544 | stronger TEAD-side program |
| `ANKRD1` | 0.247 | 0.709 | strong pathway activation |
| `KLF5` | 0.641 | 0.758 | stronger transcriptional bridge |
| `NFIB` | 0.758 | 0.830 | stronger transcriptional bridge |
| `AGER` | 0.077 | 0.451 | strong AT1-facing gain |
| `PDPN` | 0.372 | 0.501 | AT1-facing gain |
| `HOPX` | 0.612 | 0.854 | strong AT1-associated gain |
| `SOX9` | 0.148 | 0.030 | progenitor carryover decreases |
| `CAV1` | 0.148 | 0.705 | membrane / flattening-compatible gain |
| `EMP2` | 0.533 | 0.892 | strong compatibility gain |

Again the same mature-AT1 boundary appears:

- `AQP5` decreases (`0.060 -> 0.011`)
- `SFTPC` decreases strongly (`0.121 -> 0.044`)

So `LATS-IN-1` is highly consistent with a YAP/TAZ-facing AT1-directed shift,
but not with mature-AT1 closure.

### `PAL_Day14` as a counterexample

`PAL` does not reproduce the same panel:

- `ANKRD1` remains low (`0.170`)
- `AGER` remains low (`0.086`)
- `HOPX` is lower than both `3i_Day7` and `LATS_Day14` (`0.347`)
- `SFTPC` is nearly absent (`0.012`)
- `AQP5` remains near zero (`0.009`)

This makes `PAL` a useful negative comparator inside the same dataset family:
not every Day14 perturbation produces the YAP/TAZ-like AT1-facing pattern.

## Integrated Reading

Across direct YAP perturbation and pharmacologic Hippo perturbation, the
consistent bridge-side signal is:

- **pathway activation**: `ANKRD1`, `TEAD1`, `TEAD4`
- **AT1-facing shift**: `AGER`, `HOPX`, often `PDPN`
- **flattening / membrane compatibility**: `CAV1`, `CAV2`, `EMP2`
- **progenitor exit**: lower `SOX9`

What remains inconsistent with full mature AT1 is also reproducible:

- `AQP5` does not track with the strongest positive arms
- `SFTPC` often remains high in direct YAP perturbation or collapses without
  producing a clean mature-AT1 signature

So the current best bridge-side reading is:

- YAP/TAZ-related perturbation is **directionally aligned with AT1-onset and
  early AT1-facing differentiation**;
- YAP/TAZ-related perturbation is **not equivalent to full mature AT1
  resolution**.

## What This Supports

This analysis supports:

- a stronger mechanistic interpretation for Tier 2 AT1-onset,
- a better-defined Tier 3 boundary,
- metadata-level separation between direct perturbation, directed medium, and
  pharmacologic analog layers,
- future use of `GSE246243` as the most natural next kinetic tranche for
  ordering a YAP/TAZ-like module against BU3 commitment timing.

It does not support:

- mature AT1 closure,
- direct fetal-spatial YAP/TAZ activity adjudication,
- a claim that YAP/TAZ alone explains the whole bridge-side AT1 program,
- promotion of these local reads into registered evidence without a separate
  review step.
