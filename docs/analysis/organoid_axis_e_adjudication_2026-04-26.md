# Organoid Axis E Adjudication, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `mesenchymal_axis_e_integration_v1.md`
  - `gse237359_inspect_v1.md`
  - `e_mtab_11435_condition_contrast_v1.md`
  - `e_mtab_11435_integration_v1.md`
  - `docs/analysis/axis_reference_findings_2026-04-16.md`
  - `docs/organoid_mapping_axes_scoping.md`
- additional local check:
  - direct 2026-04-26 feature-presence inspection of the local
    `E-MTAB-11435` H5AD against the working Axis E marker panel
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

Current bridge-side organoid datasets are still best read as **mostly
epithelial**. None of the main organoid-side bridge datasets currently closes
positive Axis E1-E3 mesenchymal niche support.

The practical adjudication is:

- `GSE237359`: strong epithelial Tier 1 support, **E4 caveat** on the
  mesenchymal side.
- `E-MTAB-11435`: strong epithelial Tier 1-2 bridge, **no positive organoid
  Axis E call** from the currently exposed object.
- `EV-0009` / `GSE221342` BU3_NGAT_iAT1 serial chain: epithelial trajectory
  anchor only, **no organoid Axis E call**.

This is not a failure of the bridge. It is the point of Axis E: epithelial
alignment and mesenchymal niche support are separate biological questions.

## Operational Rule

The bridge should continue to use the D-0010 Axis E split exactly as intended.

- **E1-E3** require an intentional or compartment-resolved mesenchymal
  component with subtype-level interpretability.
- **E4** is a caveat class for generic stromal mixture, epithelial-intent
  carryover, or unresolved whole-tissue stromal material.
- Broad stromal markers such as `VIM`, `COL1A1`, or `COL3A1` are not
  sufficient to claim alveolar fibroblast niche support.

This means an organoid record can be biologically useful for AT1/AT2 alignment
while remaining unusable for positive mesenchymal support.

## Dataset-Level Adjudication

| Dataset / layer | Epithelial role | Axis E call | Why |
|---|---|---|---|
| `GSE237359` fetal-primary AT2 organoid | Tier 1 AT2 bridge | `E4 caveat` | stromal signal is present but unresolved; not positive E1-E3 support |
| `E-MTAB-11435` fetal-primary late-tip organoid | Tier 1-2 epithelial bridge | `no positive E call` | current exposed object is used as an epithelial condition contrast; the working Axis E marker panel is not available in the exposed feature set |
| `EV-0009` / `GSE221342` BU3_NGAT_iAT1 serial chain | Tier 2 epithelial trajectory anchor | `no positive E call` | epithelial-only trajectory object; no mesenchymal adjudication target in the present bridge use |

## GSE237359: E4 Caveat, Not Positive Niche Support

`GSE237359` is the clearest case where strong epithelial value must be kept
separate from mesenchymal interpretation.

### Epithelial strength

The same dataset is strong for Tier 1 epithelial biology:

- `SFTPC` `1.000`
- `HOPX` `0.897`
- `AQP5` `0.304`

That is exactly why it is useful for the AT2-related distal-alignment question.

### Mesenchymal limitation

Its mesenchymal side does not support positive E1-E3 use:

| Observation | Value | Read |
|---|---:|---|
| Rawlins `majority_voting` Mid fibro | `0.098` | minor stromal component, not resolved niche support |
| `VIM` positive fraction | `0.283` | broad stromal signal |
| `COL1A1` positive fraction | `0.097` | low ECM-fibro signal |
| `COL3A1` positive fraction | `0.008` | near-floor ECM-fibro signal |

This is the definition of E4 in the current bridge logic:

- mesenchymal material is detectable;
- but it is not subtype-resolved into E1, E2, or E3;
- therefore it should remain a caveat rather than a positive niche claim.

## E-MTAB-11435: Epithelial Bridge Only

`E-MTAB-11435` is biologically valuable, but not for organoid-side Axis E
support.

