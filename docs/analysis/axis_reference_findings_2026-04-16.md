# Axis Reference Findings, 2026-04-16

- date: 2026-04-16
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `epithelial_analyses_summary_2026-04-16.md`
  - `epithelial_biology_narrative_v1.md`
  - `he_late_tip_reference_v1.md`
  - `he_epithelium_axis_a_basal_reference_v1.md`
  - `he_fibroblast_axis_e_reference_v1.md`
  - `mesenchymal_axis_e_integration_v1.md`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/research_overview_and_data_summary_ja_v1.md`

## Summary

Local analyses now support a two-layer framing:

1. Epithelial lineage-state fidelity: Axis C1, Axis C2, and Axis A.
2. Tissue-context fidelity: Axis E1-E4.

These layers are separable. An organoid system may partially reproduce fetal
distal epithelial states while still lacking the mesenchymal and spatial tissue
context required for stronger alveolarization claims.

## Axis C1: Budtip Progenitor

Working biology:

- SOX9+ NKX2-1+ lung identity.
- TESC / ID2 / CA2 budtip-marker dominance.
- FGF20 as supportive budtip / branching context.

Repository-reflected refinements:

- D-0008 removed the old requirement that AQP5 be absent from C1.
- D-0009 recorded the developmental-window caveat: the working C1 panel is
  most interpretable across the mid-pseudoglandular to canalicular window.

Local reference findings:

| Reference | Source | n | Key interpretation |
|---|---|---:|---|
| He Late tip | `E-MTAB-11278`, HDBR native fetal epithelium | 2,127 | Native-tissue C1 reference |
| `E-MTAB-8221` Day_0 c5 | UW LDB primary fetal BTO | 63 | Fetal-primary organoid C1 bridge |

He Late tip values:

- `frac_sox9_nkx21`: 0.780.
- `frac_budtip_STRICT`: 0.765.
- SOX9 fraction: 0.804.
- NKX2-1 fraction: 0.954.
- TESC fraction: 0.921.
- ID2 fraction: 0.905.
- CA2 fraction: 0.927.
- SFTPC fraction: 0.998.
- AQP5 fraction: 0.100.
- HOPX fraction: 0.489.

The C1 signal peaks around pcw15 in the He atlas and declines at later
post-canalicular windows. Lower fit outside this window should not be read as
simple absence of distal progenitor biology.

## Axis C2: Late-Tip / Early Alveolar Commitment

Working biology:

- SOX9+ NKX2-1+ SFTPC+ cells.
- Commitment markers HOPX, AQP5, AGER, and PDPN.
- Continuum from tip to stalk to AT1 / AT2 commitment.

Local findings:

- Late stalk is a strong transitional state: it retains budtip signal while
  carrying high C2 commitment.
- AT1 carries stronger HOPX / AQP5 / AGER / PDPN commitment.
- Primary fetal organoid systems retain AQP5 at interpretable fractions.
- iPSC/hESC-derived systems remain AQP5-low in the currently inspected
  landscape.

The AQP5 caveat should remain scoped to iPSC/hESC-derived organoid systems,
consistent with D-0008.

## Axis A: Proximal Airway / Basal

Current repository status:

- Axis A has not been revised in the sidecar after the 2026-04-16 analyses.
- The local revision remains deferred pending independent source confirmation.

Local finding:

He native fetal basal family (n = 278):

- TP63+KRT5+ fraction: 0.673.
- TP63+KRT5+ plus KRT14 or NGFR: 0.345.
- TP63+KRT5+KRT14+NGFR+ quartet: 0.018.
- KRT14+ fraction: 0.388.
- NGFR+ fraction: 0.054.

Interpretation:

- The adult-like canonical basal quartet is not fetal-realistic at the sampled
  fetal windows.
- TP63+KRT5+ is the current local fetal-realistic primary basal signature.
- `GSE160231` hPSC airway organoid retains only about 0.8% of this native
  fetal TP63+KRT5+ fraction.

Governance:

- This remains local-only because it is currently single-source.
- Independent confirmation from `GSE280880`, Sountoulidis, or another fetal
  reference should precede a sidecar update.

## Axis E: Mesenchymal Tissue Context

Repository-reflected refinement:

- D-0010 split Axis E into E1-E4.

Working sub-axes:

- E1: alveolar fibroblast / lipofibroblast niche.
- E2: myofibroblast / septation-like mesenchyme.
- E3: pericyte / smooth muscle / airway-associated mesenchyme.
- E4: generic stromal mixture / off-target caveat.

He fibroblast / smooth muscle reference:

- Alveolar fibroblast E1 anchor: n = 8,289.
  - PDGFRA fraction: 0.387.
  - WNT2 fraction: 0.940.
  - LIFR fraction: 0.630.
  - E1 core >= 2: 0.808.
- Myofibro 1 E2 anchor:
  - ACTA2 fraction: 0.782.
  - TAGLN fraction: 0.689.
  - contractile core >= 2: 0.770.
- E3 anchors:
  - Pericyte: n = 2,169.
  - Late airway SMC: n = 1,855.
- E4 caution:
  - VIM: 0.998.
  - COL1A1: 0.957.
  - COL3A1: 0.973.

Interpretation:

- Broad stromal markers are not sufficient to identify alveolar fibroblast
  niche support.
- Same-spot anti-correlation between epithelial and mesenchymal weights in
  Visium can reflect adjacent but mutually exclusive compartments at capture
  resolution.
- E1-E3 support in organoids requires intentional or compartment-resolved
  mesenchyme.
- Epithelial-intent organoid data with unresolved stromal signal should remain
  E4 caveat.

## Paper Implication

The evidence-map paper should distinguish:

- epithelial lineage-state fidelity, where local public data support partial
  distal / canalicular alignment; and
- tissue-context fidelity, where organoid-resolved mesenchymal niche support
  remains open.

