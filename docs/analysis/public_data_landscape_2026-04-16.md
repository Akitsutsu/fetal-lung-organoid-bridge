# Public Data Landscape, 2026-04-16

- date: 2026-04-16
- status: non-authoritative analysis synthesis; not an evidence registry entry,
  not a claim-status change, not a contract change
- governance: `docs/analysis/README.md`
- source memos:
  - `dataset_census_v1.md`
  - `dataset_census_v2_audit_fix.md`
  - `census_classification_v2.md`
  - `census_classification_v2.tsv`
  - `research_overview_and_data_summary_ja_v1.md`
- repo-facing English; for human-discussion equivalents see
  `/mnt/c/Users/avanc/Desktop/lungs_analysis/notes/research_overview_and_data_summary_ja_v1.md`

## Summary

The current public-data landscape contains 81 explicit human fetal lung and
lung organoid dataset rows. The earlier 82-dataset count was audited and
resolved as a summary arithmetic error in the adult-derived / primary organoid
category, not as a missing dataset.

The census is broader than P-0002 alveolarization evidence. It includes fetal
single-cell references, fetal spatial datasets, fetal-primary-derived organoid
systems, iPSC / ESC organoid systems, perturbation models, adult boundary
contexts, and disease / infection contexts. Most rows are not claim-linked
evidence. Their use is classification, prioritization, bridge-layer analysis,
or boundary-context interpretation.

## Census Audit

- `census_classification_v1.tsv`: 82 rows including one audit placeholder.
- `dataset_census_v2_audit_fix.md`: resolves the discrepancy as summary
  overcount, not a missing dataset.
- `census_classification_v2.tsv`: 81 explicit dataset rows, audit placeholder
  removed.

Overall v2 counts:

| Dimension | Counts |
|---|---|
| L1 | INCLUDE 78; EDGE_CASE 3 |
| L2 | ADMIT 56; BLOCKED 25 |
| L3 | CLAIM_LINKED 3; PARTIAL_AXIS 27; BRIDGE_LAYER 12; BOUNDARY_CONTEXT 32; LOCAL_TRIAGE 5; DISQUALIFIED 2 |
| Follow-up priority | HIGH 15; MEDIUM 24; LOW 34; CONTEXTUAL 8 |

## Category Map

| Category | n | Primary role |
|---|---:|---|
| Fetal lung scRNA/snRNA | 13 | Native fetal references, stage trends, compartment baselines |
| Fetal chromatin / non-RNA | 1 | Boundary and future regulatory context |
| Fetal lung spatial | 7 | Registered spatial evidence plus gap-filling spatial candidates |
| Fetal-primary-derived organoid / explant | 11 | Primary fetal organoid bridges for C1, C2, AQP5, and perturbation biology |
| iPSC/ESC alveolar organoid | 15 | iPSC/hESC limitations, P-0001 / P-0002 organoid-side context |
| iPSC/ESC airway organoid | 8 | Axis A and airway differentiation comparisons |
| Kotton iPSC-AT2 disease modeling | 7 | Disease and perturbation boundary contexts |
| Infection / perturbation organoid | 6 | Contextual perturbation records outside the main P-0002 center |
| Adult-derived primary organoid | 8 | Adult boundary context for airway / SMG / organoid biology |
| Adult lung atlas context | 5 | Adult reference and disease boundary context |

## High-Priority Rows

The HIGH follow-up set includes:

- `GSE264407`
- `GSE280880`
- `E-MTAB-11278`
- `E-MTAB-10662`
- `GSE215898 (SS)`
- `GSE215895`
- `GSE264425`
- `GSE215897`
- `E-MTAB-11265`
- `E-MTAB-8221`
- `E-MTAB-11435`
- `GSE237359`
- `GSE221342/343/344`
- `GSE184142`

These rows are not all evidence rows. Their HIGH priority indicates biological
or paper-planning value, not claim-linked status.

## Source-Bank Structure

Most fetal data fall into two large source-bank / lab clusters:

- UW LDB / Spence-related cluster:
  - Quach-Farrell Xenium / Visium
  - Frum/Spence fetal snRNA / Xenium
  - `E-MTAB-8221`
  - `E-MTAB-10662`
  - `E-MTAB-12753`
  - `GSE266789`
  - `GSE297945`
- HDBR / Rawlins-related cluster:
  - `E-MTAB-11278`
  - `E-MTAB-11265`
  - `E-MTAB-11435`
  - `GSE237359`
  - `GSE296547 / GSE273089`
  - `GSE178529`

Other important sources include:

- OHRI / Thebaud: `GSE280880`, an independent fetal snRNA reference by author
  labels, with marker scoring blocked by missing feature symbols.
- Sountoulidis / Swedish federated EGA: `GSE215895` / `GSE215897`, important
  for early fetal / Carnegie-stage context but access and processed-layer
  details remain limiting.

## Current Use In Paper Planning

The paper should use the census to show that public data are informative but
unevenly distributed across claim layers:

- Registered evidence remains limited and claim-specific.
- Local fetal references sharpen biological interpretation.
- Bridge-layer organoid datasets help interpret axis biology.
- Boundary-context records prevent overclaiming.
- Blocked rows reveal what public data still cannot resolve.

The census does not by itself close P-0001 or P-0002.
