# Axis E Native-to-Organoid Gap, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `he_fibroblast_axis_e_reference_v1.md`
  - `mesenchymal_axis_e_integration_v1.md`
  - `gse280880_initial_inspection_v1.md`
  - `docs/analysis/gse280880_mesenchyme_author_label_context_2026-04-26.md`
  - `docs/analysis/organoid_axis_e_adjudication_2026-04-26.md`
- additional local checks:
  - direct 2026-04-26 ratio read from
    `mesenchymal_axis_e_gse280880_author_by_ga_v1.tsv`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

Axis E is now supported by a coherent native-side story and a coherent
organoid-side limitation story.

The current bridge can make five biology-first statements at once:

1. native fetal lung contains marker-resolved positive E1, E2, and E3
   mesenchymal compartments;
2. independent OHRI / Thebaud fetal lung remains strongly stromal-rich across
   `GA_14.1` to `GA_19.0`, even as distal epithelial fractions rise;
3. same-spot anti-correlation between epithelial and fibroblast weights in He
   Visium does not invalidate mesenchymal niche logic, because same-spot
   occupancy and tissue-context support are different questions;
4. the current bridge organoid datasets still do not close positive E1-E3
   niche support;
5. therefore stronger alveolarization claims should keep epithelial AT1/AT2
   alignment separate from mesenchymal tissue-context closure.

This is not a negative result in the simplistic sense. It is a more precise
biological map: native fetal lung carries a real and structured mesenchymal
context, while the current organoid bridge remains mostly epithelial.

## Native Fetal Lung Sets A High Bar For Positive Axis E Support

The He fetal fibroblast / smooth muscle reference is the current bridge's
cleanest positive-support baseline for Axis E.

| Sub-axis | Native reference | Key signals | Why it matters |
|---|---|---|---|
| `E1` alveolar fibro / lipofibro-like niche | `Alveolar fibro` | `WNT2` `0.9403`, `LIFR` `0.6304`, `PDGFRA` `0.3871`; E1 core frac `>=2` markers `0.8076` | positive-support E1 requires more than generic fibro markers |
| `E2` contractile myofibro-like niche | `Myofibro 1` | `ACTA2` `0.7823`, `TAGLN` `0.6890`, `MYL9` `0.8421`; E2 core frac `>=2` markers `0.7703` | ECM-rich stromal signal is not enough without contractile-core support |
| `E3` pericyte / smooth-muscle / airway-associated boundary | `Pericyte`, `Late airway SMC` | `Pericyte`: `PDGFRB` `0.9659`, `RGS5` `0.3098`; `Late airway SMC`: `MYH11` `0.9806`, `ACTA2` `0.9951`, `TAGLN` `0.9768` | positive E3 support must distinguish pericyte / SMC boundary states from alveolar-supportive fibro states |
| `E4` generic stromal mixture caveat | all fibro / SMC cells | `VIM` `0.9983`, `COL1A1` `0.9566`, `COL3A1` `0.9725` | generic stromal detectability alone is not subtype-resolved niche support |

This is the main native-side lesson for bridge interpretation: positive Axis E
support is a **high bar**, because native fetal lung already shows that
generic mesenchymal markers are widespread across multiple non-equivalent
states.

## Independent OHRI Fetal Lung Confirms Stromal-Rich Native Context

`GSE280880` is still blocked for marker-level scoring, but it already provides
an independent author-label composition reference from a distinct fetal source
bank.

At the author-label layer:

- overall coarse composition is stromal-heavy:
  - `Stroma_1` `0.657`
  - `Stroma_2` `0.065`
  - `PDGFRB+` `0.028`
  - `Epi_distal airway` `0.178`
- finer author labels remain dominated by stromal / fibro-like classes:
  - `Lipofibro precursor` `0.518`
  - `Lipofibro-like` `0.062`
  - `Myofibro` `0.108`
  - `Early fibro` `0.027`
  - `Bud tip progenitor` `0.093`
  - `Bud tip adjacent` `0.066`

The developmental read is also informative.

| Author-label proxy | earliest GA | latest GA | Spearman `r` vs GA | Read |
|---|---:|---:|---:|---|
| `E1` author-combined = `Lipofibro precursor + Lipofibro-like` | `0.7573` | `0.4184` | `-0.7333` | major stromal / lipofibro-like context remains substantial throughout the window |
| `E2` author-combined = `Myofibro + ACTA2+` | `0.1075` | `0.0947` | `-0.2833` | smaller myofibro-like compartment remains present across the window |
| epithelial comparator = `Bud tip progenitor + Bud tip adjacent` | `0.0269` | `0.3569` | `0.7667` | distal epithelial fraction rises while stromal dominance decreases |

