# AT1 / AT2 Alignment Tiers, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `e_mtab_11435_condition_contrast_v1.md`
  - `e_mtab_11435_integration_v1.md`
  - `gse237359_inspect_v1.md`
  - `mesenchymal_axis_e_integration_v1.md`
  - `paper_results_skeleton_v1.md`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

Current bridge-side evidence is strongest when AT1 / AT2 interpretation is
split into three biological tiers rather than treated as one alveolar endpoint:

1. **Tier 1: AT2-related distal alignment** - currently the strongest positive
   bridge-side statement.
2. **Tier 2: AT1-onset / early alveolar commitment** - partially supported,
   but not claim-closing.
3. **Tier 3: full AT1 maturity** - currently open.

This tiering sharpens what the bridge can say biologically without promoting
local bridge-layer observations into registered evidence or confusing early
commitment with mature AT1 equivalence.

## Why Tiering Is Needed

The current positive P-0002 core is real but bounded. The registered fetal
spatial layer anchors a distal-epithelial tissue context, while local fetal and
organoid bridge datasets add biological coherence around alveolar commitment.
The same evidence does not close full AT1 maturity.

The main risk without tiering is over-collapsing three different statements:

- distal epithelial / AT2-related alignment,
- early AT1-relevant commitment,
- mature AT1 identity.

The current bridge should make those three levels explicit.

## Tier 1: AT2-Related Distal Alignment

### Biological reading

Tier 1 is the strongest bridge-side positive statement currently available:
organoid systems can align to a fetal distal epithelial program with clear
AT2-related features, and this alignment is not restricted to one source bank
or one organoid system.

### Main bridge-side supports

- `GSE237359` is a strong fetal-primary AT2 bridge:
  - `SFTPC` 1.000
  - `HOPX` 0.897
  - `AQP5` 0.304
  - `AGER` 0.067
  - `PDPN` 0.034
  - `SOX9` 0.051
- A bridge-layer GSE237359 synthesis
  (`gse237359_tier1_at2_bridge_2026-04-26.md`) strengthens the biological
  reading that this is a fetal-primary Tier 1 epithelial bridge and an
  independent corroboration of the iPSC/hESC-specific `AQP5` boundary.
- `E-MTAB-11435` self-renewing remains alveolar-fated rather than clean budtip,
  but it already carries strong epithelial commitment features:
  - `SFTPC` 0.998
  - `HOPX` 0.425
  - `AQP5` 0.321
  - `AGER` 0.028
- A bridge-layer E-MTAB-11435 synthesis
  (`e_mtab_11435_tier1_tier2_bridge_2026-04-26.md`) clarifies why the dataset
  belongs between Tier 1 and Tier 2 rather than serving as a clean C1 anchor.
- `E-MTAB-8221` Day_0 remains the cleaner fetal-primary C1 anchor and helps
  show that primary fetal organoid systems retain interpretable `AQP5`, unlike
  most iPSC/hESC-derived systems.

### Bridge-side consequence

The existing AQP5 caveat should stay narrowed to **iPSC/hESC-derived organoid
systems** per D-0008. The present bridge does support a system-specific
boundary:

- fetal-primary organoid systems can retain interpretable `AQP5` / `HOPX` /
  `SFTPC`;
- iPSC/hESC-derived organoid systems often do not.

Tier 1 therefore supports **AT2-related distal alignment** and
`alveolar_epithelial_maturation`-relevant biological coherence, without
claiming mature AT1 closure.

## Tier 2: AT1-Onset / Early Alveolar Commitment

### Biological reading

Tier 2 is the most useful next bridge-side biological layer. The current data
do support early AT1-relevant commitment or onset, but only partially and only
with explicit caveats.

### Main bridge-side supports

- `E-MTAB-11435` is most valuable here as an **internal condition contrast**,
  not as a clean budtip reference.
  - `HOPX`: 0.425 -> 0.985
  - `AQP5`: 0.321 -> 0.451
  - `AGER`: 0.028 -> 0.300
  - `SOX9+NKX2-1+` fraction: 0.256 -> 0.089
  - `MKI67` sample-wide: 0.173 -> 0.001
- This reads as a late-tip / alveolar-fated self-renewing state moving toward
  a more committed early alveolar state, with stronger AT1-relevant markers in
  differentiation.
- The dedicated bridge-layer E-MTAB-11435 synthesis
  (`e_mtab_11435_tier1_tier2_bridge_2026-04-26.md`) makes that Tier 1-to-Tier
  2 connector role explicit and preserves the non-closure caveat.
- The registered `EV-0009` BU3_NGAT_iAT1 ALI serial chain remains the organoid
  trajectory-side anchor for AT1-directed movement, with culture format held
  constant.
- The registered Quach-Farrell Xenium (`EV-0010`, `EV-0013`) remains the fetal
  tissue-context anchor for the distal epithelial niche, especially after the
  GW15 broad base class was narrowed to stricter `SFTPC`-positive /
  proximal-excluded variants.
