# Culture / Profiling / Object Triage for Septation-Gap Datasets, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos and local notes:
  - `pdgfa_pdgfra_septation_gap_2026-04-26.md`
  - `yap_taz_at1_directionality_2026-04-26.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/candidate_eval_gse246243_v1.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/new_organoid_query_candidate_longlist_v1.md`
- source records / primary dataset pages:
  - `GSE237359` GEO / EMBO Journal fdAT2 paper
  - `E-MTAB-11435` Cell Stem Cell / STAR Protocols / ArrayExpress record
  - `GSE221343`, `GSE221342`, `GSE221344`, `GSE246243` GEO / Cell Stem Cell
    iAT1 paper
  - `GSE289846` GEO
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Purpose

The septation-gap re-read showed a repeated asymmetry:

- epithelial ligand-side markers are often recoverable in organoid-side bridge
  objects;
- receptor-side mesenchymal / septation-ECM components are not.

That observation is real at the **distributed object** level, but it does not
automatically tell us whether the underlying **culture systems** themselves
lacked all stromal or support components. This note therefore separates three
layers for the six datasets directly implicated in the current septation-gap
discussion:

1. **culture level**: what was grown;
2. **profiling level**: what was dissociated / selected for scRNA;
3. **distributed object level**: what is actually recoverable from the public
   object currently used in the bridge.

## Bottom Line

Across these six datasets, the current bridge can say something narrower and
more accurate than "organoids lack septation machinery."

What the bridge currently shows is:

- the public scRNA derivatives are strongly epithelial-weighted;
- in several datasets, that epithelial weighting is expected by construction
  because the underlying systems are epithelial organoids or epithelial
  reporter-line differentiations;
- the released objects therefore cannot be used as direct negative evidence
  that the full culture system never contained any stromal support.

The bridge-useful claim is therefore:

> the current public scRNA derivatives do not recover a bridge-usable
> receptor-side mesenchymal septation compartment.

That is stronger than a generic "mostly epithelial" statement, but more
honest than a culture-level "no mesenchyme existed" statement.

## Accession Sanity Check: `GSE221342` Versus `GSE221344`

One metadata issue needs to be stated explicitly.

- GEO series pages identify `GSE221342` as the **BU3 NGAT 3D versus ALI**
  dataset and `GSE221344` as the **WT-YAP versus YAP5SA** lentiviral
  perturbation dataset.
- The Cell Stem Cell iAT1 paper's key-resources / data-availability table
  appears to swap those two accession labels, listing WT-YAP / YAP5SA under
  `GSE221342` and 3D versus ALI under `GSE221344`.

This note follows **GEO series pages and distributed sample files as accession
authority**:

- `GSE221342` = `iAT2 3D`, `iAT1 3D`, `iAT1 ALI p0`, `iAT1 ALI p1`
- `GSE221344` = `GSM6858857_WT_YAP`, `GSM6858858_YAP5SA`

## Dataset Triage

### `GSE237359`

- culture level:
  - fetal-derived AT2 (`fdAT2`) 3D organoids derived from 16-22 pcw human
    fetal tip epithelium / immature AT2-compatible distal epithelium.
  - This is an epithelial organoid system, not a mesenchyme-profiled co-culture
    design.
- profiling level:
  - four biological fdAT2 organoid lines were harvested, dissociated with
    TrypLE, pooled, and run through 10x Chromium 5' scRNA-seq.
  - The scRNA object is therefore a pooled organoid-cell suspension, not an
    unsorted fetal tissue object.
- distributed object level:
  - the released bridge object contains donor demultiplexing and projected
    labels, but current re-read still finds no bona fide `PDGFRA+`
    receptor-side mesenchymal compartment.
  - fibro-like projected labels remain `SFTPC`-saturated and therefore behave
    as epithelial cells carrying fibro-like transfer labels, not as true
    septation mesenchyme.
- bridge implication:
  - `GSE237359` is informative for epithelial Tier 1 / AT2 biology and for
    object-level annotation failure modes.
  - It is not valid as direct evidence that the underlying fdAT2 culture system
    completely lacked all stromal influence.

### `E-MTAB-11435`

- culture level:
  - fetal late-stage distal lung epithelial progenitors were isolated as distal
    epithelial organoids; the associated protocol explicitly describes
    epithelial isolation using `EpCAM` microbeads and enrichment of
    `CD36+` alveolar-fated `LinPOS` tip organoids.
  - The relevant bridge biology is therefore being modeled in an epithelial
    organoid system from the outset.
- profiling level:
  - four biological replicates of `LinPOS` and alveolar organoids were
    individually harvested, enzymatically dissociated, and profiled by 10x
    Chromium 5' scRNA-seq.
  - This is not a released unsorted mixed epithelial-plus-mesenchymal tissue
    object.
- distributed object level:
  - the local bridge object used here is a late-tip/alveolar organoid derivative
    with epithelial author states (`Tip`, `AT2-like`, `Differentiating AT2`,
    `AT1-like`, `Basal cell-like`).
  - current re-read finds no recoverable `PDGFRA+` receptor-side mesenchymal
    compartment in that distributed object.
- bridge implication:
  - this dataset is strong for fetal-primary epithelial commitment logic.
  - it cannot be used as a negative test of mesenchymal coupling at the full
    culture-system level.

### `GSE221343`