An additional local ratio read makes the same point from a different angle.
The `E1` author-combined fraction remains larger than the epithelial
comparator at **every** GA point:

- `GA_14.1`: `28.18x`
- `GA_16.0`: `2.10x`
- `GA_19.0`: `1.17x`

So even late in this window, the native fetal context is not a mostly
epithelial substrate. Stromal / fibro-like material remains a major biological
layer.

## Why Visium Anti-Correlation Does Not Collapse Axis E

He Visium helps explain why the bridge should not equate niche support with
same-spot co-occupancy.

At the same-spot cell2location layer, E1 fibroblast weights tend to be
negative against epithelial weights:

| Axis E weight | epithelial weight | mean Spearman `r` |
|---|---|---:|
| `E1_alveolar_fibro` | `AT1` | `-0.1290` |
| `E1_alveolar_fibro` | `AT2` | `-0.2384` |
| `E1_alveolar_fibro` | `Late_tip` | `-0.2296` |
| `E2_myofibro` | `AT2` | `0.1500` |

At the library-mean layer the same trend remains visible:

| Axis E metric | epithelial metric | Spearman `r` |
|---|---|---:|
| `mean_axis_E1_alveolar_fibro` | `mean_SLT_AT2` | `-0.6643` |
| `mean_axis_E1_alveolar_fibro` | `mean_SLT_AT1` | `-0.5609` |
| `mean_axis_E1_broad_fibro_minimal` | `mean_SLT_AT2` | `-0.8252` |

This should **not** be read as "mesenchyme is biologically unrelated to
distal epithelium." It means only that:

- Visium same-spot weights are mixture measurements, not direct neighborhood
  maps;
- epithelial and mesenchymal cell states can occupy nearby but non-identical
  spatial compartments;
- the tissue-context role of Axis E is compatible with partial anti-correlation
  at the spot level.

This is exactly why the bridge separates positive niche support from generic
whole-tissue stromal mixture.

For an explicit coordinate-level follow-up showing that immediate neighboring
spots recover positive `E1` / `E2` association around distal epithelial
weights, while `E3` behaves as a more selective boundary-context layer, see
`he_visium_axis_e_neighborhood_2026-04-26.md`.

## Current Organoid Bridge Objects Still Do Not Close Positive E1-E3 Support

The organoid-side adjudication remains conservative.

| Dataset / layer | Current bridge use | Axis E status |
|---|---|---|
| `GSE237359` fetal-primary AT2 organoid | strong epithelial Tier 1 bridge | `E4 caveat`; stromal signal present but not subtype-resolved into positive E1-E3 support |
| `E-MTAB-11435` fetal-primary late-tip organoid | Tier 1-2 epithelial bridge | no positive E call from the currently exposed bridge object; working Axis E marker panel is unavailable |
| `EV-0009` / `GSE221342` BU3_NGAT_iAT1 serial chain | Tier 2 epithelial trajectory anchor | no organoid-side Axis E use in the present bridge |

The important biological point is not that mesenchyme has "failed." It is that
the present bridge evidence remains **mostly epithelial**, while the native
fetal reference shows that mesenchymal context is a real and structured layer
of the same developmental system.

## Practical Reading For The Paper

This synthesis supports a cleaner paper-level sentence:

- current public organoid evidence can support AT2-related distal alignment
  and partial AT1-onset interpretation;
- but stronger alveolarization language still requires a separate answer to
  the mesenchymal tissue-context question;
- current bridge datasets do not yet close that positive E1-E3 question.

In other words, epithelial success and mesenchymal niche closure should remain
separate accounting lines.

## Interface To Satellite Mesenchyme Work

This document also clarifies the bridge-to-satellite division of labor.

- bridge defines the biological target ontology and the bar for positive E1,
  E2, and E3 support;
- bridge also records the current organoid-side non-closure honestly;
- satellite mesenchyme work can later ask whether structure-linked or
  morphology-linked signals are readable against that ontology without changing
  the current bridge claim state.

That makes the current bridge result stronger, not weaker: the target is
explicit, the native context is anchored, and the open gap is biologically
named rather than hand-waved.