- A bridge-layer Quach-Farrell reinspection
  (`quach_farrell_at1_onset_reinspection_2026-04-26.md`) further shows
  stage-enriched `AGER` / `PDPN` positivity within strict distal epithelial
  compartments from GW15 to GW18. That supports onset / commitment, not mature
  AT1 closure.

### What Tier 2 does and does not mean

Tier 2 does mean:

- early alveolar commitment can be described biologically,
- AT1-relevant onset markers begin to appear in fetal-primary bridge systems,
- the distal epithelial niche has tissue-context support in native fetal lung.

Tier 2 does not mean:

- mature AT1 equivalence is demonstrated,
- Quach-Farrell Xenium independently closes AT1 identity,
- `E-MTAB-11435` proves donor-resolved AT1 maturation.

The bridge should therefore use Tier 2 as a **partial commitment layer**, not a
claim-closing AT1 layer.

## Tier 3: Full AT1 Maturity

### Current status

Tier 3 is **not currently claimable** from bridge-side evidence.

### Why it remains open

- The registered Quach-Farrell Xenium 339-gene panel does not include `HOPX`
  or `AQP5`.
- `AGER` alone is not sufficient for full AT1 maturity.
- `PDPN` remains weak in the current fetal-primary organoid bridges.
- No single registered evidence unit simultaneously closes stage, trajectory,
  tissue context, morphology, mesenchymal adjudication, and a full AT1 marker
  panel.
- Independent cross-donor single-cell spatial replication is still absent.
- The `alveolar_epithelial_maturation` gap reflects both panel coverage and
  organoid-system boundary, not panel coverage alone.

### Most useful next bridge-side follow-up

`GSE280880` remains the most important independent-source follow-up for this
open tier. At present it is limited because feature / gene-symbol resolution
blocks marker-level epithelial scoring. Until that is resolved, it can support
author-label composition checks but not a direct marker-level AT1 closure read.

## Dataset Roles In The Tier Ladder

| Dataset / layer | Main tier role | Current best use | Main caveat |
|---|---|---|---|
| `EV-0009` / `GSE221342` BU3_NGAT_iAT1 serial chain | Tier 2 | organoid trajectory-side AT1-directed movement | not by itself a fetal tissue anchor |
| Quach-Farrell Xenium `GSE264425` (`EV-0010`, `EV-0013`, `EV-0011`, `EV-0014`) | Tier 2 context anchor | distal epithelial tissue-context validation, GW15 strict-variant admissibility refinement, artifact exclusion | not full AT1 maturity; no `HOPX` / `AQP5`; no mesenchymal closure |
| `E-MTAB-11435` | Tier 1-2 bridge | fetal-primary late-tip to early alveolar commitment contrast | pooled condition object; not donor-resolved; not clean C1 |
| `GSE237359` | Tier 1 bridge | fetal-primary AT2 maturation bridge; independent corroboration of the iPSC/hESC `AQP5` boundary | mesenchymal signal is E4 caveat, not E1 support |
| `E-MTAB-8221` Day_0 | Tier 1 support | fetal-primary C1/C2-adjacent bridge and `AQP5`-retaining primary BTO contrast | local bridge layer, not registered claim support |
| `GSE280880` | Tier 3 follow-up | independent OHRI/Thebaud epithelial and mesenchymal source after feature-resolution unblock | marker scoring blocked by feature/gene-symbol mapping |

## Relation To Axis E And Mesenchymal Interpretation

This epithelial tier ladder should stay separate from positive mesenchymal
niche claims.

- Tier 1 or Tier 2 epithelial support does **not** imply positive E1-E3 niche
  support.
- `GSE237359` remains the clearest example: strong epithelial AT2 / commitment
  biology, but only an E4 stromal caveat on the mesenchymal side.
- `E-MTAB-11435` is also useful as an epithelial late-tip / commitment bridge
  without resolving organoid-side E1-E3 niche support.

This separation is intentional. The bridge should define the **biological
target ontology** first; mesenchymal structure-readability or morphology-linked
extensions can then be tested separately without collapsing epithelial success
into niche closure.

## What Is Deliberately Excluded From Primary Bridge Evidence Here

Two classes of findings are intentionally not used as primary bridge-side tier
definitions in this document:

- satellite-only exploratory findings such as MCMR regression and pilot probes;
- light-probe ontology refinements that are biologically interesting but not
  yet matured into bridge-native synthesis.

Those findings may later strengthen Discussion or future `docs/analysis/`
documents, but the present ladder is built from bridge-native registered
evidence plus bridge-layer local syntheses already established in this
repository workflow.

For a mechanistic overlay focused on YAP/TAZ and AT1-directed interpretation,
see `yap_taz_at1_inventory_2026-04-26.md`, which separates direct
perturbation, commitment-ordering, and fetal-compatibility layers without
altering the present tier ladder.

## Paper Implication

The bridge no longer needs to choose between a purely governance-centered paper
and an over-claimed mature-alveolar paper. A more honest biological line is:

- Tier 1: AT2-related distal alignment is supportable.
- Tier 2: AT1-onset / early alveolar commitment is partially supportable.
- Tier 3: full AT1 maturity remains open.

This gives the paper a biology-first center while preserving the repository's
existing admissibility and non-promotion discipline.
