# E-MTAB-11435 Tier 1-2 Bridge, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `e_mtab_11435_condition_contrast_v1.md`
  - `e_mtab_11435_integration_v1.md`
  - `paper_results_skeleton_v1.md`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

`E-MTAB-11435` is best understood as a **Tier 1-2 bridge**, not as a clean C1
budtip anchor and not as a claim-closing AT1 object.

Its bridge value comes from a specific combination:

1. the fetal-primary `self_renewing` condition is already strongly
   alveolar-fated and therefore useful for Tier 1 biological coherence;
2. the within-dataset transition from `self_renewing` to
   `alveolar_differentiation` makes Tier 2 early alveolar commitment explicit;
3. the same dataset remains limited because the exposed object is condition
   pooled rather than donor-resolved.

This makes `E-MTAB-11435` one of the most useful bridge-side datasets for
linking distal epithelial / AT2-related alignment to early AT1-relevant
commitment without over-calling mature AT1 closure.

## Why It Is Not A Clean C1 Anchor

The first point to preserve is what this dataset is **not**.

- The `self_renewing` condition contains a sizeable `SOX9+ NKX2-1+` fraction:
  `0.256` (`3,080` cells).
- But those cells are already almost universally `SFTPC+` (`0.999`) and often
  `HOPX+` (`0.488`) and `AQP5+` (`0.432`) within the same quadrant.
- Sample-wide, `self_renewing` is already:
  - `SFTPC` `0.998`
  - `HOPX` `0.425`
  - `AQP5` `0.321`
  - `AGER` `0.028`

That profile is too alveolar-fated to serve as a clean budtip reference.
`E-MTAB-8221` Day_0 remains the cleaner fetal-primary C1 anchor.

## Tier 1 Role: Fetal-Primary Alveolar-Fated Epithelial Coherence

Although `E-MTAB-11435` is not a clean C1 object, its `self_renewing`
condition is still valuable for Tier 1.

### Tier 1-relevant marker profile in `self_renewing`

| Marker | Fraction positive | Read |
|---|---:|---|
| `SFTPC` | 0.998 | near-saturated AT2-related program |
| `SFTPB` | 0.822 | strong surfactant support |
| `HOPX` | 0.425 | interpretable alveolar maturation signal |
| `AQP5` | 0.321 | interpretable fetal-primary `AQP5` retention |
| `AGER` | 0.028 | low AT1-onset signal |
| `PDPN` | 0.001 | near-floor AT1-onset signal |
| `SOX2` | 0.595 | residual self-renewing / proximal-like tone |
| `MKI67` | 0.173 | proliferative organoid state still present |

This is useful because it shows that a fetal-primary organoid can remain
proliferative and late-tip-adjacent while already carrying a strong
alveolar-fated epithelial program.

In bridge terms, `E-MTAB-11435` therefore helps Tier 1 in a different way from
`GSE237359`:

- `GSE237359` is the cleaner AT2-directed Tier 1 bridge;
- `E-MTAB-11435 self_renewing` is the more transition-proximal Tier 1 bridge.

## Tier 2 Role: Internal Late-Tip To Early Alveolar Commitment Contrast

The strongest use of `E-MTAB-11435` is the condition contrast itself.

### Main transition

| Signal | `self_renewing` -> `alveolar_differentiation` | Read |
|---|---:|---|
| C1 budtip-fit fraction | `0.133` -> `0.020` | C1-like fit collapses |
| `SOX9+ NKX2-1+` fraction | `0.256` -> `0.089` | progenitor-like pool shrinks |
| `SOX9+ NKX2-1+` cell count | `3,080` -> `755` | absolute pool shrinks |
| sample-wide `HOPX` | `0.425` -> `0.985` | near-universal alveolar commitment |
| sample-wide `AQP5` | `0.321` -> `0.451` | stronger AT1-associated maturation layer |
| sample-wide `AGER` | `0.028` -> `0.300` | stronger AT1-onset signal |
| `HOPX+ SFTPC+` all cells | `0.424` -> `0.985` | alveolar co-positive state expands |
| `MKI67` within `SOX9+ NKX2-1+` | `0.189` -> `0.000` | proliferative progenitor program is lost |
| `TP63` within `SOX9+ NKX2-1+` | `0.106` -> `0.004` | proximal/basal-like contamination decreases |

This is a strong Tier 2 read because the direction is biologically coherent at
multiple levels at once:

- less budtip-like,
- less proliferative,
- less proximal-like,
- more `HOPX`,
- more `AQP5`,
- more `AGER`.

### Within the remaining `SOX9+ NKX2-1+` compartment

The same directional story persists even if the focus is restricted to the
remaining distal progenitor-like cells.

| Marker within `SOX9+ NKX2-1+` | `self_renewing` -> `alveolar_differentiation` |
|---|---:|
| `HOPX` | `0.488` -> `0.997` |
| `AQP5` | `0.432` -> `0.691` |
| `AGER` | `0.032` -> `0.249` |

That is exactly why this dataset is a bridge: it does not merely compare two
unrelated states. It shows the same fetal-primary system moving from a
late-tip-adjacent, alveolar-fated state toward a more committed early alveolar
state.

## Why Tier 1 And Tier 2 Must Be Read Together

`E-MTAB-11435` is less informative if either condition is isolated.

- `self_renewing` alone can be misunderstood as a poor budtip object.
- `alveolar_differentiation` alone can be misunderstood as just another
  alveolar organoid endpoint.

The bridge value comes from their relation:

- the start state is already distal and alveolar-fated;
- the end state is more committed and less progenitor-like;
- the transition helps explain how Tier 1 epithelial alignment can coexist with
  only partial Tier 2/Tier 3 closure.

That makes `E-MTAB-11435` especially useful for paper logic, because it links
AT2-related alignment and AT1-onset / early alveolar commitment within one
fetal-primary system.

## What This Dataset Does Not Resolve

The main limitations should remain explicit.

- The exposed H5AD contains two pooled condition objects rather than
  donor-resolved submitted libraries, so donor/library-level replication is not
  testable here.
- The positivity summaries are based on raw count `> 0` and therefore remain a
  permissive descriptive layer rather than a calibrated expression model.
- The dataset is not a native fetal tissue-context anchor.
- It does not independently close full AT1 maturity.
- It does not resolve organoid-side E1-E3 mesenchymal niche support.
- It does not by itself justify evidence-row promotion or claim closure.

In short:

- useful as Tier 1-2 bridge;
- not usable as clean C1 reference;
- not usable as mature AT1 closure.

## Relation To Other Bridge Datasets

`E-MTAB-11435` becomes easier to interpret when placed beside the other bridge
documents.

- `GSE237359` is the strongest current fetal-primary Tier 1 AT2 bridge.
- Quach-Farrell Xenium is the fetal tissue-context anchor for Tier 2 onset
  support.
- `E-MTAB-11435` sits between them by showing a fetal-primary internal
  transition from late-tip-adjacent / alveolar-fated self-renewal to early
  alveolar commitment.

This is why the bridge should keep it as a Tier 1-2 connector rather than try
to force it into a cleaner single-tier role.

## Paper Implication

This dataset gives the paper a biologically useful middle layer.

It supports a line like:

- fetal-primary organoid systems can already carry strong distal / alveolar
  epithelial programs before full maturation;
- within such systems, a further shift toward early alveolar commitment can be
  observed through rising `HOPX`, `AQP5`, and `AGER` with loss of
  progenitor-like and proliferative features;
- but this still falls short of donor-resolved mature AT1 closure.

That is exactly the sort of Tier 1-to-Tier 2 bridge the current paper needs.
