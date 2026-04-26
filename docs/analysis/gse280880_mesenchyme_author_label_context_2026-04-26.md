# GSE280880 Mesenchyme Author-Label Context, 2026-04-26

- date: 2026-04-26
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `gse280880_initial_inspection_v1.md`
  - `mesenchymal_axis_e_integration_v1.md`
  - `docs/analysis/axis_reference_findings_2026-04-16.md`
- source files:
  - `GSE280880_meta_data_GEO.csv.gz`
  - `GSE280880_UMI_count_matrix.csv.gz`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/HUMAN_RESEARCH_STATUS_ja.md`

## Summary

`GSE280880` is currently usable as an **independent native mesenchymal context
dataset**, but only at the author-label layer.

It is not yet usable for marker-level Axis E scoring because the public GEO
supplementary UMI matrix still lacks row-level gene symbols or Ensembl IDs.

Even with that limitation, the author labels already support three useful
bridge-side statements:

1. the OHRI / Thebaud fetal lung reference is strongly stromal / lipofibro
   rich across GA14-19;
2. a myofibroblast-like compartment is present throughout the same window but
   is much smaller than the lipofibro-like compartment;
3. epithelial budtip-adjacent fractions rise with gestational age while the
   lipofibro-like fraction falls, reinforcing that epithelial and mesenchymal
   context must be read together during this developmental window.

## Why This Dataset Matters For Axis E

The bridge already has a strong reason to separate epithelial success from
mesenchymal niche support. `GSE280880` strengthens that separation using an
independent native fetal source bank.

- Source context: OHRI / Thebaud fetal human lung, distinct from the UW LDB
  bank that anchors Quach-Farrell and `E-MTAB-8221`.
- Scale: `23,030` nuclei across `9` gestational-age points from `GA_14.1` to
  `GA_19.0`.
- Biological emphasis: the dataset is dominated by stromal labels rather than
  epithelial labels.

That is exactly why it matters for mesenchyme-side interpretation. It shows
that a strong stromal context is a normal feature of native fetal lung in the
same developmental window where the bridge is asking epithelial alignment
questions.

## Public-Layer Limitation

The current public processed layer is still incomplete for marker-level use.

- GEO supplementary files currently expose:
  - `GSE280880_meta_data_GEO.csv.gz`
  - `GSE280880_UMI_count_matrix.csv.gz`
- The matrix header contains cell barcodes only.
- Matrix rows are numeric counts without gene symbols or Ensembl IDs.

So the dataset is **not safe** for direct marker-level scoring of:

- E1 markers such as `PDGFRA`, `WNT2`, `LIFR`;
- E2 markers such as `ACTA2`, `TAGLN`;
- E3 markers such as `RGS5`, `PDGFRB`, `MYH11`;
- or epithelial markers such as `SOX9`, `SFTPC`, `HOPX`, `AQP5`, `AGER`.

Until a feature list or author object is obtained, the bridge should use
`GSE280880` only as an author-label composition reference.

## Mesenchymal Dominance At The Author-Label Layer

### Overall composition

At coarse label level, the dataset is stromal-heavy:

| Author label | Count | Fraction |
|---|---:|---:|
| `Stroma_1` | 15,124 | 0.657 |
| `Stroma_2` | 1,492 | 0.065 |
| `PDGFRB+` | 644 | 0.028 |
| `Epi_distal airway` | 4,099 | 0.178 |

At finer label level:

| Author label | Count | Fraction |
|---|---:|---:|
| `Lipofibro precursor` | 11,941 | 0.518 |
| `Myofibro` | 2,485 | 0.108 |
| `Bud tip progenitor` | 2,131 | 0.093 |
| `Bud tip adjacent` | 1,517 | 0.066 |
| `Lipofibro-like` | 1,439 | 0.062 |
| `Early fibro` | 622 | 0.027 |

This is already enough to show that native fetal lung in this window carries a
large stromal / lipofibro-like compartment alongside distal epithelial states.

## Practical Axis E Groupings Used Here

Because marker-level validation is blocked, the current read should stay close
to the author annotations.

- **E1 author-combined**: `Lipofibro precursor + Lipofibro-like`
- **E1 broad author-combined**: `Lipofibro precursor + Lipofibro-like + Early fibro`
- **E2 author-combined**: `Myofibro + ACTA2+`
- **Epithelial developmental comparator**: `Bud tip progenitor + Bud tip adjacent`

These are author-label proxies, not replacement marker definitions.

## Gestational-Age Trends

### E1 lipofibro-like author-combined

The strongest pattern is the decline of the lipofibro-like author group across
the pseudoglandular window.

| GA | E1 author-combined fraction |
|---|---:|
| `GA_14.1` | 0.7573 |
| `GA_14.3` | 0.6408 |
| `GA_15.1` | 0.6332 |
| `GA_15.5` | 0.5511 |
| `GA_16.0` | 0.5003 |
| `GA_16.3` | 0.5683 |
| `GA_17.5` | 0.5544 |
| `GA_18.2` | 0.5682 |
| `GA_19.0` | 0.4184 |

Trend summary:

- first GA: `0.7573`
- last GA: `0.4184`
- Spearman `r` versus GA: `-0.7333`

This does not prove mature alveolar fibroblast identity at marker level. It
does show that lipofibro-like mesenchymal context is a major native component
early in this window and remains substantial through `GA_19.0`.

### E2 myofibro / ACTA2 author-combined

The myofibro-like compartment is present throughout but much smaller and less
dynamic than the E1 lipofibro-like compartment.

| GA | E2 author-combined fraction |
|---|---:|
| `GA_14.1` | 0.1075 |
| `GA_14.3` | 0.1169 |
| `GA_15.1` | 0.1228 |
| `GA_15.5` | 0.1293 |
| `GA_16.0` | 0.1361 |
| `GA_16.3` | 0.0996 |
| `GA_17.5` | 0.1083 |
| `GA_18.2` | 0.1227 |
| `GA_19.0` | 0.0947 |

Trend summary:

- first GA: `0.1075`
- last GA: `0.0947`
- Spearman `r` versus GA: `-0.2833`

The bridge use of this pattern is conservative: E2-like mesenchyme is clearly
present, but it does not show the same strong monotonic behavior as the E1
author-combined compartment.

### Epithelial budtip-adjacent comparator

The epithelial developmental comparator moves in the opposite direction.

| GA | `Bud tip progenitor + Bud tip adjacent` fraction |
|---|---:|
| `GA_14.1` | 0.0269 |
| `GA_14.3` | 0.1096 |
| `GA_15.1` | 0.0949 |
| `GA_15.5` | 0.1586 |
| `GA_16.0` | 0.2386 |
| `GA_16.3` | 0.1727 |
| `GA_17.5` | 0.2261 |
| `GA_18.2` | 0.1441 |
| `GA_19.0` | 0.3569 |

Trend summary:

- first GA: `0.0269`
- last GA: `0.3569`
- Spearman `r` versus GA: `0.7667`

This reciprocal pattern is biologically useful even without gene labels. It
shows that stromal-rich native context and changing distal epithelial content
coexist across the same developmental interval.

## What This Supports

`GSE280880` currently supports three bridge-side uses.

### 1. Native mesenchymal context is real and large

The dataset independently confirms that fetal lung in this window is not a
mostly epithelial substrate. Large stromal / lipofibro-like compartments are a
normal part of the tissue context.

### 2. Axis E is biologically load-bearing, not optional

Because the native tissue is so stromal-rich, stronger alveolarization claims
should continue to distinguish epithelial alignment from mesenchymal niche
closure.

### 3. Organoid-side Axis E gaps remain interpretable

The organoid-side bridge objects can remain mostly epithelial without being
dismissed as biologically useless. But they should also not be overread as if
they already reproduce the native mesenchymal context seen here.

## What This Does Not Support

This document does **not** support:

- marker-level E1/E2/E3 scoring;
- promotion of `GSE280880` to claim-linked evidence;
- direct comparison of native OHRI labels to organoid marker-defined states;
- or any statement that author labels alone prove a specific fibroblast subtype
  taxonomy.

The current use is intentionally narrower:

- independent native context,
- author-label composition,
- mesenchyme-first biological orientation.

## Relation To Organoid Axis E Adjudication

This document pairs naturally with
`organoid_axis_e_adjudication_2026-04-26.md`.

- `GSE280880` shows why positive mesenchymal context matters.
- `organoid_axis_e_adjudication_2026-04-26.md` shows why current organoid-side
  bridge datasets do not yet close that context.

Together they create a cleaner mesenchyme-side story:

- native fetal mesenchymal context is substantial and developmentally
  structured;
- current organoid bridge datasets remain mostly epithelial;
- therefore mesenchymal niche closure remains an honest open layer rather than
  a hidden failure.

For a higher-order synthesis that also brings in the He native reference and
Visium interpretation, see
`axis_e_native_to_organoid_gap_2026-04-26.md`.

## Paper Implication

The paper can now say something sharper on the mesenchyme side:

- independent native fetal references support a large lipofibro-like and
  myofibro-like context across the same developmental window used for bridge
  epithelial interpretation;
- current public organoid datasets do not yet reproduce that context at a
  resolvable subtype level;
- this is exactly why Axis E must remain separate from epithelial alignment.