### What it is good for

- `self_renewing` is an alveolar-fated fetal-primary epithelial state.
- `alveolar_differentiation` provides an internal transition toward early
  alveolar commitment.
- The dataset is therefore highly useful for the Tier 1-to-Tier 2 epithelial
  bridge.

### Why it should not be used for positive Axis E support

The currently exposed object does not support organoid-side E1-E3 adjudication.

A direct 2026-04-26 feature-presence check against the working Axis E marker
panel found no exposed features for:

- `VIM`, `COL1A1`, `COL3A1`
- `PDGFRA`, `WNT2`, `LIFR`
- `ACTA2`, `TAGLN`
- `RGS5`, `PDGFRB`, `MYH11`

This does **not** prove that mesenchymal biology is absent in an absolute
sense. It means only that the currently exposed bridge object is not usable for
positive Axis E subtype adjudication.

In bridge terms, the correct call is:

- keep `E-MTAB-11435` as epithelial Tier 1-2 support;
- do not treat it as evidence for E1-E3 niche closure;
- do not even force an E4 call from the current feature set, because the
  relevant stromal panel is not available.

## EV-0009 / GSE221342: No Axis E Read

The BU3_NGAT_iAT1 serial chain is an epithelial trajectory anchor with culture
format held constant. In the present bridge, it is not asked to answer a
mesenchymal question.

That matters because it prevents overloading the strongest organoid-side AT1
trajectory object with a niche claim it was never designed to support.

The correct use is:

- trajectory-side Tier 2 epithelial movement: yes;
- organoid-side E1-E3 support: no;
- organoid-side E4 caveat adjudication: not from the current bridge object.

## Why Native Axis E Still Matters

The absence of organoid-side E1-E3 closure does not make Axis E optional.

The native fetal references still show why this layer is biologically
load-bearing:

- D-0010 split Axis E into E1-E4 because generic stromal signal and true
  alveolar-supportive mesenchyme are not equivalent.
- In He Visium, same-spot epithelial-versus-mesenchymal anti-correlation does
  not invalidate niche interpretation at spot scale; it shows that adjacency
  and same-spot co-occupancy are different questions.
- In `GSE280880`, author-label composition remains strongly stromal /
  lipofibro-like across GA14-19, reinforcing that mesenchymal context is a
  real developmental layer even when organoid-side positive support is absent.
  See also `gse280880_mesenchyme_author_label_context_2026-04-26.md`.
- For a higher-order native-to-organoid synthesis of the same point, see
  `axis_e_native_to_organoid_gap_2026-04-26.md`.

The bridge should therefore keep two statements true at once:

- current organoid evidence is mostly epithelial;
- mesenchymal context is still biologically necessary for stronger
  alveolarization claims.

## Bridge Use

The point of this adjudication is to keep the biological accounting clean.

- Strong epithelial Tier 1 or Tier 2 support does **not** imply positive E1-E3
  support.
- `GSE237359` should be cited as epithelial Tier 1 plus E4 caveat.
- `E-MTAB-11435` should be cited as epithelial Tier 1-2 bridge without a
  positive organoid Axis E read.
- `EV-0009` should remain a trajectory anchor only.

This is also the right interface to the satellite mesenchyme work:

- bridge defines the target ontology and the positive-support bar;
- satellite can later test whether morphology-linked or structure-linked
  mesenchymal signals are readable against that ontology.

## Paper Implication

This document supports a cleaner biological sentence for the paper:

- current public organoid evidence can support distal epithelial, AT2-related,
  and partial AT1-onset interpretations;
- but organoid-side mesenchymal niche support remains unresolved or caveated in
  the currently accessible bridge datasets.

For a more specific molecular reading of that unresolved layer, especially the
`PDGFA -> PDGFRA` septation-coupling gap, see
`pdgfa_pdgfra_septation_gap_2026-04-26.md`.

That keeps the paper biology-first without pretending that epithelial success
and tissue-context closure are the same achievement.