- culture level:
  - SPC2-ST-B2 iPSC-derived alveolar epithelial cells in 3D culture across
    `CK+DCI`, `YAP5SA in CK+DCI`, and `L+DCI` conditions.
  - This is a directed epithelial differentiation system.
- profiling level:
  - sample-level GEO metadata states that cells were dissociated to single
    cells using `0.05% trypsin` and sorted for live cells using `DRAQ7`,
    followed by 10x Chromium 3' v2 scRNA-seq.
  - The profiling step therefore explicitly enriches for live dissociated
    cells from an epithelial differentiation object.
- distributed object level:
  - the public release consists of per-condition CellRanger H5 matrices with
    minimal sample metadata and no mesenchymal annotation layer.
  - current bridge reads these objects as epithelial-only count matrices and
    does not recover a receptor-side septation compartment.
- bridge implication:
  - the `PDGFRA`-side absence here should be read primarily as an
    epithelial-object design feature, not as a test of mixed-culture capacity.

### `GSE221344`

- culture level:
  - SPC2-ST-B2 iAT2s were transduced in single-cell suspension with either
    control WT-YAP or activated `YAP5SA` lentivirus and then regrown in
    `CK+DCI` 3D Matrigel culture.
  - This is a cell-autonomous epithelial perturbation system.
- profiling level:
  - the released series contains two scRNA count matrices corresponding to the
    WT-YAP and `YAP5SA` perturbation arms.
  - sample-level extraction protocol was not separately re-read in this note,
    but the system is defined at the series level as lentivirally perturbed
    iAT2-derived epithelial scRNA-seq rather than a mixed stromal profiling
    design.
- distributed object level:
  - the current bridge uses two per-condition epithelial objects
    (`GSM6858857_WT_YAP`, `GSM6858858_YAP5SA`).
  - no bridge-usable receptor-side mesenchymal compartment is recoverable from
    those objects.
- bridge implication:
  - `GSE221344` is useful for epithelial YAP directionality only.
  - it is not informative as a culture-level mesenchyme test.

### `GSE289846`

- culture level:
  - human iPSC-derived pulmonary epithelial cells were seeded on micropatterned
    plates, cultured in `DCIK+3i` medium, then switched to either
    `DCI+LATS-IN-1` or `PAL`.
  - The stated design centers epithelial pulmonary differentiation rather than
    explicit stromal co-culture.
- profiling level:
  - GEO states that organoids in each condition were dissociated using
    Accutase and subjected to scRNA-seq.
  - No separate mesenchymal sampling strategy is described in the series
    summary.
- distributed object level:
  - the released bridge objects are per-condition matrices
    (`3i_Day7`, `3i_LATS_Day14`, `3i_PAL_Day14`).
  - current re-read recovers pulmonary epithelial programs and YAP/TAZ-facing
    directionality but not a receptor-side septation compartment.
- bridge implication:
  - this dataset adds cross-lab epithelial mechanistic support.
  - it does not function as a direct stromal-coupling readout.

### `GSE246243`

- culture level:
  - BU3 NGAT iAT2-to-iAT1 kinetic series in 3D culture, sampled at baseline
    (`CK+DCI`) and `24 hr`, `48 hr`, `72 hr` after switch into `L+DCI`.
  - This is a same-line epithelial commitment time series.
- profiling level:
  - the source paper describes a 72 hr scRNA time series during `CK+DCI -> L+DCI`
    transition.
  - local candidate-intake notes record that GEO distributes per-GSM filtered H5
    files from a 10x Chromium / CellRanger workflow on `GPL30173` (NextSeq
    2000), consistent with the Kotton family data structure.
- distributed object level:
  - the bridge uses four per-timepoint H5ADs (`iAT2 3D`, `iAT1 24 hr`,
    `iAT1 48 hr`, `iAT1 72 hr`).
  - these are epithelial timepoint objects and do not recover a receptor-side
    mesenchymal compartment.
- bridge implication:
  - `GSE246243` is a kinetic epithelial commitment extension.
  - it cannot adjudicate mesenchymal septation coupling from the released
    object alone.

## Practical Readout for the Septation-Gap Story

After this triage, the current bridge should interpret the septation-gap
analysis as follows.

1. Native fetal references demonstrate that the coupled
   `PDGFA/VEGFA` ligand side and `PDGFRA/FGF10/WNT2/ELN/FBLN5/LOXL1`
   mesenchymal side coexist in real fetal lung context.
2. Current organoid-side bridge objects repeatedly preserve the epithelial
   side better than the receptor / ECM side.
3. That repeated asymmetry is real and biologically useful at the **object
   level**.
4. But it is not equivalent to the stronger statement that every underlying
   culture system entirely lacked all mesenchymal or support components.

## What This Supports

This note supports:

- rephrasing the septation-gap document in object-level terms,
- explicit separation of `culture`, `profiling`, and `distributed object`
  interpretations,
- continued use of the current datasets for epithelial Tier 1 / Tier 2 and
  mechanistic directionality,
- continued caution about using their negative mesenchymal results as
  culture-level failure claims.

It does not support:

- declaring that all six underlying culture systems lacked mesenchyme,
- using current negative `PDGFRA` reads as direct evidence against all possible
  co-culture or feeder-supported variants of those systems,
- promoting any of these observations into registered evidence without a
  separate review step.
