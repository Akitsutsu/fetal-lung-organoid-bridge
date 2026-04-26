# YAP/TAZ And AT1 Inventory Reconsideration, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos and local reports:
  - `at1_at2_alignment_tiers_2026-04-26.md`
  - `quach_farrell_at1_onset_reinspection_2026-04-26.md`
  - `gse237359_tier1_at2_bridge_2026-04-26.md`
  - `e_mtab_11435_tier1_tier2_bridge_2026-04-26.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/tranches/gse221343_query_ready_review_v1/gse221343_query_ready_decisions_v1.tsv`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/tranches/gse221344_query_ready_review_v1/gse221344_query_ready_decisions_v1.tsv`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/repo_state/p0001_geo_candidate_reevaluation_v1.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/repo_state/p0002_alveolar_commitment_design_v1.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/reports/repo_state/gse246243_candidate_value_v1.md`
  - `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/gse289846_integration_v1.md`
- external primary-literature anchors:
  - Nguyen et al. 2021, stretch / ROCK / YAP / TAZ fetal AT1 differentiation
    (`PMID: 34431413`)
  - Gokey et al. 2021, YAP regulates `AGER` via `NFIB` / `KLF5` / `NKX2-1`
    (`PMID: 34466790`)
  - Alysandratos et al. 2023, human iAT1 generation and Hippo-LATS-YAP
    enrichment (`PMID: 36711505`)
  - Ueda et al. 2024, `LATS-IN-1` and YAP/TAZ activation in human iPSC AT1
    induction (`PMID: 38552636`)
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

If YAP/TAZ-related AT1 interpretation is added to the bridge, the inventory
should be reconsidered as a **layered mechanobiology package**, not as a
single-dataset extension of the current fetal AT1 marker ladder.

The key reason is simple:

- current bridge-native fetal datasets are strong for **Tier 1 AT2-related
  distal alignment** and partial **Tier 2 AT1-onset**;
- those same datasets are weak for **direct YAP/TAZ pathway adjudication**;
- the strongest direct YAP/TAZ directionality surfaces in the local inventory
  are actually **same-line perturbation** and **pharmacologic induction**
  tranches on the organoid side.

The most honest bridge-side design is therefore:

1. use **same-line perturbation / induction** datasets for the direct
   mechanistic direction;
2. use **BU3 kinetic / endpoint** datasets for commitment ordering;
3. use **fetal-primary and fetal-spatial** datasets for compatibility and
   explicit non-closure of mature AT1.

This keeps mechanistic interpretation biology-first without pretending that the
current fetal spatial layer directly measures YAP/TAZ activity.

## Why The Inventory Needs Reconsideration

The current AT1/AT2 bridge is organized around a biological tier ladder:

- Tier 1: AT2-related distal alignment
- Tier 2: AT1-onset / early alveolar commitment
- Tier 3: full AT1 maturity open

That ladder is still correct. The issue is that YAP/TAZ is not merely another
AT1 marker. It is an **upstream mechanotransductive axis** whose strongest
evidence often comes from perturbation, localization, and pathway-activity
readouts rather than from static marker co-expression alone.

Without an inventory rethink, a YAP/TAZ addition would risk collapsing three
different questions:

- whether AT1-relevant markers are present,
- whether AT1-directed differentiation is mechanically inducible,
- whether native fetal tissue context directly supports a YAP/TAZ mechanism.

Those questions should remain separate.

## Inventory Layers

| Layer | Dataset / tranche | What it contributes | Why it matters for YAP/TAZ | Main limitation |
|---|---|---|---|---|
| Direct same-line perturbation | `GSE221344` SPC2-ST-B2 `WT-YAP` vs `YAP5SA` | paired lentiviral control versus constitutively active nuclear YAP | strongest direct organoid-side YAP perturbation already in local inventory | partial positive-arm only; top state remains proliferating-progenitor-like |
| Same-line induction ladder | `GSE221343` SPC2-ST-B2 `CK+DCI`, `YAP5SA+CK+DCI`, `L+DCI` | distinguishes baseline, YAP activation in maintenance medium, and directed iAT1 medium | asks whether YAP activation alone recapitulates the stronger L+DCI shift | no format-only arm; not a fetal tissue anchor |
| Cross-lab pharmacologic analog | `GSE289846` B2-3 `3i_Day7` vs `LATS-IN-1_Day14` | independent iPSC system with Hippo/YAP-activating perturbation | provides cross-lab directionality and aligns with recent PSC literature | confounds time and treatment; local-only sample-wide read so far |
| BU3 endpoint commitment chain | `GSE221342` BU3 NGAT `iAT2_3D -> iAT1_3D -> ALI_p0 -> ALI_p1` | best current endpoint ordering toward AT1-like state | anchor for where a mechanistic program would need to point | not a direct YAP perturbation experiment |
| BU3 kinetic commitment chain | `GSE246243` BU3 NGAT `0/24/48/72 hr L+DCI` | same-line temporal ordering of early commitment | best candidate to ask whether mechanistic genes precede stronger AT1-marker resolution | candidate tranche only; not yet acquired into current bridge workflow |
| Fetal-primary compatibility | `GSE237359`, `E-MTAB-11435` | fetal-primary epithelial compatibility around Tier 1 / Tier 2 | can test whether mechanobiology-linked genes are at least compatible with fetal-primary alveolar-fated states | not direct perturbation; pooled or sample-wide reads remain limited |
| Fetal spatial tissue context | Quach-Farrell Xenium `GSE264425` | strict distal tissue context and stage-enriched `AGER` / `PDPN` onset | says where AT1-onset sits in fetal tissue space | panel does not include `YAP1`, `WWTR1`, `HOPX`, `AQP5`, `CTGF`, or `CYR61` |
| Native mesenchymal context | He Visium / Axis E neighborhood layer | adjacency-scale E1/E2/E3 niche logic | motivates a mechanobiology interpretation rather than same-spot epithelial isolation | not a direct YAP/TAZ activity assay |

## Layer 1: Direct YAP/TAZ Directionality Is Already In The Inventory

The strongest direct YAP/TAZ dataset currently on hand is not fetal spatial,
but the SPC2-ST-B2 paired perturbation tranche.

### `GSE221344`: paired `WT-YAP` versus `YAP5SA`

This is the cleanest direct mechanistic inventory element because it holds:

- same line: `SPC2-ST-B2`
- same medium / same timepoint
- matched lentiviral control
- constitutively active nuclear YAP perturbation

Current local query-ready review says:

- `WT-YAP` remains `Proliferating progenitors` as top epithelial state
  (`35.9%`)
- `YAP5SA` also remains `Proliferating progenitors` as top epithelial state
  (`42.8%`)
- but `YAP5SA` shows approximately `100x` enrichment of
  `SOX2lowCFTR+` (`5.6%` versus `0.06%`) and approximately `100x`
  enrichment of `NKX2-1+SOX9+CFTR+` (`7.3%` versus `0.07%`)

This is biologically important because it supports a **directional positive
arm** for YAP activation without overstating identity conversion. In bridge
terms, this is mechanistic directionality, not claim closure.

### `GSE221343`: `CK+DCI` versus `YAP5SA+CK+DCI` versus `L+DCI`

This same-line SPC2-ST-B2 trio adds an equally important negative constraint.

- `CK+DCI` baseline top epithelial state: `Stromal-like cells 1` (`27.2%`)
- `YAP5SA+CK+DCI` top epithelial state: still `Stromal-like cells 1` (`25.8%`)
- `L+DCI` top epithelial state: `SOX2lowCFTR+ cells` (`34.8%`)

So within the same line:

- YAP activation in maintenance medium is **readable as a relative shift**
  but does not collapse the sample into the same endpoint reached by `L+DCI`.
- Directed iAT1 medium remains the stronger state-level driver.

This is a useful inventory result because it prevents the bridge from saying
"YAP alone explains the whole AT1 program." The current local data instead fit
a more careful reading: YAP/TAZ is a plausible mechanistic axis inside a
broader differentiation program.

## Layer 2: Pharmacologic Hippo / YAP Directionality Adds Cross-Lab Support

`GSE289846` adds a second mechanistic surface from a different iPSC system
(`B2-3`, Kyoto / CiRA) using `LATS-IN-1`.

The current local sample-wide read is directionally strong:

- `HOPX`: `0.612 -> 0.854`
- `AGER`: `0.077 -> 0.451`
- `PDPN`: `0.372 -> 0.501`
- `SFTPC`: `0.121 -> 0.044`
- `AQP5`: `0.060 -> 0.011`

The most honest interpretation is:

- `LATS-IN-1` is consistent with partial AT1-marker induction,
- the shift is cross-lab support for a Hippo/YAP-linked AT1 direction,
- but the exact maturity state remains system-specific and does not by itself
  solve the AQP5 or full AT1 closure problem.

This makes `GSE289846` a good **cross-lab mechanistic-support layer**, not a
standalone fetal-alignment layer.

## Layer 3: Commitment Ordering Belongs To BU3, Not To YAP Alone

For bridge use, YAP/TAZ should be tied back to the existing BU3 commitment
story rather than replacing it.

### `GSE221342`: endpoint ordering

The current BU3 chain remains the best endpoint scaffold:

- `iAT2_3D`: `Budtip progenitors` (`24.5%`)
- `iAT1_3D`: `SOX2lowCFTR+` (`60.9%`)
- `iAT1_ALI_p0`: `SOX2lowCFTR+` (`56.8%`)
- `iAT1_ALI_p1`: `SOX2lowCFTR+` (`78.0%`)

This tells us where a mechanobiology story would need to land: toward the
resolved AT1-directed BU3 endpoint, especially the later ALI state.

### `GSE246243`: kinetic ordering

If a new YAP/TAZ analysis is going to move beyond inventory, the most valuable
candidate tranche is `GSE246243`:

- same line as `GSE221342` (`BU3 NGAT`)
- same `CK+DCI -> L+DCI` axis
- `24 / 48 / 72 hr` timepoints

This is the right place to ask whether a mechanobiology-linked module rises
*before* or *along with* AT1-facing state resolution. At present it is still a
candidate tranche rather than an established bridge object.

## Layer 4: Fetal Compatibility Is Necessary, But Not Sufficient

Current fetal-primary and fetal-spatial datasets are still needed, but they
should be used for **compatibility** and **boundary setting**, not for direct
pathway closure.

### What they can do

- `GSE237359` and `E-MTAB-11435` can test whether a mechanobiology-linked
  epithelial program is compatible with fetal-primary alveolar-fated states.
- Quach-Farrell Xenium can anchor where AT1-onset sits inside strict distal
  fetal tissue context.
- He Visium Axis E can explain why an adjacency-scale mesenchymal layer makes
  mechanobiology biologically plausible.

### What they cannot do

- Quach-Farrell Xenium cannot directly test YAP/TAZ pathway activity because
  the panel lacks `YAP1`, `WWTR1`, `CTGF`, `CYR61`, `HOPX`, and `AQP5`.
- Marker positivity alone cannot distinguish nuclear YAP/TAZ activation from a
  downstream compatible state.
- None of the current bridge-native fetal layers directly measures flattening,
  membrane tension, or nuclear localization.

This is exactly why a YAP/TAZ addition should start with inventory
reconsideration rather than with an over-read of the existing fetal spatial
panel.

## External Mechanobiology Rationale

Primary literature supports the biological plausibility of this layered design.

- Fetal stretch experiments show that mechanical tension can increase AT1
  differentiation through a `ROCK-YAP/TAZ` pathway (`PMID: 34431413`).
- YAP has been shown to regulate alveolar epithelial differentiation and
  promote `AGER` through a transcriptional network involving `NFIB`, `KLF5`,
  and `NKX2-1` (`PMID: 34466790`).
- Human PSC work shows that active nuclear YAP is sufficient to promote a
  broad iAT2-to-iAT1 transcriptomic shift (`PMID: 36711505`).
- Human PSC screening work shows that `LATS-IN-1` and YAP/TAZ activation can
  promote AT1 differentiation, especially when combined with other pathway
  tuning (`PMID: 38552636`).

These papers support a mechanistic overlay for the bridge. They do not convert
the current bridge into a direct causal test of YAP/TAZ.

## Recommended Bridge-Side Use

If YAP/TAZ is added to the bridge now, the most honest use is:

1. **Inventory-first mechanistic framing**
   - direct perturbation / induction layer
   - commitment ordering layer
   - fetal compatibility layer
2. **Discussion-level biological interpretation**
   - why AT1-onset may appear before full AT1 maturity closure
   - why native mesenchymal adjacency may matter for a mechanotransductive axis
3. **Explicit non-closure statement**
   - current bridge does not directly measure nuclear YAP/TAZ activity,
     mechanical strain, or mature AT1 completion

In other words, YAP/TAZ should currently be used to strengthen **mechanistic
interpretation** of Tier 2 and the Tier 3 boundary, not to replace the current
AT1/AT2 ladder.

## Practical Next Step

The next useful analysis should not start from Quach-Farrell alone.

The best next step is to build a compact cross-layer bridge note with:

- `GSE221344` as the direct YAP perturbation layer,
- `GSE221343` and `GSE289846` as induction comparators,
- `GSE221342` and `GSE246243` as endpoint / kinetic ordering layers,
- current Tier 1 / Tier 2 fetal-primary and fetal-spatial syntheses as the
  compatibility layer.

That direct organoid-side read is now summarized in
`yap_taz_at1_directionality_2026-04-26.md`.

Only after that should targeted gene-level re-reads of fetal-primary datasets
be used to ask whether `YAP1` / `WWTR1` / `NKX2-1` / `KLF5` / `NFIB` /
`AGER`-related patterns are compatible with the mechanistic direction inferred
from the organoid perturbation inventory.
